## Visa VO 总结

* [X] 比如通常map的实现方法、优劣，初始 capacity 的设置，什么时候应该拓展bucket的数量，rehash的方法 & 触发条件
* [ ] implement any sorting algorithm
* [X] hashmap和hashset的区别，他们的retrieve的time complexity 分别是什么
* [X] java和其他语言的区别（java's feature）
* [X] 问了一堆Java的问题，JVM是什么，组成成份是什么，怎么工作的，Java程序是怎么run起来的，内存如何分配和管理，GC是怎么工作的等等
* [X] Java 8 的lamda是否会写，如果会，会让你写个函数
* [X] System.out.println()是如何运行的，这个out不是个static class，大家查一下，System是
* [X] HashMap:

  * [X] HashMap的知识，put操作在已有的key上会发生什么？是否可以有null，我记得允许一个null
  * [X] HashMap的基础用法
* [ ] database, sql
* [ ] ood(ATM)
* [ ] OOD: design a bookshelf 需要有bookeshelf， shelf, book这3个class，每个都有size的信息等
* [ ] post & get
* [ ] 刷题:

  * [X] same tree
  * [X] 3
  * [X] subtree
  * [ ] 253 只不过问题变为给了一堆人从出生到死亡的时间，问到今天还有几人活着
  * [X] 217 **高频** visa有一题高频题，利口217， 找kth大element，我觉得最后可能会让你implement quick select的做法，所以大家要掌握1. sort 2. max heap 3. min heap 4.quickselect 以上四种
  * [X] 384 第一题是把一个party上的所有guest给randomly排序，list of string，打乱顺序输出
  * [X] 蠡口 叁拾叁 不同的是在rotate sorted array里面找最大值，而不是index，用二分查找
  * [x] trapping rain water
  * [X] 3 Longest Substring Without Repeating Characters
  * [X] 给定一个数组[2, 3, 5, 7]代表每个step的price，每次可以爬一个step或2个steps，问爬到最后一个阶梯最小的price
    其实就是一个简单的dp，写出来之后她说不需要一个array，我说对，只决定于前2个数，所以用2个变量就可以了
  * [ ] 最后做了一个题，给一个链表，里面只有1和0，输出链表代表的二进制数，太简单了
  * [ ] 一个String "abcad"，输出 "abcd"，也就数输出一个新的String，不包含重复字符，太简单了，一个set和StringBuilder就行了
  * [ ] 一个IP "127.0.0.1" 输出"127001"，也就是跳过所有"."，更简单，一个StringBuilder结束
  * [ ] 给定一个数组[1, 19, 27‍‍‍‌‌‍‌‌‍‌‍‍‍‌‌‌‍‌‌, 3]拼接组成最大数32719，这个很简单，我直接转成String[]，然后sort，用StringBuilder从后往前加。其实当然不需要转了，自己写一个数组的比较器也可以。
* [ ] SQL:

  * [ ] 一个是如何找duplicate record
  * [ ] 一个是找工资最高的员工。


## OOD

### 5C:

- Clarify
- Core Objects
- Cases
-

## 刷题

### [445. Add Two Numbers II](https://leetcode.com/problems/add-two-numbers-ii/)

No Reverse Linkedlist，use 2 stacks -> calculate and reconstruct the res LinkedList

### [215. Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array/)

1. Sort -> TC: O(NlogN), SC: O(logN)递归调用栈的高度
2. Quick Select -> TC: O(N), SC: O(1) 因为没有用recursion
3. PriorityQueue -> TC: O(NlogK) 遍历元素N，堆内元素调整logK, SC: O(k);

## Java's feature

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

## System.out.println()

**System.out.println()** is used to print an argument that is passed to it. The statement can be broken into 3 parts which can be understood separately as:

