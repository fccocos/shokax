---
title: OpenGL图形渲染之元素缓冲对象
categories:
  - OpenGL
tag:
  - OpenGL
valine: true
sticky: true
date: '2023-10-23 21:08'
---

```c++
//
//  main.cpp
//  OpenGL_Start_Tectangles
//
//  Created by apple on 2023/10/23.
//

#include <iostream>
#include <glad/glad.h>
#include <GLFW/glfw3.h>




void inputProcess(GLFWwindow *window);
void framebuffer_size_callback(GLFWwindow* window, int width, int height);

const int SCR_WIDTH = 800;
const int SCR_HEIGHT = 600;

const char* vertexShaderSourceCode = "#version 330 core\n"
"layout (location=0) in vec3 aPos;\n"
""
"void main(){\n"
"  gl_Position = vec4(aPos, 1.0f);\n"
"}\n\0";

const char* fragmentShaderSourceCode = "#version 330 core\n"
"out vec4 FragColor;\n"
"void main(){\n"
"  FragColor = vec4(1.0f, 0.5f, 0.2f, 1.0f);\n"
"}\n\0";

int main(int argc, const char * argv[]) {
    glfwInit();
    glfwWindowHint(GLFW_CONTEXT_VERSION_MAJOR, 3);
    glfwWindowHint(GLFW_CONTEXT_VERSION_MINOR, 3);
    glfwWindowHint(GLFW_OPENGL_PROFILE, GLFW_OPENGL_CORE_PROFILE);
#ifdef __APPLE__
    glfwWindowHint(GLFW_OPENGL_FORWARD_COMPAT, GL_TRUE);
#endif
    GLFWwindow *window = glfwCreateWindow(SCR_WIDTH, SCR_HEIGHT, "LearnOpenGL", NULL, NULL);
    if(window == NULL){
        std::cerr<<"Failed to create window"<<std::endl;
        glfwTerminate();
        return -1;
    }
    
    glfwMakeContextCurrent(window);
    
    if(!gladLoadGLLoader((GLADloadproc)glfwGetProcAddress)){
        std::cerr<<"Failled to initialize GLAD"<<std::endl;
        return -1;
    }
    
    glfwSetFramebufferSizeCallback(window, framebuffer_size_callback);
    
    // shader
    unsigned int vertex_shader, fragment_shader;
    unsigned int shader_program;
    int success;
    char errlog[512]={0};
    vertex_shader = glCreateShader(GL_VERTEX_SHADER);
    glShaderSource(vertex_shader, 1, &vertexShaderSourceCode, NULL);
    glCompileShader(vertex_shader);
    glGetShaderiv(vertex_shader,GL_COMPILE_STATUS, &success);
    if(!success){
        glGetShaderInfoLog(vertex_shader, sizeof(errlog), NULL, errlog);
        std::cerr<<"ERROR::SHADER::VERTEX::COMPLIATION_FAILED"<<errlog<<std::endl;
    }
    fragment_shader = glCreateShader(GL_FRAGMENT_SHADER);
    glShaderSource(fragment_shader, 1, &fragmentShaderSourceCode, NULL);
    glCompileShader(fragment_shader);
    glGetShaderiv(fragment_shader,GL_COMPILE_STATUS, &success);
    if(!success){
        glGetShaderInfoLog(fragment_shader, sizeof(errlog), NULL, errlog);
        std::cerr<<"ERROR::SHADER::FRAGMENT::COMPLIATION_FAILED"<<errlog<<std::endl;
    }
    shader_program = glCreateProgram();
    glAttachShader(shader_program, vertex_shader);
    glAttachShader(shader_program, fragment_shader);
    glLinkProgram(shader_program);
    glGetProgramiv(shader_program, GL_LINK_STATUS, &success);
    if(!success){
        glGetProgramInfoLog(shader_program, sizeof(errlog), NULL, errlog);
        std::cerr<<"ERROR::SHADER::PROGRAM::LINKING_FAILED\n"<<errlog<<std::endl;
    }
    glDeleteShader(vertex_shader);
    glDeleteShader(fragment_shader);
    
    GLfloat vertices[] = {
         0.5f,  0.5f, 0.0f, // 0 右上
         0.5f, -0.5f, 0.0f, // 1 右下
        -0.5f, -0.5f, 0.0f, // 2 左下
        -0.5f,  0.5f, 0.0f  // 3 左上
    };
    GLuint indices[] = {
        0, 1, 3, // 右上 右下 左上
        1, 2, 3  // 右下 左下 左上
    };
    // 数据绑定
    GLuint VAO, VBO, EBO;
    // ID
    glGenVertexArrays(1, &VAO);
    glGenBuffers(1, &VBO);
    glGenBuffers(1, &EBO);
    // Bind
    glBindVertexArray(VAO);
    glBindBuffer(GL_ARRAY_BUFFER, VBO);
    glBufferData(GL_ARRAY_BUFFER, sizeof(vertices), vertices, GL_STATIC_DRAW);
    glBindBuffer(GL_ELEMENT_ARRAY_BUFFER, EBO);
    glBufferData(GL_ELEMENT_ARRAY_BUFFER, sizeof(indices), indices, GL_STATIC_DRAW);
    // Attribute
    glVertexAttribPointer(0, 3, GL_FLOAT, GL_FALSE, 3*sizeof(GLfloat), (void*)0);
    //Activate
    glEnableVertexAttribArray(0);
    
    // 可以通过属性指针来绑定顶点缓冲对象
    glBindBuffer(GL_ARRAY_BUFFER, 0);
    
    // unbind VAO
    glBindVertexArray(0);
    
   
    
    // wireframe polygons
    //glPolygonMode(GL_FRONT_AND_BACK, GL_LINE);
    
    
    while(!glfwWindowShouldClose(window)){
        inputProcess(window);
        // render
        glClearColor(0.3f, 0.2f, 0.3f, 1.0f);
        glClear(GL_COLOR_BUFFER_BIT);
      
        // triangle
        glUseProgram(shader_program);
        glBindVertexArray(VAO);
        glDrawElements(GL_TRIANGLES, 6, GL_UNSIGNED_INT, 0);
        glBindVertexArray(0);
        
        glfwSwapBuffers(window);
        glfwPollEvents();
          
    }
    
    glDeleteVertexArrays(1, &VAO);
    glDeleteBuffers(1, &VBO);
    glDeleteProgram(shader_program);
    
    glfwTerminate();
    return 0;
}
void inputProcess(GLFWwindow* window){
    if(glfwGetKey(window, GLFW_KEY_ESCAPE)==GLFW_PRESS){
        glfwSetWindowShouldClose(window, GL_TRUE);
    }
}
void framebuffer_size_callback(GLFWwindow *window, int width, int height){
    glViewport(0,0,width,height);
}


```

![image-20231023212410195](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231023212410195.png)