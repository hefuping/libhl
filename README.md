libhl
=====

C library implementing a set of APIs to efficiently manage some basic data structures
such as : hashtables, linked lists, queues, trees, ringbuffers, red-black trees, priority queues, skip lists

The provided APIs are :

- hashtable.[ch]  :  一个线程安全的哈希表实现
- linklist.[ch]   :  线程安全的双链表 (with also a tag-based API)
- rbtree.[ch]     :  一个常规的红黑树实现
- fbuf.[ch]       :  Dynamically-growing flat buffers
- queue.[ch]      :  无锁线程安全的平面（动态增长）队列实现
- rqueue.[ch]     :  一个无锁线程安全循环（固定大小）队列实现 (aka: vaule-oriented ringbuffers)
- rbuf.[ch]       :  面向字节的环形缓冲区
- refcnt.[ch]     :  引用计数内存管理器
- binheap.[ch]    :  二项式堆实现 (building block for the priority queue implementation)
- pqueue.[ch]     :  优先级队列实现
- skiplist.[ch]   :  A skip list implementation
- graph.[ch]      :  一种通用图形实现，允许定义选择器函数来确定路径

Provided APIs typically don't depend on each other and can be simply included in an existing project by 
copying both the .c and the .h files plus, if necessary, bsd_queue.h and/or atomic_defs.h into the project sourcetree.

The only exceptions are:

- queue => depending on: refcnt
- pqueue => depending on: binheap
- graph => depending on: hashtable
