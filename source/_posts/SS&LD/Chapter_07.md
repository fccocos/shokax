---
title: 第七章 查找
math: true
date: '2023-10-15 06:16'
---

顺序表数据结构

```c++
#define LIST_INIT_SIZE 1024
#define LISTINCREMNET 32
typedef struct {
  int *elem;
  int length;
  int list_size;
}DSqList;
```

顺序查找

```c++
typedef DSqList SSTable;
int Seq_Search(SSTable T,  int key){
  for(int i=0; i<T.length; ++i){
    if(T.elem[i] == elem) return i;
  }
  return -1;
}
```

> 时间复杂度：$O(n)$
>
> 空间复杂度：$O(1)$

![有序表的顺序查找树](https://gitee.com/fangcongss/blog-pic/raw/master/img/%E6%9C%89%E5%BA%8F%E8%A1%A8%E7%9A%84%E9%A1%BA%E5%BA%8F%E6%9F%A5%E6%89%BE%E6%A0%91.png)

折半查找

```c++
typedef DSqList SSTable;
int Binary_Search(SSTable T, int key){
  int low=0, high=T.length-1,mid=0;
  while(low<=high){
    mid = (low+high)/2;
    if(key == T.elem[mid])
      return mid;
    else if(key < T.elem[mid])
      high = mid - 1;
    else
      low = mid + 1;
  }
  return -1;
}
  
```

