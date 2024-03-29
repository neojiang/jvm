    Java虚拟机在执Java程序的过程会把所管理的内存分为不同的区域管理。
    如图有方法区，堆，虚拟机栈，本地方法栈，程序计数器5个部分组成。
    其中，方法区和堆是线程共享的；虚拟机栈，本地方法栈，程序计数器是线程隔离的。
![image](https://github.com/neojiang/study/blob/master/%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3Java%E8%99%9A%E6%8B%9F%E6%9C%BA/img/Java%E5%86%85%E5%AD%98%E6%A8%A1%E5%9E%8B%E5%9B%BE.png)

### 程序计算器

    1、程序计数器(Program CounterRegister) 是一块较小的内存空间,作用是当前线程所执行的字节码的行号指示器. 
       在虚拟机的概念模型里, 字节码解释器工作时就是通过改变这个计数器的值来选去下一跳需要执行的字节码指令, 
       分支, 循环, 跳转, 异常处理, 线程恢复等基础功能都需要依赖这个计数器来完成.

    2、由于Java虚拟机的多线程是通过线程轮流切换并分配处理器执行时间的方式来实现的, 在任何一个确定的时刻,
       一个处理器(对于多核处理器来说是一个内核) 只会执行一条线程中的指令.因此, 为了线程切换后能恢复到正确的
       执行位置, 每条线程都需要有一个独立的程序计数器, 各条线程之间的计数器互不影响, 独立存储, 
       我们称这类内存区域为"线程私有内存".

    3、如果线程正在执行的是一个Java方法, 则计数器记录的是正在执行的虚拟机字节码指令的地址; 
       如果正在执行的是Native方法, 这个计数器值则为空(Undefined). 

    4、此内存区域是唯一一个在Java虚拟机规范中没有规定任何OutOfMemoryError情况的区域.
