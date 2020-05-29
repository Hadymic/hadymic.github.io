---
title: Hello World
tags:
  - Markdown
index_img: >-
  https://t8.baidu.com/it/u=2247852322,986532796&fm=79&app=86&size=h300&n=0&g=4n&f=jpeg?sec=1591262865&t=f9199846e0b9a93054f9e1a23dd94be3
top: true
hide: true
abbrlink: 4a17b156
date: 2020-05-28 18:00:00
---

这里是摘要

<!--more--> #首先这是一个摘要分割符
#这是一级标题
##这是二级标题
###这是三级标题
####这是四级标题
...
![图片详情](url "{图片占位符}")    #这是放置一个图片

- [ ] 任务一 未做任务 `- + 空格 + [ ]`
- [x] 任务二 已做任务 `- + 空格 + [x]`    #这是服务列表
&nbsp;    #设置缩进之一个空格

*斜体*或_斜体_
**粗体**
***加粗斜体***
~~删除线~~
++下划线++
==背景高亮==

超链接还是<a href=""></a>比较好用

我经常去的几个网站[Google][1]、[Leanote][2]。    #参考链接

[1]:http://www.google.com
[2]:http://www.leanote.com

使用 Markdown[^1]可以效率的书写文档, 直接转换成 HTML[^2]。    #注脚/引用来源

[^1]:Markdown是一种纯文本标记语言

[^2]:HyperText Markup Language 超文本标记语言

## 0. 目录    #描至页面的其他部分

* 无序列表项 一    #无序列表
+ 无序列表项 二
- 无序列表项 三

1. 有序列表项 一    #有序列表
2. 有序列表项 二
3. 有序列表项 三

>>> 请问 Markdwon 怎么用？ - 小白    #多级引用
>> 自己看教程！ - 愤青
> 教程在哪？ - 小白

#代码
```
include <stdio.h>
int main(void)
{
    printf("Hello world\n");
}
```

```
graph LR    #流程图
A-->B
```

```
sequenceDiagram    #消息列表
A->>B: How are you?
B->>A: Great!
```

|学号|姓名|序号|    #表格
|-|-|-|
|小明明|男|5|
|小红|女|79|
|小陆|男|192|


`$ {equation} $`    #行内公式

$$ 公式 $$   #整行公式

```math    #块级公式
x = \dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a} 
```
```math
[\frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} =
1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}}
{1+\frac{e^{-8\pi}} {1+\ldots} } } }]
```

#分割线
* * *
***
*****
- - -
-----------

#特殊字符的使用
特殊字符 	描述 	字符的代码
	空格符 	&nbsp;
< 	小于号 	<
> 	大于号 	>
& 	和号 	&
￥ 	人民币 	&yen;
© 	版权 	&copy;
® 	注册商标 	&reg;
°C 	摄氏度 	&deg;C
± 	正负号 	&plusmn;
× 	乘号 	&times;
÷ 	除号 	&divide;
² 	平方（上标²） 	&sup2;
³ 	立方（上标³） 	&sup3;