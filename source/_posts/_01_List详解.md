---
title: _01_List详解
date: 2023-06-20 20:01:28
tags: [JDK]
---
# ArrayList

## 三个构造方法

```java
/*
指定初始化大小，在后续扩容时，以这个capacity为基础进行1.5倍扩容
*/
public ArrayList(int initialCapacity){
  if(initialCapacity>0){
    this.elementData=new Object[initialCapacity];
  }else if(initialCapacity==0){
    this.elementData=EMPTY_ELEMENTDATA;
  }else{
    throw new IllegalArgumentException("Illegal Capacity: "+
                                       initialCapacity);
  }
}

/*
默认初始化一个空数组，等到真正add element 的时候，才进行内存分配
*/
public ArrayList(){
  this.elementData=DEFAULTCAPACITY_EMPTY_ELEMENTDATA;
}

/*
将传入的集合复制ArrayList中，如果集合也是ArrayList类型，那么将内部元素的值进行拷贝，如果不是，那么将进行Arrays.copyOf操作，进行值拷贝
*/
public ArrayList(Collection<?extends E> c){
  Object[]a=c.toArray();
  if((size=a.length)!=0){
    if(c.getClass()==ArrayList.class){
      elementData=a;
    }else{
      elementData=Arrays.copyOf(a,size,Object[].class);
    }
  }else{
    // replace with empty array.
    elementData=EMPTY_ELEMENTDATA;
  }
}
```

## 增加元素

## 删除元素

## 修改元素

## 查询元素

# Vector

# LinkedList

## 构造方法

## 增加元素

## 删除元素

## 修改元素

# ArrayList/Vector/LinkedList 三者异同

|            | 底层数据结构   | 线程安全  | 查询效率 | 增加、删除效率 |
|------------|----------|-------|------|---------|
| ArrayList  | Object数组 | 非线程安全 |      |         |
| Vector     | Object数组 | 线程安全  |      |         |
| LinkedList | 双向链表     | 非线程安全 |      |         |



