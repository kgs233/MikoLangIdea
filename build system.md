# 构建系统
名称：sando（参道（さんどう）去掉u），在神社建筑中用于连接神社各个部分的路，符合构建系统意境。  

# sando core
一个通用的元构建系统，目标是通用，简单，易于生成的语法。
```
project Test
version 0.0.1
sandov 0.0.1
--
CC=gcc
CXX=g++
--
@CC:
    #$(CC) &(1) -o &(2)
@CXX:
    #$(CXX) &(1) -o &(2)
--
@target build:
    @CC main.c main.out

@target clean:
    #rm main.out

# 此外还包括内置函数@include，@goto，@sub，@deftarget
```

# sando
Miko语言的构建系统，使用miko script书写构建逻辑，当然在拓展之后可以为其它语言使用。
具体正在构思。

# 包管理器 ema
絵馬（えま），是在神社中由参拜者许愿的工具，由用户自己书写符合包意境。
包管理器当然也应该是通用的（当然这很难），还是一样的目标：简单，通用，构建快速。
