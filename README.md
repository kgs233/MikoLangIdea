# Miko Language Idea
Miko 是一个正在构思中的编程语言，其名称取自日语“巫女（みこ）”如同汉字字面意思是巫女的意思，至于起这个名字原因是应为个人十分喜欢巫女属性（  
一个Hello World的设计感受下语法。
```
open Std.Type;
open Std.System.IO;

const main : func(Args : String[]) : Int32
{
    StdIO.Stdout("Hello World!");
    return 0;
}
```

# 这个语言的总目标
一门可控的，现代化的，语法优美且语义统一的编程语言。

## 可控的
层次可控，不单单的是low-level或high-level，而是uni-level。
语言规则可控，不局限于内存安全，类型安全，可见性，可访问性，而是让程序员选择是否应该去遵守这些规定。
繁简可控，语言指提供最基本的功能，且能够实现一切想要的功能，保证若能在库中实现的就不要将其放在语言中实现，让程序员自己选择是否使用一些会让代码复杂化的功能。

## 现代化
现代化的意思是他不是一门传统的like c的编程语言，在程序员愿意的情况下为程序员提供尽可能方便的功能（如GC，多范式，泛型，反射等），好的安全性和更快的开发速度。

## 语法优美与语义统一
语法符合程序员直觉，可阅读性强，但是不失代码该有的整洁性，一致性，使用明确的分隔符，尽可能的减少关键字数量，尽可能保证每个关键字只对应到一种含义，每个符号都对应到一种操作，将繁琐复杂的内容放置于标准库中，保证语言本身的简洁明了。

# 实现方式
使用LLVM作为语言基础框架，在编译器原型期采用c++作为编译器开发，原型可以正常使用后立刻进行自举。
有计划使这门语言直接可以调用c语言代码。

# 为什么要制作那么一门编程语言
第一原因是应为好玩，好玩乃是个人项目的第一动力。
第二呢则是我对现有语言的不满，我尝试过许许多多的语言，其中最让我感到满意的是c#，应为它足够强大，且有着一个强大的runtime：dotnet，但是应为过于high-level，在与low-level交互会遇到各种麻烦与问题，其次则是c，一门足够low-level的语言，语法十分简洁，写起来极其舒适，问题在于标准库没有那么的强大需要使用第三方库，而构建系统并没有那么好用（下面会提到）。

# 语言的灵感
首先来自于zig，zig的语言设计十分精妙，尤其是编译期特性，类型是一等公民，在与c的交互方面极为出色，但是问题在与过于低层次，以及语法的复杂与不美观。

然后则是D，这门语言我并没有实际的用过也并不是很了解，但是层次可控性的灵感来自于这门语言。

c，一门简洁强大的语言，极端的简洁性让我特别喜欢这门语言书写的程序。

c#，拥有一个极为强大的运行时与库，几乎你能想到的运行时与库都已经帮你做好。

Python，这是一个反例，让我知道了语法真正烂的语言应该是怎样的。

lua，可嵌入性与模块化很让我喜欢，但是语法并不是很喜欢，应为用到了end。

c++，一门很烂但是又出色的语言，完全的多范式灵感来源于它。

smalltalk，lisp，语义统一的灵感来自于这两门语言。

Ruby，程序员友好，现代化的目标来源于它。

rust，这个语言的复杂性让我意识到了可控性是多么重要。

除了xmake以外的所有构建系统，这些下面会提。

易语言，这只是单纯的想放上来，它敢于创新，也是我使用过的第一门编程语言。

# 关于构建系统
现有的构建系统都很垃圾（xmake可能要好一点），具体哪里垃圾我还需要构思一下（
