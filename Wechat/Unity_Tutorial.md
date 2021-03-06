- 如何声明 Java 的单例类

  - 通过在类中创建该变量，只提供返回这个单例的方法（接口），具体实现要注意线程安全。

- Unity的AndroidJavaClass是怎么通过路径访问到那个包的？

  - 似乎就是 放在指定目录下，然后指定包名中的类名就可以访问了

- Java  的 Object 类非常重要 可以深入看一下java的Object 类都是怎么实现的

  - 见 java/java_object.md

- 为什么Unity可以用"currentActivity"关键字来找到我要用的包

  - 见下文 链接处， 下一个问题同理

- 为什么是GetStatic的方式得到currentActivity(static 就是单例的意思嘛？)

  - 因为currentActivity是一个UnityPlayer的静态成员变量

- 那么在Java Class中是不是static的方法用 CallStatic来操纵呢？

- Android 的操纵手机存储的API

- Native 关键字究竟是什么意思（为啥还有动态库的实现方式呢？）

  - Java用native表明这段代码用其他代码实现的。

- Java的标记接口是什么意思？ 没有任何关于方法的声明嘛?

  - 没有任何方法和属性的接口，仅仅表明它的类属于一个特定的类型，常常用instance of

- Java的类对象 ： 每个类是Class 类的实例？java的运行时类对象，object对象的类对象

  - Java 的 Class class 对象， 每个type 都是 Class 类的一个实例（void int double 等等） 不过可以走进去看看这个 Class类定义了哪些接口。

- Java的包究竟是什么东西?

  - 把类组织到包中，一是方便命名空间的识别

- Java的sychronized关键字是干什么用的？Throw 关键字呢

- JNI 又是什么东西呢？

  - JNI就是 java native interface 使得java可以调用本地的应用或者库，非常的给力

- delete 代理 动态代理又是些什么东西？

- AndroidJavaProxy的internal 关键字声明又是干什么的

  ```  java  
  package demo;
  
  interface PlayStateListener {
    void onBufferFinished(SongInfo songInfo);
    void onBufferProgress(String songId, long buffered, long total);
  }
  ```



  ``` c# 
  class PlayStateChangedHandler : AndroidJavaProxy {
    internal PlayStateChangedHandler() : base(new AndroidJavaClass("demo.PlayStateListener")) {}
    public void onBufferFinished(AndroidJavaObject songInfoObject) {}
    public void onBufferProgress(string songId, long buffered, long total) {}
  }
  ```



- 有空可以看一下 Android 的 自动化构建 Android Demo Unity Bridge的实现。写gradle文件
- Java 的反射又是 什么东西？
- Unity 的player 是什么东西， Unity 的 UnityPlayer 又是什么东西？ 为什么可以通过这个访问到安卓
  - UnityPlayer 是一个专门的对象， currentActivity是 其中的一个静态成员变量，getStatic似乎对很多java类都有用
  - [详细解释](https://blog.csdn.net/yang8456211/article/details/51331358)
  - 似乎还和反射有一定的关系，可以继续查找反射发生了什么
- 元数据又是什么呢？
- javac 是干什么的来着？constant pool 又是干什么的？
- java 为什么 不给每个平台写专门的编译器（既然可以JIT编译了）
  - 事实上是可以的，现行的JVM 会选择解释执行某些代码，而不全部编译的原因在于：很多手机引用受限于磁盘大小，太多的应用程序会占用固有的空间。
- android 应用程序是运行在JVM嘛？
  - 会有Msbuild等类似的东西转换成DVM bytecode变成 dex然后执行
- 为什么MyApplication里的api可以传给IWXAPIEventHandler呢？ 我们能看到getIntent的是什么东西嘛？为什么要把这个函数传到handleIntent里面去呢？这个是只在初始化的时候被调用了嘛？
- 什么是 返回code的回调接口， 为什么把一个接口传给函数 作为参数呢？
- 什么是类中的类，或者类中的接口？
- 需不需要更改到wxapi文件夹目录下面去呢？
- 什么是事件回调接口注册？
- new WeChatCode() {} 这个声明到底干了什么事情呢？
- 这个应用里的Android Application 有什么用？ 是singleton嘛？这个Application在什么时候被初始化呢？
- initWeiXin干了什么事，授权域应该怎么写？
- Java 静态方法不能直接访问非静态成员
- new WXEntryActivity.WeChatCode() 创建了一个 接口的实例？为什么有一个 mWeChatCode 的public static 变量在这个类里面呢？（[教程里是说一个成员变量](https://www.ibm.com/developerworks/cn/java/j-perry-nested-classes/index.html)）
  - 这里其实是 创建了一个 接口的引用（可以把接口类似于一个抽象类），这个引用并没有绑定到任何实例，但是之后会被绑定到一个子类实例上从而实现多态。
- 这又引入了一个问题，Java中是怎么区分引用的值的呢？我怎么知道我当前的变量是一个引用还是一个确实存在的值呢？看一下Java中的4种引用类型
- Unity 出现 NoClassDefFoundError 是什么个意思呢？有没有更好的调试方法呢？
- 现在要做的事情，如何把code给拿出来，它本身给我的接口没有一个存储code的地方，我是要更改一下那个接口呢？还是要做点别的事情呢？
- 为什么在外部类之外创建一个内部类的实例，这个实例可以有成员变量嘛？如果可以有的话，能在外面访问嘛？
- Java 的Classpath是干什么的？