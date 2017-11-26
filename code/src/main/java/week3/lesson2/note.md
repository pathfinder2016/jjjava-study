# Week3-2 深入理解函数调用（下）

# 关于swap函数如果传入Reference的问题
因为即使传入Reference的话, 拷贝了一份Reference作为Local变量,
通过这个Local变量作为指针也是可以找到堆中准确的对象, 所以可以交换对象的属性的值.

但是并不能交换对象本身:

即变成a -> A(2), b -> A(1). 本质上是因为a和b是被拷贝了一份的, 是值传递, 改变栈帧中的值并不影响外层函数里的值.


