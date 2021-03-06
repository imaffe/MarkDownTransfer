

## Java Interface : 接口的常见用法

#### 为什么可以在类中定义接口

首先我们需要知道为什么 java 要支持嵌套定义，肯定和类中定义类有关，以及我们java是怎样实现这样的代码的，在作用域，包的上下文里又是怎样的。

#### Java 嵌套/内部类

[IBM 嵌套类](https://www.ibm.com/developerworks/cn/java/j-perry-nested-classes/index.html)的讲解也非常的详细了，

- 内部类仍然是一个独立的类，在编译之后内部类会被编译成独立的.class文件，但是会冠上外部类的类名，（内部类，是不是某些情况下只有定义了内部类的才能用这个类，但是在外部类之外能够创建内部类的实例嘛？）

- 有个文章有这么一句话，我感觉其中有一些错误，经过查证之后有这么几个说法

  >     1.对于内部类，通常在定义类的class关键字前不加public 或 private等限制符，若加了没有任何影响。
  >     2.内部类中可以直接访问外部类的数据成员和方法。
  >     3、另外，就是要注意，内部类Inner及InnterTwo只在类Outer的作用域内是可知的，如果类Outer外的任何代码尝试初始化类Inner或使用它，编译就不会通过。同时，内部类的变量成员只在内部内内部可见，若外部类或同层次的内部类需要访问，需采用示例程序中的方法，不可直接访问内部类的变量。

#### Java 中的接口声明对象

这个问题回答了为什么 可以看似创建一个接口的“实例” ``` public CallBack mCallBack;```, 实际上这是一个声明对象，其实这里可以看成创建了一个 抽象类的 reference，本身并不会绑定到任何实例，只有当某个具体的类实现了这个接口的时候，可以通过多态性调用这个 声明的变量去实际访问实际被完成了的类的成员（就像是c++ 中声明了一个 ``` Base * ptr;``` 之后会用这个ptr指向一个derived 对象，从而访问那个对象，称之为父类引用指向子类对象）

- 这又引入了一个问题，Java中是怎么区分引用的值的呢？我怎么知道我当前的变量是一个引用还是一个确实存在的值呢？

