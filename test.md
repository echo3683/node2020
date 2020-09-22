“富函数”是DataStream API提供的一个函数类的接口，所有Flink函数类都有其Rich版本。它与常规函数的不同在于，可以获取运行环境的上下文，并拥有一些生命周期方法，所以可以实现更复杂的功能。
    RichMapFunction
    RichFlatMapFunction
    RichFilterFunction
 Rich Function有一个生命周期的概念。典型的生命周期方法有：
    open()方法是rich function的初始化方法，当一个算子例如map或者filter被调用之前open()会被调用。
    close()方法是生命周期中的最后一个调用的方法，做一些清理工作。
    getRuntimeContext()方法提供了函数的RuntimeContext的一些信息，例如函数执行的并行度，任务的名字，以及state状态

**selectExpr**

**可以对指定字段进行特殊处理**
　　可以直接对指定字段调用UDF函数，或者指定别名等。传入`String`类型参数，得到DataFrame对象。
　　示例，查询`id`字段，`c3`字段取别名`time`，`c4`字段四舍五入：()

<img src="test.assets/image-20200922210812139.png" alt="image-20200922210812139" style="zoom:50%;" />

llal