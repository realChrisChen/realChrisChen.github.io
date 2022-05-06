## 将字符串转换为字符数组

```java

char[] stringArr = str.toCharArray();

```

## 字符串数组及二维数组

```java

//1维的
//java的数组都是同一类型的
String[] cars ={"Camaro", "Corvette","Tesla"};

//宁一种创建方法
Sring [] cars = new String[3];
cars[0] = "Tesla";
cars[1] = "Corvette";


//2维的
String[][] cars = new String[3][3];
String[][] persons = {
                         {Jack, Mally},
                         {Blake,Griffin}
                     };
```