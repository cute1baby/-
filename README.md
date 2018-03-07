# -
记录平时一些小细节部分的知识


```
#bootstrapTable的请求方法，如果在请求之前不进行销毁数据的话，那么就会读取缓存里面的
数据，我们看到的现象也就是只能看到请求一次。所以我们需要在list请求之前：
$("#table").bootstrapTable('destroy'); 
```

```
prop和attr在jquery中的区别
prop一般用在标签的固有属性和属性值为布尔值的属性上。例如：class,href,selected,checked,disabled等
attr一般用在标签的自定义属性上。例如：abc,rebpet等自己定义的。
为什么要这样使用？
  就是在jq中，获取布尔值属性切布尔值属性在标签内没有定义的话，此时用attr获取的属性值是undefind.
  实例：
  <select>
    <option selected>111</option>
    <option>222</option>
    <option>333</option>
    <option selected>444</option>
  </select>
  此时如果说对当前的所有option进行遍历，并且用attr去获取selected的属性值，会出现三个undefind.
```