1. **[System](https://www.geeksforgeeks.org/java-lang-system-class-java/):** It is a final class defined in the [java.lang package](https://www.geeksforgeeks.org/java-lang-package-java/). ![](https://images2015.cnblogs.com/blog/739525/201601/739525-20160119185727687-1621310018.png)
2. **out:** This is an instance of **[PrintStream](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** type, which is a public and static member field of the [System class](https://www.geeksforgeeks.org/java-lang-system-class-java/). ![](https://images2015.cnblogs.com/blog/739525/201601/739525-20160119190442328-550264769.png)
3. **[println()](https://www.geeksforgeeks.org/difference-between-print-and-println-in-java/):** As all instances of **[PrintStream class](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/)** have a public method println(), hence we can invoke the same on out as well. This is an upgraded version of print(). It prints any argument passed to it and adds a new line to the output. We can assume that System.out represents the Standard Output Stream. ![](https://images2015.cnblogs.com/blog/739525/201601/739525-20160119191040250-1798193938.png)

## Lambda

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

## JVM

JVM (Java Virtual Machine) is an abstract machine. It is a specification that provides runtime environment in which java bytecode can be executed.

![](https://www.guru99.com/images/1/2.png)

### Method Area

Method Area is a part of the heap memory which is shared among all the threads. It creates when the JVM starts up. It is used to store class structure, superclass name, interface name, and constructors. The JVM stores the following kinds of information in the method area:

- A Fully qualified name of a type (ex: String)
- The type's modifiers
- Type's direct superclass name
- A structured list of the fully qualified names of super interfaces.

### Heap Area

Heap stores the **actual objects**. It creates when the JVM starts up. The user can control the heap if needed. It can be of fixed or dynamic size. When you use a new keyword, the JVM creates an instance for the object in a heap. While the reference of that object stores in the stack. There exists only one heap for each running JVM process. When heap becomes full, the garbage is collected. For example:

`StringBuilder sb= new StringBuilder();`

The above statement creates an object of the StringBuilder class. The object allocates to the heap, and the reference sb allocates to stack. Heap is divided into the following parts:

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

### JVM Language Stack

The stack is a part of memory that contains information about nested method calls down to the current position in the program. It also contains all local variables and references to objects on the heap defined in currently executing methods.

This structure allows the runtime to return from the method knowing the address whence it was called, and also clear all local variables after exiting the method. Every thread has its own stack.

Stack memory is responsible for holding references to heap objects and for storing value types (also known in Java as **primitive types**), which hold the value itself rather than a reference to an object from the heap.

### Native Method Stack

It is also known as C stack. It is a stack for native code written in a language other than Java. Java Native Interface (JNI) calls the native stack. The performance of the native stack depends on the OS.

### PC Registers

Each thread has a Program Counter (PC) register associated with it. PC register stores the return address or a native pointer. It also contains the address of the JVM instructions currently being executed.

程序计数器是一个比较小的内存区域，可能是CPU寄存器或者操作系统内存，其主要用于指示当前线程所执行的字节码执行到了第几行，可以理解为是当前线程的行号指示器。字节码解释器在工作时，会通过改变这个计数器的值来取下一条语句指令。 每个程序计数器只用来记录一个线程的行号，所以它是线程私有（一个线程就有一个程序计数器）的。

如果程序执行的是一个Java方法，则计数器记录的是正在执行的虚拟机字节码指令地址；如果正在执行的是一个本地（native，由C语言编写完成）方法，则计数器的值为Undefined，由于程序计数器只是记录当前指令地址，所以不存在内存溢出的情况，因此，程序计数器也是所有JVM内存区域中唯一一个没有定义OutOfMemoryError的区域。

## Working of Garbage Collector

### Garbage Collector Overview

When a program executes in Java, it uses memory in different ways. The heap is a part of memory where objects live. It's the only part of memory that involved in the garbage collection process. It is also known as garbage collectible heap. All the garbage collection makes sure that the heap has as much free space as possible. The function of the garbage collector is to find and delete the objects that cannot be reached.

### Minor Gc和Full GC 有什么不同呢?

大多数情况下，对象在新生代中 eden 区分配。当 eden 区没有足够空间进行分配时，虚拟机将发起一次Minor GC。新生代GC(Minor GC):指发生新生代的的垃圾收集动作，Minor GC非常频繁，回收速度一般也比较快。

老年代GC(Major GC/Full GC):指发生在老年代的GC，出现了Major GC经常会伴随至少一次的Minor GC(并非绝对)，Major GC的速度一般会比Minor GC的慢10倍以上。

### Types of Garbage Collection

There are five types of garbage collection are as follows:

* **Serial GC:** It uses the mark and sweeps approach for young and old generations, which is minor and major GC.
* **Parallel GC:** It is similar to serial GC except that, it spawns N (the number of CPU cores in the system) threads for young generation garbage collection.
* **Parallel Old GC:** It is similar to parallel GC, except that it uses multiple threads for both generations.
* **Concurrent Mark Sweep (CMS) Collector:** **It does the garbage collection for the old generation. You can limit the number of threads in CMS collector using** **XX:ParalleCMSThreads=JVM option** . It is also known as Concurrent Low Pause Collector.
* **G1 Garbage Collector:** It introduced in Java 7. Its objective is to replace the CMS collector. It is a parallel, concurrent, and CMS collector. There is no young and old generation space. It divides the heap into several equal sized heaps. It first collects the regions with lesser live data.

### Mark and Sweep Algorithm

JRockit JVM uses the mark, and sweep algorithm for performing the garbage collection. It contains two phases, the mark phase, and the sweep phase.

**Mark Phase:** Objects that are accessible from the threads, native handles, and other GC root sources are marked as live. Every object tree has more than one root objects. GC root is always reachable. So any object that has a garbage collection root at its root. It identifies and marks all objects that are in use, and the remaining can be considered garbage.

![Memory Management in Java](https://static.javatpoint.com/core/images/memory-management-in-java2.png)

**Sweep Phase:** In this phase, the heap is traversed to find the gap between the live objects. These gaps are recorded in the free list and are available for new object allocation.

There are two improved versions of mark and sweep:

* **Concurrent Mark and Sweep**
* **Parallel Mark and Sweep**

#### Concurrent Mark and Sweep

It allows the threads to continue running during a large portion of the garbage collection. There are following types of marking:

* **Initial marking:** It identifies the root set of live objects. It is done while threads are paused.
* **Concurrent marking:** In this marking, the reference from the root set are followed. It finds and marks the rest of the live objects in a heap. It is done while the thread is running.
* **Pre-cleaning marking:** It identifies the changes made by concurrent marking. Other live objects marked and found. It is done while the threads are running.
* **Final marking:** It identifies the changes made by pre-cleaning marking. Other live objects marked and found. It is done while threads are paused.

#### Parallel Mark and Sweep

It uses all available CPU in the system for performing the garbage collection as fast as possible. It is also called the parallel garbage collector. Threads do not execute when the parallel garbage collection executes.

**Pros of Mark and Sweep**

* It is a recurring process.
* It is an infinite loop.
* No additional overheads allowed during the execution of an algorithm.

**Cons of Mark and Sweep**

* It stops the normal program execution while the garbage collection algorithm runs.
* It runs multiple times on a program.

## Java创建对象的过程

![](https://markpersonal.oss-us-east-1.aliyuncs.com/pic/20220106160142.png)

## Java Collection Time Complexity

### List

#### ArrayList

get() 直接读取下标，复杂度 O(1)
add(E) 直接在队尾添加，复杂度 O(1)
add(index, E) 在第n个元素后插入，n后面的元素需要向后移动，复杂度 O(n)
remove() 删除元素后面的元素需要逐个前移，复杂度 O(n)

#### LinkedList

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

### Set

#### HashSet

add() 复杂度为 O(1)
remove() 复杂度为 O(1)
contains() 复杂度为 O(1)

#### TreeSet（基于红黑树）

add() 复杂度为 O(log (n))
remove() 复杂度为 O(log (n))
contains() 复杂度为 O(log (n))

### map

#### TreeMap（基于红黑树）

平均时间复杂度 O(log n)

#### HashMap

正常时间复杂度 O(1)~O(n)
红黑树后 O(log n)

#### LinkedHashMap

能以时间复杂度 O(1) 查找元素，又能够保证key的有序性

## HashMap, HashTable, HashSet

### 说说 List,Set,Map 三者的区别?

- List (对付顺序的好帮手): 存储的元素是有序的、可重复的。
- Set (注重独一无二的性质): 存储的元素是无序的、不可重复的。
- Map (用 Key 来搜索的专家): 使用键值对(kye-value)存储，类似于数学上的函数 y=f(x)，“x”代表 key，"y"代表 value，Key 是无序的、不可重复的，value 是无序的、可重复的，每个键最多映射到一个值。

### HashMap 详解

- inherits(implement) from Map interface
- 底层：

  - JDK1.8之前：数组 + 链表
  - JDK1.8之后：数组 + 链表 + 红黑树，链表长度 > 8时转化为红黑树
- 初始化默认大小16，必须是2的整数次幂(the integer power of 2)
- 最大容量:必须是2的整数次幂且小于2^30
- load factor 负载因子 默认 0.75 当元素数量大于capacity * load factor的时候，扩容 -> *2
- ![](https://zeral.cn/images/java/hashmap/tradeoff-time-space.png)
- ![](https://zeral.cn/images/java/hashmap/hashmap-1.8.png)

### HashMap vs HashTable

#### Thread Safe

HashMap is non-synchronized. It is not thread-safe and can’t be shared between many threads without proper synchronization code whereas Hashtable is synchronized. It is thread-safe and can be shared with many threads.

HashMap is generally preferred over HashTable if thread synchronization is not needed

#### key -> Value

HashMap allows one null key and multiple null values whereas Hashtable doesn’t allow any null key or value -> `NullPointerException`.

#### 初始容量大小和扩容

创建时如果不指定容量初始值，Hashtable 默认的初始大小为 11，之后每次扩充，容量变为原来的 2n+1。

HashMap 默认的初始化大小为 16。之后每次扩充，容量变为原来的 2 倍。

创建时如果给定了容量初始值，那么 Hashtable 会直接使用你给定的大小，而 HashMap 会将其扩充为 2 的幂次方大小(HashMap 中的 tableSizeFor() 方法保证，下面给出了源代码)。也就是说 HashMap 总是使用 2 的幂作为哈希表的大小,后面会介绍到为什么是 2 的幂次方。

#### 底层数据结构

HashMap : JDK1.8 之前 HashMap 由数组+链表组成的，数组是 HashMap 的主体，链表则是主要为了解决哈希冲突而存在的(“拉链法”解决冲突)。JDK1.8 以后在解决哈希冲突时有了较大的变化，当链表⻓度大于阈值(默认为 8)(将链表转换成红黑树前会判断，如果当前数组的⻓度小于64，那么会选择先进行数组扩容，而不是转换为红黑树)时，将链表转化为红黑树，以减少搜索时间

JDK1.8 以后的 HashMap 在解决哈希冲突时有了较大的变化，当链表⻓度大于阈值(默认为 8)(将链表转换成红黑树前会判断，如果当前数组的⻓度小于 64，那么会选择先进行数组扩容，而不是转换为红黑树)时，将链表转化为红黑树，以减少搜索时间。Hashtable 没有这样的机制。

### Hashmap vs HashSet

如果你看过 HashSet 源码的话就应该知道:HashSet 底层就是基于 HashMap 实现的。(HashSet 的源码非常非常少，因为除了 clone() 、 writeObject() 、 readObject() 是 HashSet 自己不得不实现之外，其他方法都是直接调用 HashMap 中的方法。

HashSet is an implementation of Set Interface which does not allow duplicate value.

HashMap internally uses a hashing method to store the elements. On the other hand, the HashSet uses the HashMap object to store or add the elements.

![](https://img2018.cnblogs.com/blog/1265453/202002/1265453-20200222231738458-1252225000.png)

### HashSet如何检查重复

compute the object's hashcode -> determine where to add / compare with other's hashcode

- if not -> add
- if duplicate -> 这时会调用 equals() 方法来检查 hashcode 相等的对象是否真的相同 -> false

# Simple Max Difference

![](https://oss.1point3acres.cn/forum/202109/30/193114k689w91u6t90x8p9.jpg)

```java
    private static int maxDiff(int[] arr){
        int diff = arr[1] - arr[0];
        int minElement = arr[0];
        for(int i = 1; i < arr.length; i++){
            if(arr[i] - minElement > diff){
                diff = arr[i] - minElement;
            }
            if(arr[i] < minElement){
                minElement = arr[i];
            }
        }
        return diff > 0 ? diff : -1;
    }
```

# [Maximal Square](https://leetcode.com/problems/maximal-square/)

```java
class Solution {
    public int maximalSquare(char[][] matrix) {
        int maxSide = 0;
        int m = matrix.length;
        int n = matrix[0].length;
        if(matrix == null || m == 0 || n == 0){
            return 0;
        }
        int[][] dp = new int[m][n];
        for(int i = 0; i < m; i++){
            for(int j = 0; j < n; j++){
                if(matrix[i][j] == '1'){
                    if(i == 0 || j == 0){
                        dp[i][j] = 1;
                    }else{
                        dp[i][j] = Math.min(Math.min(dp[i - 1][j], dp[i][j - 1]), dp[i - 1][j - 1]) + 1;
                    }
                    maxSide = Math.max(maxSide, dp[i][j]);
                }
            }
        }
        return maxSide * maxSide;
    }
}
```

```java
class Solution {
    public int maximalSquare(char[][] matrix) {
        int maxSide = 0;
        int m = matrix.length;
        int n = matrix[0].length;
        if(matrix == null || m == 0 || n == 0){
            return 0;
        }
        for(int i = 0; i < m; i++){
            for(int j = 0; j < n; j++){
                if(matrix[i][j] == '1'){
                    maxSide = Math.max(maxSide, 1);
                    int curMaxSide = Math.min(m - i, n - j);
                    for(int k = 1; k < curMaxSide; k++){
                        boolean flag = true;
                        if(matrix[i + k][j + k] == '0'){
                            break;
                        }
                        for(int b = 0; b < k; b++){
                            if(matrix[i + k][j + b] == '0' || matrix[i + b][j + k] == '0'){
                                flag = false;
                                break;
                            }
                        }
                        if(flag){
                            maxSide = Math.max(maxSide, k + 1);
                        }else{
                            break;
                        }
                    }
                }
            }
        }
        return maxSide * maxSide;
    }
}
```
