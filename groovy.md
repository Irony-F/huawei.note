



## 一、基本语法

1.默认情况下groovy包含java的基本库，不需要手动导入。

2.变量名遵循java命名规则。

3.基本数据类型：byte，short，int，long，float，double等

4.打印同java

## 二 、语法



1.每行结尾可以无分号；
2.定义  def
		·变量 `def a=1`
		·字符串 `def b="string"`
		·double def double c=1.0
		·函数,如果指定了返回类型则不需要def,如果不设置返回值的话，函数里最后一句代码的执行结果被执行成返回值。函数调用可以不加括号。
		

~~~groovy
		def func(){}
		
		def func1(def1,def2){
			}
		
		String func2(def1)
		{	return "返回值"
		}
		
		def func3(){
			````
			1000	
		}
~~~


​		调用：
	

```groovy
		func1(s1,s2)
		func s3
```

4.断言 assert ()

​	如果断言中的参数为假，则系统推出，并输出一套错写信息；如果为真，则继续执行代码。

5.循环

​	a.while

​	b.for

​	c.for-in，可以用来循环map

```groovy
for(int i in 1..5){
	println(i)
}

//map
def employee=["ken":21."John":25,"Sally":22];

for(emp in employee)
{	println(emp);	
}
```

​	d.upto 和downto

```groovy
//upto downto
1.upto(3){println it}
3.downto(1){println it}
```

​	e.times的方法

​        `3.times{ println it}` 

​	输出从0开始到2      

​	f.step

​	 `1.step(7,2){println it}`

​	从1开始到7之前，每次递增2。 小于7.

​	

6.字符串

​	·单引号''，其中的内容严格对应java的string，不对符号进行计算处理。
	·双引号""，其中的内容和脚本相似，若存在特殊的计算符号，会进行相应的转义。
	·三引号'''    '''，支持内容的随意换行，内容中保存换行符。

7.容器：range,是list的拓展。可以使用   x..y标识从x到y的区间，其顺序可憎可减。

​	其中常用的函数：

​		

```groovy
getFrom() //获取下限
getTO() //获取上线
isReverse() //反向范围，反向迭代
last()  	//最后一个元素

```



8.链表list  []

​	 常用函数：

``` groovy
isEmpty()	//如果列表为空，返回true
add()	//填在末尾
pop()	//移除末尾
remove() //删除指定元素
size() 	 //返回
sort()	//排序
```

9.映射map

def map =['tcp':'tcp','ip':'ip'];

函数：



```
get() 参数为key，返回值为value
keyset() 获取一组key
put() 将指定的值与此映射中的指定键相关联。如果此映射先前包含此键的映射，则旧值将替换为指定的值。
values() 返回map中的集合视图
```

10.闭包。类似指针数组。

​	格式：{   参数 ->操作}	其中参数可选

​	调用：	·对象名.call（参数）  

​		 	·对象名（参数）

​	注意事项：

​		·对于有参数的闭包，在调用时参数可选；对于没有参数的闭包，调用时一定不能有参数。

​		·如果闭包没有定义参数，则有一个隐藏参数it。类似this，代表闭包的参数。定义在闭包所在类的一个嵌套对象，值得是最上层的类。

​		

```groovy
	[1,2,3,4].each{
        println(it)
	}
```

​		因此在闭包只有一颗参数的时候，可以省略，使用it代替。

```
	def doubing={a -> println a*2}
	[1,2,3,4].each{
		doubing(it)
		}
	
	//等于


```

​		·调用函数时，如果函数的最后一个参数是闭包，则不需要写括号。

12.闭包和each

​	闭包中的each函数循环可以用于遍历list，但是each不支持break和continue，当需要在遍历时中途退出，可以使用find或直接使用java的for。



13.groovy为 数字类型提供一种更简单的声明类型的方式：类型后缀。

```
- Integer 使用I或i
- Long 使用L或l
- BigInteger 使用G或g
- BigDecimal 使用G或g
- Double 使用D或d
- Float 使用F或f
```

