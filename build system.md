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
