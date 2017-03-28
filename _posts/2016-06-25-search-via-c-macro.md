---
layout: post
title: c宏来实现穷举
author: "Hao Zhang"
categories: test
---

问题：[编写一个在1，2，…，9（顺序不能变）数字之间插入+或-或什么都不插入，使得计算结果总是 100 的程序，并输出所有的可能性。例如：1 + 2 + 34 – 5 + 67 – 8 + 9 = 100。][question]

代码：
{% highlight c %}
#include <stdio.h>
#include <stdlib.h>

#define C10(x) if((x)==num)printf("%s = %d\n",#x,num);
#define C9(x) C10(x##9);C10(x+9);C10(x-9);
#define C8(x) C9(x##8);C9(x+8);C9(x-8);
#define C7(x) C8(x##7);C8(x+7);C8(x-7);
#define C6(x) C7(x##6);C7(x+6);C7(x-6);
#define C5(x) C6(x##5);C6(x+5);C6(x-5);
#define C4(x) C5(x##4);C5(x+4);C5(x-4);
#define C3(x) C4(x##3);C4(x+3);C4(x-3);
#define C2(x) C3(x##2);C3(x+2);C3(x-2);

int main(int argc,char ** argv){
  int num;
  if(argc==1) num = 0;
  else        num = atoi(argv[1]);
  C2(1);
  C2(-1);
  return 0;
}
{% endhighlight %}

结果：

{% highlight plain %}
123+45-67+8-9 = 100
123+4-5+67-89 = 100
123-45-67+89 = 100
123-4-5-6-7+8-9 = 100
12+3+4+5-6-7+89 = 100
12+3-4+5+67+8+9 = 100
12-3-4+5-6+7+89 = 100
1+23-4+56+7+8+9 = 100
1+23-4+5+6+78-9 = 100
1+2+34-5+67-8+9 = 100
1+2+3-4+5+6+78+9 = 100
-1+2-3+4+5+6+78+9 = 100
{% endhighlight %}

感觉挺有趣，所以发一下

[question]: http://www.linuxeden.com/html/develop/20150907/162726.html
