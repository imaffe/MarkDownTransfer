## Java Object 类需要注意的点

#### hashcode

override equals() 方法必须也要override hashCode() 方法， 这个为了增加hash表的性能，并且 equals 为真hash一定相同，但是hash相同不一定equal

反例： hash 相同但是equal不成立的两个对象（似乎就是最简单的hahs的性质）

#### toString

#### java 多线程， wait， notify， notifyAll

#### finalize

在对象被垃圾回收之前调用





