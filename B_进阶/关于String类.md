#### String.valueOf(Object),Object为空的情况
- 如果Object为空，那么将会返回字符串‘null’,而非null
- valueOf(Object)源码如下：
``` java
public static String valueOf(Object obj) {
	return (obj == null) ? "null" : obj.toString();
}
```

- 错误示范
``` java
Object obj = null;
String str = String.valueOf(obj);
if( null != str ){
	System.out.println("str is not null!");
}else{
	System.out.println("str is null!");
}
System.out.println(str instanceof String);
```

- 输出结果
``` java
str is not null!
true
```

- 总结
> 无论```Object```是否为空，```valueOf()```后的结果都不可能为空，所以正确判断方式应该是提前判断```Object```是否为空，或者使用```equals("null")```来判断