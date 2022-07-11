- [Why Coinbase](#why-coinbase)
- [What can you bring for our company](#what-can-you-bring-for-our-company)
- [Self Introduction](#self-introduction)
- [Network](#network)
  - [Public IP vs Private IP](#public-ip-vs-private-ip)
  - [subnet mask](#subnet-mask)
  - [HTTPS vs HTTP](#https-vs-http)
  - [TCP 3-way handshaking](#tcp-3-way-handshaking)
  - [NAT](#nat)
  - [What happens when you enter google.com in the web browser?](#what-happens-when-you-enter-googlecom-in-the-web-browser)
- [Java](#java)
  - [Java’s Feature](#javas-feature)
  - [OOP 3 features](#oop-3-features)
    - [Encapsulation](#encapsulation)
    - [Inheritance](#inheritance)
    - [Polymorphism](#polymorphism)
  - [Java Keywords](#java-keywords)
    - [access modifier](#access-modifier)
    - [non-access modifier](#non-access-modifier)
  - [System.out.println()](#systemoutprintln)
  - [Lambda](#lambda)
  - [JVM](#jvm)
    - [Class Loader](#class-loader)
    - [Method Area](#method-area)
    - [Heap Area](#heap-area)
    - [JVM Language Stack](#jvm-language-stack)
    - [Native Method Stack](#native-method-stack)
    - [PC Registers](#pc-registers)
  - [Working of Garbage Collector](#working-of-garbage-collector)
    - [Garbage Collector Overview](#garbage-collector-overview)
    - [GC机制](#gc机制)
      - [JVM Heap memory (Hotspot heap structure)  in java consists of following elements](#jvm-heap-memory-hotspot-heap-structure--in-java-consists-of-following-elements)
      - [Young Generation (Minor garbage collection occurs in Young Generation)](#young-generation-minor-garbage-collection-occurs-in-young-generation)
      - [Old Generation (tenured generation) - (Major garbage collection occurs in Old Generation)](#old-generation-tenured-generation---major-garbage-collection-occurs-in-old-generation)
      - [Permanent Generation or (Permgen) - (full garbage collection occurs in permanent generation in java).](#permanent-generation-or-permgen---full-garbage-collection-occurs-in-permanent-generation-in-java)
    - [Types of Garbage Collection](#types-of-garbage-collection)
    - [Mark and Sweep Algorithm](#mark-and-sweep-algorithm)
      - [Concurrent Mark and Sweep](#concurrent-mark-and-sweep)
      - [Parallel Mark and Sweep](#parallel-mark-and-sweep)
  - [Java创建对象的过程](#java创建对象的过程)
  - [Java Collection Time Complexity](#java-collection-time-complexity)
    - [List](#list)
      - [ArrayList](#arraylist)
      - [LinkedList](#linkedlist)
    - [Set](#set)
      - [HashSet](#hashset)
      - [TreeSet（基于红黑树）](#treeset基于红黑树)
    - [map](#map)
      - [TreeMap（基于红黑树）](#treemap基于红黑树)
      - [HashMap](#hashmap)
      - [LinkedHashMap](#linkedhashmap)
  - [HashMap, HashTable, HashSet](#hashmap-hashtable-hashset)
    - [说说 List,Set,Map 三者的区别?](#说说-listsetmap-三者的区别)
    - [HashMap 详解](#hashmap-详解)
    - [HashMap vs HashTable](#hashmap-vs-hashtable)
      - [Thread Safe](#thread-safe)
      - [key -> Value](#key---value)
      - [初始容量大小和扩容](#初始容量大小和扩容)
      - [底层数据结构](#底层数据结构)
    - [Hashmap vs HashSet](#hashmap-vs-hashset)
    - [HashSet如何检查重复](#hashset如何检查重复)
  - [Spring](#spring)
    - [IOC](#ioc)
    - [AOP](#aop)
- [Database](#database)
  - [MongoDB?](#mongodb)
  - [What is DynamoDB?](#what-is-dynamodb)
  - [Diff between MongoDb and DynamoDB](#diff-between-mongodb-and-dynamodb)
    - [platform:](#platform)
    - [configuration](#configuration)
    - [Querying data & indexes](#querying-data--indexes)
  - [Normal form](#normal-form)
    - [1NF (First Normal Form) Rules](#1nf-first-normal-form-rules)
    - [2NF (Second Normal Form) Rules](#2nf-second-normal-form-rules)
    - [3NF (Third Normal Form) Rules](#3nf-third-normal-form-rules)
- [Resume:](#resume)
  - [Coinbase](#coinbase)
  - [Cmind Ai:](#cmind-ai)
  - [Awesome Rush B:](#awesome-rush-b)
  - [Online Pet Adoption Platform](#online-pet-adoption-platform)
  - [Automated data analytics report process:](#automated-data-analytics-report-process)


## Why Coinbase

Our company's main business is crypto currency, which is very popular in recent years, -> digital age

The company is developing rapidly and has great potential. I believe it is a good opportunity for me，Because I have just graduated, full of energy and hope to learn a lot

## What can you bring for our company

1: for the work, for the Tech skills, I know I am just a new grad, so compared with my colleagus, I am the most inexperienced guy, It is hard to say that I could bring some advanced tech for the company, but I think my advantage is I have strong ability to learn and i am a fast learner, so basically I am curious about new knowledges, and acts to explore them! so if I was in, I could adapt the productive env rapidly and contribute my own power, help my collegues, imporve the efficiency of the whole project!
2: for the Diversity, I come from China, and for my self, always seek to improve myself, and I am open to others critical feedback. I really enjoy cooking!


## Self Introduction
My name is Sichen Zhao, I am pursuing an Information System major at Northeastern University. I am expected to graduate in December this year.

I worked as a software engineer intern in Cmind-Ai this Spring, which is a fin-tech start-up company. and my job there includes developing** new features like trending news and stock portfolio via React, MongoDB

可说可不说（he once optimized the** backend algorithms via ElasticSearch for high-efficiency search on GBs data and increased the search speed by 60%.）



For the study, I took some courses like *Data Structure & Algorithms, Web Design & User Experience, Web Development Tools, Application Engineering & Development, Data Science Engineering Methods & Tools.*

I never stop learning and always seek to improve myself, I am curious about new possibilities and acts to explore them. 

My undergraduate major is Management Information System, so there were some courses related to computer programming and data analysis. The undergraduate study career has inspired my interest in programming, which is why I came to NEU to continue learning programming..

**毕业时间**：Dec. 2021

**Visa**: Expiration Date: June 18, 2024

**I20**: Dec, 20, 2021

## Network
### Public IP vs Private IP
Private IP address of a system is the IP address that is used to communicate within the same network. Using private IP data or information can be sent or received within the same network. 

Public IP address of a system is the IP address that is used to communicate outside the network. A public IP address is basically assigned by the ISP (Internet Service Provider). 

![](https://markpersonal.oss-us-east-1.aliyuncs.com/pic/20220710222655.png)

### subnet mask
A subnet mask defines the range of IP addresses that can be used within a network or subnet. It also separates an IP address into two parts: network bits and host bits.

### HTTPS vs HTTP
HyperText Transfer Protocol

HTTPS is HTTP with encryption. The difference between the two protocols is that HTTPS uses TLS (SSL) to encrypt normal HTTP requests and responses. As a result, HTTPS is far more secure than HTTP. A website that uses HTTP has HTTP:// in its URL, while a website that uses HTTPS has HTTPS://.

![](https://markpersonal.oss-us-east-1.aliyuncs.com/pic/20220710223741.png)

### TCP 3-way handshaking
- Step 1 (SYN): In the first step, the client wants to establish a connection with a server, so it sends a segment with SYN(Synchronize Sequence Number) which informs the server that the client is likely to start communication and with what sequence number it starts segments with
- Step 2 (SYN + ACK): Server responds to the client request with SYN-ACK signal bits set. Acknowledgement(ACK) signifies the response of the segment it received and SYN signifies with what sequence number it is likely to start the segments with
- Step 3 (ACK): In the final part client acknowledges the response of the server and they both establish a reliable connection with which they will start the actual data transfer

### NAT
NAT stands for network address translation. It’s a way to map multiple local private addresses to a public one before transferring the information. 

### What happens when you enter google.com in the web browser?
Below are the steps that are being followed:

- **Check the browser cache** first if the content is fresh and present in cache display the same.
- If not, the browser checks if the IP of the URL is present in the cache (browser and OS) if not then **request the OS to do a DNS lookup using UDP to get the corresponding IP address of the URL from the DNS server to establish a new TCP connection**.
- A new TCP connection is set between the browser and the server using three-way handshaking.
- An HTTP request is sent to the server using the TCP connection.
- The web servers running on the Servers handle the incoming HTTP request and send the HTTP response.
- The browser process the HTTP response sent by the server and may close the TCP connection or reuse the same for future requests.
- If the response data is cacheable then browsers cache the same.
- Browser decodes the response and renders the content.


## Java
### Java’s Feature
1. Simple
2. Object-Oriented
3. Portable
4. Platform independent: write once, run anywhere
5. Secured
6. Robust
7. Architecture neutral
8. Interpreted
9. High Performance
10. Multithreaded
11. Distributed
12. Dynamic

### OOP 3 features
#### Encapsulation
The meaning of Encapsulation, is to make sure that "sensitive" data is hidden from users. To achieve this, you must:

- declare class variables/attributes as private
- provide public get and set methods to access and update the value of a private variable
#### Inheritance
In Java, it is possible to inherit attributes and methods from one class to another. We group the "inheritance concept" into two categories:

- subclass (child) - the class that inherits from another class
- superclass (parent) - the class being inherited from

To inherit from a class, use the extends keyword.

#### Polymorphism
Polymorphism means "many forms", and it occurs when we have many classes that are related to each other by inheritance.

Inheritance lets us inherit attributes and methods from another class. Polymorphism uses those methods to perform different tasks. This allows us to perform a single action in different ways.

Polymorphism in Java can be performed by two different methods:

- Method Overloading
- Method Overriding

![](https://markpersonal.oss-us-east-1.aliyuncs.com/pic/20220706191803.png)

Overlading vs. Overriding
- Overloading is a term used to describe when two methods have the same name but different in the type or number of arguments
- Overriding occurs when a method shares the same name and function signature as another method in its super class

Overwritting: 
Car Class, not overwrite ->  com.stu.Car@2542880d class name + @ + hashCode
overwrite -> 
```java
public String toString(){
        return "这个汽车名叫 "+carName+",型号是 "+carNo+",汽车颜色 "+color+",价格 "+price;
    }
```


### Java Keywords
#### access modifier
- **public:** Used for classes, attributes, methods and constructors, making them accessible by any other class
- **private:**	Used for attributes, methods and constructors, making them only accessible within the declared class
- **protected:**	Used for attributes, methods and constructors, making them accessible in the same package and subclasses

#### non-access modifier
- **static:**	Used for methods and attributes. Static methods/attributes can be accessed without creating an object of a class
- **final:** Used for classes, attributes and methods, which makes them non-changeable (impossible to inherit or override)
- **abstract:** Used for classes and methods: An abstract class cannot be used to create objects (to access it, it must be inherited from another class). An abstract method can only be used in an abstract class, and it does not have a body. The body is provided by the subclass (inherited from)
- **synchronized:**	which specifies that methods can only be accessed by one thread at a time

### System.out.println()

**System.out.println()** is used to print an argument that is passed to it. The statement can be broken into 3 parts which can be understood separately as:

1. **System:** It is a final class defined in the java.lang package. ![](https://images2015.cnblogs.com/blog/739525/201601/739525-20160119185727687-1621310018.png)
2. **out:** This is an instance of **PrintStream** type, which is a public and static member field of the System class. ![](https://images2015.cnblogs.com/blog/739525/201601/739525-20160119190442328-550264769.png)
3. **println():** As all instances of **PrintStream class** have a public method println(), hence we can invoke the same on out as well. This is an upgraded version of print(). It prints any argument passed to it and adds a new line to the output. We can assume that System.out represents the Standard Output Stream. ![](https://images2015.cnblogs.com/blog/739525/201601/739525-20160119191040250-1798193938.png)


### Lambda
```java
Collections.sort(Arrays.asList(s), new Comparator<String>() {
    @Override
    public int compare(String o1, String o2) {
        return o1.length()-o2.length();
    }
});
```
```java
Collections.sort(Arrays.asList(s), (p,q)->{
    return p.length()-q.length();
});
```


### JVM
JVM (Java Virtual Machine) is an abstract machine. It is a specification that provides runtime environment in which java bytecode can be executed.
![](https://www.guru99.com/images/1/2.png)
#### Class Loader
The class loader is a subsystem used for loading class files. It performs three major functions viz. Loading, Linking, and Initialization.
#### Method Area
Method Area is a part of the heap memory which is shared among all the threads. It creates when the JVM starts up. It is used to store class structure, superclass name, interface name, and constructors. The JVM stores the following kinds of information in the method area:

1. A Fully qualified name of a type (ex: String)
2. The type's modifiers
3. Type's direct superclass name
4. A structured list of the fully qualified names of super interfaces.

#### Heap Area

**Heap stores the actual objects. It creates when the JVM starts up.** The user can control the heap if needed. It can be of fixed or dynamic size. **When you use a new keyword, the JVM creates an instance for the object in a heap. While the reference of that object stores in the stack. There exists only one heap for each running JVM process.** When heap becomes full, the garbage is collected. For example:

`StringBuilder sb= new StringBuilder();`

The above statement creates an object of the StringBuilder class. The object allocates to the heap, and the reference sb allocates to stack. 

Heap is divided into the following parts:

![](https://img-blog.csdn.net/20150908155026054)

* Young generation
* Survivor space
* Old generation
* Permanent generation
* Code Cache

大部分情况，对象都会首先在 Eden 区域分配，在一次新生代垃圾回收后，如果对象还存活，则会进入 s0 或者 s1，并且对象的年龄还会加 1(Eden区i>Survivor 区后对象的初始年龄变为1)，当它的年龄增加到一定程度(默认为15岁)，就会被晋升到老年代中。对象晋升到老年代的年龄阈值，可以通过参数 `-XX:MaxTenuringThreshold` 来设置。另外，大对象和⻓期存活的对象会直接进入老年代。

年轻代（Young Generation）

对象在被创建时，内存首先是在年轻代进行分配（注意，大对象可以直接在老年代分配）。当年轻代需要回收时会触发Minor GC(也称作Young GC)。

年轻代由Eden Space和两块相同大小的Survivor Space（又称S0和S1）构成，可通过-Xmn参数来调整新生代大小，也可通过-XX:SurvivorRadio来调整Eden Space和Survivor Space大小。不同的GC方式会按不同的方式来按此值划分Eden Space和Survivor Space，有些GC方式还会根据运行状况来动态调整Eden、S0、S1的大小。

年轻代的Eden区内存是连续的，所以其分配会非常快；同样Eden区的回收也非常快（因为大部分情况下Eden区对象存活时间非常短，而Eden区采用的复制回收算法，此算法在存活对象比例很少的情况下非常高效，后面会详细介绍）。

如果在执行垃圾回收之后，仍没有足够的内存分配，也不能再扩展，将会抛出OutOfMemoryError:Java Heap Space异常。

老年代（Old Generation）

老年代用于存放在年轻代中经多次垃圾回收仍然存活的对象，可以理解为比较老一点的对象，例如缓存对象；新建的对象也有可能在老年代上直接分配内存，这主要有两种情况：一种为大对象，可以通过启动参数设置-XX:PretenureSizeThreshold=1024，表示超过多大时就不在年轻代分配，而是直接在老年代分配。此参数在年轻代采用Parallel Scavenge GC时无效，因为其会根据运行情况自己决定什么对象直接在老年代上分配内存；另一种为大的数组对象，且数组对象中无引用外部对象。

当老年代满了的时候就需要对老年代进行垃圾回收，老年代的垃圾回收称作Major GC（也称作Full GC）。

老年代所占用的内存大小为-Xmx对应的值减去-Xmn对应的值。

#### JVM Language Stack
**Stack memory is responsible for holding references to heap objects and for storing value types (also known in Java as primitive types), which hold the value itself rather than a reference to an object from the heap.**

The stack is a part of memory that contains information about nested method calls down to the current position in the program. It also contains all local variables and references to objects on the heap defined in currently executing methods.

This structure allows the runtime to return from the method knowing the address whence it was called, and also clear all local variables after exiting the method. Every thread has its own stack.


#### Native Method Stack

It is also known as C stack. **It is a stack for native code written in a language other than Java.** Java Native Interface (JNI) calls the native stack. The performance of the native stack depends on the OS.

#### PC Registers

**Each thread has a Program Counter (PC) register associated with it. PC register stores the return address or a native pointer. It also contains the address of the JVM instructions currently being executed.**
程序计数器是一个比较小的内存区域，可能是CPU寄存器或者操作系统内存，其主要用于指示当前线程所执行的字节码执行到了第几行，可以理解为是当前线程的行号指示器。字节码解释器在工作时，会通过改变这个计数器的值来取下一条语句指令。 每个程序计数器只用来记录一个线程的行号，所以它是线程私有（一个线程就有一个程序计数器）的。

如果程序执行的是一个Java方法，则计数器记录的是正在执行的虚拟机字节码指令地址；如果正在执行的是一个本地（native，由C语言编写完成）方法，则计数器的值为Undefined，由于程序计数器只是记录当前指令地址，所以不存在内存溢出的情况，因此，程序计数器也是所有JVM内存区域中唯一一个没有定义OutOfMemoryError的区域。

### Working of Garbage Collector

#### Garbage Collector Overview

When a program executes in Java, it uses memory in different ways. The heap is a part of memory where objects live. It's the only part of memory that involved in the garbage collection process. It is also known as garbage collectible heap. All the garbage collection makes sure that the heap has as much free space as possible. The function of the garbage collector is to find and delete the objects that cannot be reached.

#### GC机制

##### JVM Heap memory (Hotspot heap structure)  in java consists of following elements
- Young Generation
  - Eden
  - S0 (Survivor space 0)
  - S1 (Survivor space 1)
- Old Generation (Tenured)
- Permanent Generation.

##### Young Generation (Minor garbage collection occurs in Young Generation)

- New objects are allocated in Young generation.
- Minor garbage collection occurs in Young Generation.
- When the young generation fills up, this causes a minor garbage collection. All the unreferenced (dead) objects are cleaned up from young generation.

##### Old Generation (tenured generation) - (Major garbage collection occurs in Old Generation)
  
- The Old Generation is used for storing the long surviving aged objects.
- Major garbage collection occurs in Old Generation.
- When the old generation fills up, this causes a major garbage collection. Objects are cleaned up from old generation.

##### Permanent Generation or (Permgen) - (full garbage collection occurs in permanent generation in java).

- Permanent generation Space contains metadata required by JVM to describe the classes and methods used in the application.
- The permanent generation is included in a full garbage collection in java.

#### Types of Garbage Collection

There are five types of garbage collection are as follows:

* **Serial GC:** It uses the mark and sweeps approach for young and old generations, which is minor and major GC.
* **Parallel GC:** It is similar to serial GC except that, it spawns N (the number of CPU cores in the system) threads for young generation garbage collection.
* **Parallel Old GC:** It is similar to parallel GC, except that it uses multiple threads for both generations.
* **Concurrent Mark Sweep (CMS) Collector:** **It does the garbage collection for the old generation. You can limit the number of threads in CMS collector using** **XX:ParalleCMSThreads=JVM option** . It is also known as Concurrent Low Pause Collector.
* **G1 Garbage Collector:** It introduced in Java 7. Its objective is to replace the CMS collector. It is a parallel, concurrent, and CMS collector. There is no young and old generation space. It divides the heap into several equal sized heaps. It first collects the regions with lesser live data.

#### Mark and Sweep Algorithm

JRockit JVM uses the mark, and sweep algorithm for performing the garbage collection. It contains two phases, the mark phase, and the sweep phase.

**Mark Phase:** Objects that are accessible from the threads, native handles, and other GC root sources are marked as live. Every object tree has more than one root objects. GC root is always reachable. So any object that has a garbage collection root at its root. It identifies and marks all objects that are in use, and the remaining can be considered garbage.

![Memory Management in Java](https://static.javatpoint.com/core/images/memory-management-in-java2.png)

**Sweep Phase:** In this phase, the heap is traversed to find the gap between the live objects. These gaps are recorded in the free list and are available for new object allocation.

There are two improved versions of mark and sweep:

* **Concurrent Mark and Sweep**
* **Parallel Mark and Sweep**

##### Concurrent Mark and Sweep

It allows the threads to continue running during a large portion of the garbage collection. There are following types of marking:

* **Initial marking:** It identifies the root set of live objects. It is done while threads are paused.
* **Concurrent marking:** In this marking, the reference from the root set are followed. It finds and marks the rest of the live objects in a heap. It is done while the thread is running.
* **Pre-cleaning marking:** It identifies the changes made by concurrent marking. Other live objects marked and found. It is done while the threads are running.
* **Final marking:** It identifies the changes made by pre-cleaning marking. Other live objects marked and found. It is done while threads are paused.

##### Parallel Mark and Sweep

It uses all available CPU in the system for performing the garbage collection as fast as possible. It is also called the parallel garbage collector. Threads do not execute when the parallel garbage collection executes.

**Pros of Mark and Sweep**

* It is a recurring process.
* It is an infinite loop.
* No additional overheads allowed during the execution of an algorithm.

**Cons of Mark and Sweep**

* It stops the normal program execution while the garbage collection algorithm runs.
* It runs multiple times on a program.

### Java创建对象的过程

![](https://markpersonal.oss-us-east-1.aliyuncs.com/pic/20220106160142.png)

### Java Collection Time Complexity

#### List

##### ArrayList

get() 直接读取下标，复杂度 O(1)
add(E) 直接在队尾添加，复杂度 O(1)
add(index, E) 在第n个元素后插入，n后面的元素需要向后移动，复杂度 O(n)
remove() 删除元素后面的元素需要逐个前移，复杂度 O(n)

##### LinkedList

addFirst() 添加队列头部，复杂度 O(1)
removeFirst() 删除队列头部，复杂度 O(1)
addLast() 添加队列尾部，复杂度 O(1)
removeLast() 删除队列尾部，复杂度 O(1)
getFirst() 获取队列头部，复杂度 O(1)
getLast() 获取队列尾部，复杂度 O(1)
get() 获取第n个元素，依次遍历，复杂度O(n)
add(E) 添加到队列尾部，复杂度O(1)
add(index, E) 添加到第n个元素后，需要先查找到第n个元素，复杂度O(n)
remove() 删除元素，修改前后元素节点指针，复杂度O(1)

#### Set

##### HashSet

add() 复杂度为 O(1)
remove() 复杂度为 O(1)
contains() 复杂度为 O(1)

##### TreeSet（基于红黑树）

add() 复杂度为 O(log (n))
remove() 复杂度为 O(log (n))
contains() 复杂度为 O(log (n))

#### map

##### TreeMap（基于红黑树）

平均时间复杂度 O(log n)

##### HashMap

正常时间复杂度 O(1)~O(n)
红黑树后 O(log n)

##### LinkedHashMap

能以时间复杂度 O(1) 查找元素，又能够保证key的有序性

### HashMap, HashTable, HashSet

#### 说说 List,Set,Map 三者的区别?

- List (对付顺序的好帮手): 存储的元素是有序的、可重复的。
- Set (注重独一无二的性质): 存储的元素是无序的、不可重复的。
- Map (用 Key 来搜索的专家): 使用键值对(kye-value)存储，类似于数学上的函数 y=f(x)，“x”代表 key，"y"代表 value，Key 是无序的、不可重复的，value 是无序的、可重复的，每个键最多映射到一个值。

#### HashMap 详解

- inherits(implement) from Map interface
- **equals()**: It checks the equality of two objects. It compares the Key, whether they are equal or not. It is a method of the Object class. It can be overridden. If you override the equals() method, then it is mandatory to override the hashCode() method.
- **hashCode()**: This is the method of the object class. It returns the memory reference of the object in integer form. The value received from the method is used as the bucket number. The bucket number is the address of the element inside the map. Hash code of null Key is 0.
- **Buckets**: Array of the node is called buckets. Each node has a data structure like a LinkedList. More than one node can share the same bucket. It may be different in capacity.
- 底层：
  - JDK1.8之前：数组 + 链表
  - JDK1.8之后：数组 + 链表 + 红黑树，链表长度 > 8时转化为红黑树
  - **Hash Collision**
    - This is the case when the calculated index value is the same for two or more Keys. Let's calculate the hash code for another Key "Sunny." Suppose the hash code for "Sunny" is 63281940. To store the Key in the memory, we have to calculate index by using the index formula.
    - `Index=63281940 & (16-1) = 4`
    - ![](https://static.javatpoint.com/images/core/working-of-hashmap-in-java4.png)
    - The value 4 is the computed index value where the Key will be stored in HashMap. In this case, equals() method check that both Keys are equal or not. If Keys are same, replace the value with the current value. Otherwise, connect this node object to the existing node object through the LinkedList. Hence both Keys will be stored at index 4.
- 初始化默认大小16，必须是2的整数次幂(the integer power of 2)
- 最大容量:必须是2的整数次幂且小于2^30
- load factor 负载因子 默认 0.75 当元素数量大于capacity * load factor的时候，扩容 -> *2
- ![](https://zeral.cn/images/java/hashmap/tradeoff-time-space.png)
- ![](https://zeral.cn/images/java/hashmap/hashmap-1.8.png)

#### HashMap vs HashTable

##### Thread Safe

HashMap is non-synchronized. It is not thread-safe and can’t be shared between many threads without proper synchronization code whereas Hashtable is synchronized. It is thread-safe and can be shared with many threads.

HashMap is generally preferred over HashTable if thread synchronization is not needed

##### key -> Value

HashMap allows one null key and multiple null values whereas Hashtable doesn’t allow any null key or value -> `NullPointerException`.

##### 初始容量大小和扩容

创建时如果不指定容量初始值，Hashtable 默认的初始大小为 11，之后每次扩充，容量变为原来的 2n+1。

HashMap 默认的初始化大小为 16。之后每次扩充，容量变为原来的 2 倍。

创建时如果给定了容量初始值，那么 Hashtable 会直接使用你给定的大小，而 HashMap 会将其扩充为 2 的幂次方大小(HashMap 中的 tableSizeFor() 方法保证，下面给出了源代码)。也就是说 HashMap 总是使用 2 的幂作为哈希表的大小,后面会介绍到为什么是 2 的幂次方。

##### 底层数据结构

HashMap : JDK1.8 之前 HashMap 由数组+链表组成的，数组是 HashMap 的主体，链表则是主要为了解决哈希冲突而存在的(“拉链法”解决冲突)。JDK1.8 以后在解决哈希冲突时有了较大的变化，当链表⻓度大于阈值(默认为 8)(将链表转换成红黑树前会判断，如果当前数组的⻓度小于64，那么会选择先进行数组扩容，而不是转换为红黑树)时，将链表转化为红黑树，以减少搜索时间

JDK1.8 以后的 HashMap 在解决哈希冲突时有了较大的变化，当链表⻓度大于阈值(默认为 8)(将链表转换成红黑树前会判断，如果当前数组的⻓度小于 64，那么会选择先进行数组扩容，而不是转换为红黑树)时，将链表转化为红黑树，以减少搜索时间。Hashtable 没有这样的机制。

#### Hashmap vs HashSet

如果你看过 HashSet 源码的话就应该知道:HashSet 底层就是基于 HashMap 实现的。(HashSet 的源码非常非常少，因为除了 clone() 、 writeObject() 、 readObject() 是 HashSet 自己不得不实现之外，其他方法都是直接调用 HashMap 中的方法。

HashSet is an implementation of Set Interface which does not allow duplicate value.

HashMap internally uses a hashing method to store the elements. On the other hand, the HashSet uses the HashMap object to store or add the elements.

![](https://img2018.cnblogs.com/blog/1265453/202002/1265453-20200222231738458-1252225000.png)

#### HashSet如何检查重复

compute the object's hashcode -> determine where to add / compare with other's hashcode

- if not -> add
- if duplicate -> 这时会调用 equals() 方法来检查 hashcode 相等的对象是否真的相同 -> false


### Spring
#### IOC
Spring IoC Container is the core of Spring Framework. It creates the objects, configures and assembles their dependencies, manages their entire life cycle. The Container uses Dependency Injection(DI) to manage the components that make up the application. It gets the information about the objects from a configuration file(XML) or Java Code or Java Annotations and Java POJO class. These objects are called Beans. Since the Controlling of Java objects and their lifecycle is not done by the developers, hence the name Inversion Of Control. 

There are two types of IoC containers. They are:

- BeanFactory
- ApplicationContext

#### AOP

**Aspect Oriented Programming (AOP)** compliments OOPs in the sense that it also provides modularity. But the key unit of modularity is aspect than class.

AOP breaks the program logic into distinct parts (called concerns). It is used to increase modularity by **cross-cutting concerns**.

A **cross-cutting concern** is a concern that can affect the whole application and should be centralized in one location in code as possible, such as transaction management, authentication, logging, security etc.

## Database

### RDBMS vs. NoSQL
In choosing between SQL vs. NoSQL, you’ll need to think about what your data looks like, how you’ll query it, and your scalability needs.

#### Data structure
SQL: data -> primarily structured
A SQL database is a great fit for **transaction-oriented systems such as customer relationship management tools, accounting software, and e-commerce platforms**

Each row in a SQL database is a distinct entity (e.g. a customer), and each column is an attribute that describes that entity (e.g. address, job title, item purchased, etc.).

need ACID compliance. 
- Atomicity – each transaction either succeeds completely or is fully rolled back.
- Consistency – data written to a database must be valid according to all defined rules.
- Isolation – When transactions are run concurrently, they do not contend with each other, and act as if they were being run sequentially.
- Durability – Once a transaction has been committed to the database, it is considered permanent, even in the event of a system failure.

NoSQL: data requirements aren’t clear or data is unstructured
A NoSQL database is a much better fit to store data like **article content, social media posts, sensor data, and other types of unstructured data that won’t fit neatly into a table**. 
NoSQL databases were built with flexibility and scalability in mind, and follows the BASE consistency model, which means:

The data you store in a NoSQL database does not need a predefined schema like you do for a SQL database. Rather, the data can be column stores, document-oriented, graph-based, or key-value pairs. This provides much more flexibility and less upfront planning when managing your database.

#### Ability to query data
The next factor to consider is 
- how often you’ll query your data
- how quickly you need to run queries
- who will be responsible for running these queries.

SQL is a popular programming language that has been around for over 45 years, so it’s extremely mature and well-known. It efficiently executes queries and retrieves and edits data quickly.

When NoSQL database technology was being built, developers focused on scalability and flexibility, not query efficiency.

Querying NoSQL databases typically requires developers or data scientists, which will be more costly and less efficient.

#### Scaling
**SQL databases scale vertically**, meaning you’ll need to increase the capacity of a single server (increasing CPU, RAM, or SSD) to scale your database. SQL databases were designed to run on a single server to maintain the integrity of the data, so they’re not easy to scale.

**NoSQL databases scale horizontally**, meaning you can add more servers to power your growing database. This is a huge advantage that NoSQL has over SQL.


### MongoDB?
MongoDB is a general-purpose, document-based distributed NoSQL database.

|MongoDB|RDBMS Counterpart|Description|
|:-:|:-:|:-:|
|Collection|Table|A set of MongoDB documents.
|Document|Row|Collection of data stored in BSON format
|Field|Field/Column|A single element in a MongoDB document containing values as field and value pairs

### What is DynamoDB?
DynamoDB is a proprietary NoSQL database by Amazon that supports key-value and document data offered via the Amazon Web Services.


|DynamoDB|RDBMS Counterpart|Description
|:-:|:-:|:-:|
|Table|Table|A grouped collection of DynamoDB Items.
Item|Row|Data records that contain data. Each item consists of one or more attributes.
Attribute|Field/Column|The base element of DynamoDB contains a single data value.

### Diff between MongoDb and DynamoDB
#### platform:
MongoDB is platform-agnostic.
DynamoDB is limited to AWS.
#### configuration
MongoDb -> need complex configuration
DynamoDb -> DynamoDB is a fully managed database that allows users to start using the database straightaway, as AWS will manage all the scaling, availability, and updates. 

#### Querying data & indexes
MongoDB offers more flexibility in querying data as it enables users to aggregate and query data natively in multiple ways, such as:

- Single keys
- Ranges
- Graph traversals
- JOINs

DynamoDB:
- DynamoDB natively supports only key-value querie


### Normal form
Normalization is a database design technique that reduces data redundancy and eliminates undesirable characteristics

#### 1NF (First Normal Form) Rules
- Each table cell should contain a single value.
- Each record needs to be unique.

#### 2NF (Second Normal Form) Rules
- Rule 1- Be in 1NF
- Rule 2- Single Column Primary Key that does not functionally dependant on any subset of candidate key relation

#### 3NF (Third Normal Form) Rules
- Rule 1- Be in 2NF
- Rule 2- Has no transitive functional dependencies


## Resume:
### Coinbase
1. Crypto Watchlist
    1. Client service
        1. Create a client connection to the Users Service (codegen here)
        2. Create a client connection to the Exchange Rates Service
        3. Create a client connection to the Notifications Service
        4. Write business logic for endpoints
        5. Write unit tests for endpoint which mock service clients.
    2. **gRPC**: In gRPC, a client application can directly call a method on a server application on a different machine as if it were a local object, making it easier for you to create distributed applications and services. 
        1. Performance: Compared with REST+JSON, gRPC offers up to 10x faster performance and API-security due to the Protobuf and HTTP/2
        2. Streaming: gRPC supports client- or server-side streaming semantics, which are already incorporated in the service definition. This makes it much simpler to build streaming services or clients. 
        3. Interoperability: gRPC tools and libraries are designed to work with multiple platforms and programming languages, including Java, JavaScript, Ruby, Python, Go, Dart, Objective-C, C#, and more. Due to the Protobuf binary wire format and efficient code generation for virtually all platforms, programmers can develop performant applications while still using full cross-platform support.



### Cmind Ai:
1. Agile team: 
   1. **Iterative, incremental, and evolutionary:** break product development work into small increments that minimize the amount of up-front planning and design. We keep developing our website for a period.
   1. **Efficient and face-to-face communication:** Team meeting every 2 days, all-hands meeting every Friday.
   1. **Very short feedback loop and adaptation cycle:** communicate with client and get feedback immediately. 
   1. Quality  focus
   1. DevOps: Slack, Figma, bitbucket
1. News trending / portfolio: 
   1. News trending: 
      1. Most frequently searched companies
      1. ![](Aspose.Words.6a1e1cca-c34a-4bbc-8754-f03af25aad03.005.png)**Parallel run several API request:** The **Promise.all()** method takes an iterable of promises as an input, and returns a single [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of the results of the input promises. This returned promise will resolve when all of the input's promises have resolved, or if the input iterable contains no promises. It rejects immediately upon any of the input promises rejecting or non-promises throwing an error, and will reject with this first rejection message / error. **This method can be useful for aggregating the results of multiple promises. It is typically used when there are multiple related asynchronous tasks that the overall code relies on to work successfully**
      1. Type a keyword, display the news change that related to the keyword in the line chart. Have a Tree system on the left side, from sector(Healthcare) -> industry(Drug Manufacturers General, Biotechnology) -> company, quick search company from **Tree System** -> display the news about that keyword and the target company
   1. Portfolio: 
      1. Add Target companies into portfolio, display detailed information such stock price change, market value change, 5 recent days news (optimize fetching speed)
      1. Notification function: 
1. Set Elastic search: 
   1. Configure the Java environment
   1. Install ElasticSearch on the digitalOcean
   1. Install logstash
   1. Connect with mongoDB
1. Optimized the backend searching Algo:
   1. Overwrite the fetching and sort query that featherJS provided: 7s -> 5s
   1. Used ElasticSearch to optimize: 5s -> 1.5s
1. featherJS: from my understanding, featherJS just like a backend framework help us to connect database, provide RESTful API to manage data
### Awesome Rush B:

**Self learn to follow the Agile Dev flow:**

1. Back end: **Springboot + mybatis + Mysql**
   1. POJO: User, Blog, Tag, Subscriber
   1. **Mapper** API: Communicate with MySQL database
   1. **DAO** API： Converting the data from the data source into Java POJO, and encapsulating. Provide accessor to the Services Layer.
   1. **Service** Layer: In charge of advanced business logic based on the DAO layer, provide mutual and reusable API to Controller. Like **findUserByID, update, findBlogByAuthor, findBlogByDate**
   1. **Controller Laye**r: Provide a restful API to frontend application/client based on the Service Layer.
   1. ![](Aspose.Words.6a1e1cca-c34a-4bbc-8754-f03af25aad03.006.png)
1. Front end: Figma + ReactJS + Node.js
   1. Semantic UI + material UI
   1. Auto self adaptive for PC end and mobile end
   1. Corporate with teammate to set JWT Token to authorize users login and logout.
   1. Retrieve data from backend API and display them in beautiful layout
1. Use **Terraform:**Terraform is a scripting tool used to automate the construction, management, and configuration of various products and services of cloud providers
1. Use **Packer**: Packer is an open source tool for creating identical machine images for multiple platforms from a single source configuration.
1. Github Action: CI/CD or CICD is the combined practices of [continuous integration](https://en.wikipedia.org/wiki/Continuous_integration) (CI) and either [continuous delivery](https://en.wikipedia.org/wiki/Continuous_delivery) or [continuous deployment](https://en.wikipedia.org/wiki/Continuous_deployment) (CD).
   1. **What is CI?**: Continuous integration (CI) is a software development strategy that increases the speed of development while ensuring the quality of the code that teams deploy. Developers continually commit code in small increments (at least daily, or even several times a day), which is then automatically built and tested before it is merged with the shared repository.
   1. **What is CD?:** Following the automation of builds and unit and integration testing in CI, continuous delivery automates the release of that validated code to a repository. 
### Online Pet Adoption Platform
1. Angualr vs React:
   1. **Angular:** [Angular](https://angular.io/) is a TypeScript-based, open-source front-end web application platform. It is an MVC framework created by Google. MVC is an architecture type for frameworks that develop user interfaces. It translates to Model View Controller.
   1. **React:** React is a declarative, efficient, and flexible JavaScript library for building user interfaces.
      1. Its component-based.
      1. Reusable Components,
      1. [Speed](https://www.peerbits.com/blog/reasons-to-choose-reactjs-for-your-web-development-project.html#Qlinks3)
      1. [Flexibility](https://www.peerbits.com/blog/reasons-to-choose-reactjs-for-your-web-development-project.html#Qlinks4)
      1. [Performance](https://www.peerbits.com/blog/reasons-to-choose-reactjs-for-your-web-development-project.html#Qlinks5)
      1. [Usability](https://www.peerbits.com/blog/reasons-to-choose-reactjs-for-your-web-development-project.html#Qlinks6)
      1. [Mobile app development](https://www.peerbits.com/blog/reasons-to-choose-reactjs-for-your-web-development-project.html#Qlinks7)
   1. Angular is a Javascript framework built using Typescript, while Reactjs is a Javascript library and built using JSX. Angular is mostly used to build complex enterprise-grade apps like single-page apps and progressive web apps, while React is used to build UI components in any app with frequently variable data. 

### Automated data analytics report process:
It is just implemented with Python, Cuz some of my colleagues don't have the foundation of coding, so for the data report and visualization, they just generated the chart by inputting the data into Excel manually, that definitely consumed too much time, So I just configure the Python for them, and import Numpy, pandas, and other chart libraries to write a script, all the things they need to do is just import the raw data files, and the code will automatic clean and filter and sort those data and generate chart for them.
