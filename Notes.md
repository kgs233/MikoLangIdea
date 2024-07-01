# Namespace?还是文件夹？或是说静态结构？
Namespace起到的作用是防止重名，而文件夹也可以做到这点，或许应该思考一下namespace的不同之处。  
namespace是对文件夹的高阶抽象，若要防止函数重名的话是有必要的。  
命名空间以外？  
Realspace，编译后的内容不加前缀，不可被声明为public。  
open是什么？  
open用于打开一个结构，也许namespace也是一个结构的抽象？那么为什么不用静态结构？  

不需要namespace，namespace很多余。  

那么Realspace是结构吗？  
不是，是代码集的空间，不是结构，应该只允许声明函数或者结构。  

open到一个标识符？  
可以，但是只能open到const中。  
```
const A = open Std.A;
```
那么为什么不直接  
```
const A = Std.A;
```
不不应该open到一个标识符  
应该open到define  
```
define A = Std.A;
```
似乎不需要open  
那么这样子  
```
define A = Std.A;

function ...
const ...
```
这样？将命名空间当作宏。  
的确可以。  
那么Realspace中不就有宏了？  
否决。  
那么还是回到上面的方案，在结构中声明pravite的const来open。  

# static的struct中应该有什么？
只应该有子结构，静态函数，const。  
不对，var也应该可以是静态的，不对，那么realsapce也是结构了。  
好，那么就让所有东西都可以在处处声明。

# Function与const在本质上相同
无需解释，相同，但是不会这么实现

# static的详解
static声明变量的长期性，但是这似乎不是个很好的抽象。  
static方便的使结构拥有可以直接被访问的值，也就是说static修饰的内容具有结构，也有值，但是没有标识符，或者说在定义结构时自动赋上值。

# 结构，量，标识符
任何程序中被定义的内容都可以被抽象为这三部分  
结构：即不可变的部分，有的语言中被称为类型，在miko中使用冒号赋值，且一次赋值就不可再变（动态结构除外）  
量：即可变部分，使用等号赋值。  
标识符：为结构与量取名字。  
命名结构：拥有标识符的结构。  
匿名结构：没有标识符的结构。  
变量：可变的量，在miko中一般指var
常量：量不可变的量，使用const声明。  

# 函数作为变量类型
```
function A(var Parm1 : Int32, var Parm2 : Int32)
{
  ...
}

var B : function(var Parm1 : Int32, var Parm2 : Int32);
B(1,2);

//have return
var C : function() : Int32;

//or

(1, 2) => B;
B();

//将函数作为量的类型
```
