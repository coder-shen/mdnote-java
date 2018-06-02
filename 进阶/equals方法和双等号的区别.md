### 一、双等号的特性
* 如果等号两边是基本类型并且类型相同的情况就判断值是否相等
* 如果等号两边是基本类型但是类型不相同的情况（这个需要了解）
* 如果等号两边是对象，就是判断对象在内存中的引用地址是否相同

### 二、equals方法是什么
* equals是Object对象的一个方法，默认实现如下：
``` java
public boolean equals(Object obj) {
      return (this == obj);
}
```
* 从代码可以看出默认实现等同于直接用 “==”，所以需要子类来重写这个方法（如果有需要的话）
* 比较常见的就是String类的实现：
``` Java
public boolean equals(Object anObject) {
    if (this == anObject) {
        return true;
    }
    if (anObject instanceof String) {
        String anotherString = (String)anObject;
        int n = value.length;
        if (n == anotherString.value.length) {
            char v1[] = value;
            char v2[] = anotherString.value;
            int i = 0;
            while (n-- != 0) {
                if (v1[i] != v2[i])
                    return false;
                i++;
            }
            return true;
        }
    }
    return false;
}
```
* String类的需求就是需要判断String具体的值，而非对象地址是否相同
* 方法开始用双等号判断了对象地址是否相同，如果相同的话，那么值肯定也是相同的，所以直接返回了true
* 然后判断方法参数的Object对象是否是String类型，如果不是那么返回false
* 如果是String类型就继续判断，吧Object转换成String，然后和当前对象this的value值比较长度和每一个char是否相同
