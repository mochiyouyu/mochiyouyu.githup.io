---
title: final
date: 2020-08-08 18:16:22
tags:
---
## final

```
final 关键字代表最终，不可改变的
final关键字的四种用法：
1.可以用来修饰一个类
2.可以用来修饰一个方法
3.可以用来修饰一个局部变量
4.可以用来修饰一个成员变量
不可变对于基本类型来说是数值不可变，
对于引用类型来说是变量的地址不可变
```

```
java 的四种修饰符:访问权限从大到小访问权限
                public  >  protected  > (default)  >  private
同一类            YES          YES         YES             YES
同一包            YES          YES         YES             NO
不同包子类         YES          YES         NO              NO
不同包非子类       YES           NO          NO              NO
定义一个类时权限修饰符的规则：
外部类： public /  (default)
成员内部类： public / protected / (default) / private 
局部内部类： 什么都不能写
局部内部类，如果希望所在方法的局部变量，那么这个局部变量必须是【有效的final】
匿名内部类的定义格式：
        接口名称 对象名 = new 接口名称(){
        //覆盖重写接口里面的抽象方法
        };
1. 匿名内部类在创建对象的时候只能使用一次，
        如果希望多次创建对象，而且类的内容一样的话，必须使用单独的实现类
       2. 匿名对象在调用方法时，只能调用一次，
        如果要多次调用必须创建有名称的对象，因为匿名对象类不能调用第二次方法
       3. 匿名内部类是省略的实现类或者子类，而匿名对象是省略了对象名称，不是同一回事
```