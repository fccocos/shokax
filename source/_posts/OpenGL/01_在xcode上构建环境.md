---
title: 构建OpenGL开发环境
math: true
date: '2023-10-21 15:06'
---

### OpenGL编程之在xcode上搭建开发环境

#### 第一步：下载GLFW库并编译

#### 第二步：将GLFW库导入项目中

1. 首先打开项目配置页面

![image-20231021151543164](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021151543164.png)

2. 按照上图所示操作，将会进入构建配置页面

![image-20231021151909898](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021151909898.png)

3. 找到`Search Paths`选项

![image-20231021152329644](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021152329644.png)

4. 找到`Header Search Paths`和`Library Search Path`两个选项

![image-20231021152542169](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021152542169.png)

5. 在项目中创建一个`lib`项目用存放第三方库

![image-20231021152935960](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021152935960.png)

6. 将`glfw`的库文件复制到`.\lib\glfw`中

![image-20231021153437138](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021153437138.png)

7. 在项目中再创建一个`include`文件夹，用于存放第三方库的头文件，然后在`include`文件夹中创建一个`glfw`文件夹，用于存放glfw所需的头文件

![image-20231021154048722](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021154048722.png)

8. 在步骤4中所找到的`Header search paths`和`library search paths`用于搜索项目所需的第三方头文件目录路径和第三方库目录路径。现在要做的是将GLFW的库头文件目录路径和GLFW的库目录路径写入到这两个项目中即可。

   ![image-20231021155528545](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021155528545.png)

9. 进入`General`选项页面

   ![image-20231021155648763](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021155648763.png)

10. 将`Frameworks and Libraries`选项中的`libglfw.3.dalib`的`Embed`值修改为`Embed&Sign`

    ![image-20231021155905650](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021155905650.png)

11. 至此，OpenGL程序应该可以运行了。如果还不能运行，可以在`Build Phases`页面的`Link Binary With Libraries`中添加需要的`framework`即可。

    ![image-20231021161452150](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021161452150.png)

    

#### 第三步：配置GLAD库并倒入到项目中

1. 打开GLAD[在线服务](https://glad.dav1d.de)

   ![image-20231021162150045](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021162150045.png)

2. 根据要求设置配置选项

   ![image-20231021162424995](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021162424995.png)

3.点击生成`GENERATE`按钮

![image-20231021162622846](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021162622846.png)

![image-20231021162840617](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021162840617.png)

4. 其他操作与上述步骤相同，不多做赘述。

#### 步骤四：编写测试代码

```c++
#include <iostream>
#include <GLFW/glfw3.h>
#include <glad/glad.h>

const int w_width = 800;
const int w_height = 600;

void framebuffer_size_callback(GLFWwindow* window, int width, int height);
void inputProcess(GLFWwindow* window);

int main(int argc, char* argv{}){
  glfwInit();
  glfwWindowHint(GLFW_CONTEXT_VERSION_MAJOR, 3);
  glfwWindowHint(GLFW_CONTEXT_VERSION_MINOR, 3);
  glfwWindowHint(GLFW_OPENGL_PROFILE, GLFW_OPENGL_CORE_PROFILE);
#ifdef __APPLE__
  glfwWindowHint(GLFLW_OPENGL_FORWORD_COMPAT,GL_TRUE);
#endif
  GLFWwindow* window = glfwCreateWindow(window,0,0,w_width,w_height,NULL,NULL);
  if(!window){
    std::cerr<<"Failed to create GLFW window!"<<std:endl;
    return -1;
  }
  glfwMakeContextCurrent(window);
  if(!gladLoadGLLoader((GLADloadproc)glfwGetProAddress)){
    std::cerr<<"Failed to initialize GLAD!"<<std::endl;
    return -1;
  }
  glfwViewport(0,0,w_width,w_hegiht);
  glfwSetFramebuffersizeCallback(framebuffer_size_callback);
  while(!glfwWindowShouldClose(window)){
    inputProcess(window);
    glClearColor(0.2f,0.3f,0.2f,1.0f);
    glClear(OPENGL_COLOR_BUFFER_BIT);
    
    glSwapBuffer(window);
    glPollEvents();
  }
  glfwTerminate();
  return 0;
}

void inputProcess(GLFWwindow *window){
  if(glfwGetKey(window,GLFW_KEY_ESCAPE)==GLFW_PRESS){
    glfwWindowShouldClose(window, GL_TRUE);
  }
}

void framebuffer_size_callback(GLFWwindow *window, int width, int height){
  glfwViewport(0,0, width, height);
}
```

测试结果

![image-20231021182415237](https://gitee.com/fangcongss/blog-pic/raw/master/img/image-20231021182415237.png)