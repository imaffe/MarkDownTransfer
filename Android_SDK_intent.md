## 讲一下Android里面的Application以及各个组件的执行，部分intent的内容

``` java
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        // 微信事件回调接口注册
        MyApplication.sApi.handleIntent(getIntent(), this);
    }
```

以上就是示例代码的部分，

#### 第一个问题：MyApplication为什么作用域可以到interface里面去呢

如果MyApplication是一个singleton的话（它的所有成员变量都是static的)，单例在包种的作用范围应该是怎样的呢？解释：在Android开发中，Application本身就是全局单例的，所以无需设置单例保护，并且Application的生命周期是整个app，所以没有采用常见的单例模式的写法，application本身需要去注册到AndroidManifest文件中去，不过这里又有另外一个问题了，为什么一个lib里面会有一个Application呢？如果没有的话会发生什么呢？