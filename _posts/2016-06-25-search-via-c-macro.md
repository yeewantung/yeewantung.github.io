---
layout: post
title: An Interesting Search with c macro
author: "Hao Zhang"
categories: code
---

question：[insert "+" or "-" into "123456789" and ensure the result is 100, output all the situations.][question]

code：
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
  if(argc==1) num = 100;
  else        num = atoi(argv[1]);
  C2(1);
  C2(-1);
  return 0;
}
{% endhighlight %}

output：

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

it uses macro to expand all the situation, which is a little interesting so I post it here.

[question]: http://www.linuxeden.com/html/develop/20150907/162726.html
