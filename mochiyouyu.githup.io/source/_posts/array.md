---
title: array
date: 2020-07-18 12:00:18
tags:
---
## 二分法查找
我的通讯录里面有 10 个人，分别是
```
[
"Allen"
,
"Emma"
,
"James"
,
"Jeanne"
,
"Kelly"
,
"Kevin"
,
"Mary"
,
"Natasha"
,
"Olivia"
,
"Rose"
]
```
通讯录自带的排序功能，已经帮我们将人物按名字排序完成。

```
排序规则是按照英文字母排序，例如：Kelly在Kevin前面，因为第三个字母i在v的前面。
```

请大家完善右侧 方法，用二分查找法，快速找出人名对应的通讯录位置。

##### 测试案例：

```
Kelly , Edith 。
```

##### 测试结果

```
   Kelly 存在名单中，位置是 4
   Edith 不存在名单中
```

##### 小提示:

在 Java 中可以使用String对象compareTo()方法比较字符串的先后顺序，语法规则为:

```
str1.compareTo(str2)
```

结果如果是负数则表示 str1 排序在 str2 前面。如果用 Kelly 和 Kevin 进行比较，案例如下：

```
    "Kelly".compareTo("Kevin") // 结果为-10
    "Kevin".compareTo("Kelly") // 结果为10
```

从结果，我们知道 Kelly 排序在 Kevin 前面。

```
public static int find(ArrayList<String> array, String aim) {
    int left=0;
    int right=array.size()-1;
    while(left<=right){
      int middle=(left+right)/2;
      String middleValue=array.get(middle);
      if(aim.compareTo(middleValue)==0){
        return middle;
      }else if(aim.compareTo(middleValue)<0){
        right=middle-1;
      }else{
        left=middle+1;
      }
    }
    return -1;
  }
public static void main(String[] args) {
    ArrayList<String> array = new ArrayList<>();
    array.add("Allen");
    array.add("Emma");
    array.add("James");
    array.add("Jeanne");
    array.add("Kelly");
    array.add("Kevin");
    array.add("Mary");
    array.add("Natasha");
    array.add("Olivia");
    array.add("Rose");
    int result1 = find(array, "Kelly");
    if (result1 == -1) {
      System.out.println("Kelly 不存在名单中");
    } else {
      System.out.println("Kelly 存在名单中，位置是 " + result1);
    }
    int result2 = find(array, "Edith");
    if (result2 == -1) {
      System.out.println("Edith 不存在名单中");
    } else {
      System.out.println("Edith 存在名单中，位置是 " + result2);
    }
  }
```