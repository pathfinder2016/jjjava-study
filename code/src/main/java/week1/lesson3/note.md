# 函数都是在JVM中只有一份的
不管函数是不是被定义为static

# 关于static函数里不能用this
因为非static函数在调用时, 本质上把函数所在的对象当成其中一个参数this穿进去了, 比如:

```java
public void fn(int a, int b) {
	//...
}
```
在这样调用: `obj.fn(1, 2);` 时:
```java
public void fn(Object this, int a, int b) {
	// this = obj, a = 1, b = 2
}
```

# 最后字符串的例子
主要是看某个token右边的赋值表达式是否能够在编译器被计算出结果, 也就是编译器常量, 如果是的话, 就会放到JVM的 MetaData 区, 字面量相同的
字符串常量全局只会保存一份, 所以有些能用 == 比较的结果为 true.