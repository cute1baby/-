# -
记录平时一些小细节部分的知识

```
yarn global bin:全局安装包之后仍然在命令中找不到，需要输入该命令然后配置全局变量
同理，如果npm在全局配置的全局的包找不到，那么在C:\Users\DELL\AppData\Roaming\npm配置到全局变量中。
```


```
#bootstrapTable的请求方法，如果在请求之前不进行销毁数据的话，那么就会读取缓存里面的
数据，我们看到的现象也就是只能看到请求一次。所以我们需要在list请求之前：
$("#table").bootstrapTable('destroy'); 
```

```
【js的方法】：实现数组和对象的浅拷贝和深拷贝：
浅拷贝和深拷贝的区别：浅拷贝只能是修改基本数据类型之后不影响原数据，深拷贝是修改了引用类型不影响原数据。
简单数组的浅拷贝 =>  Array.prototype.slice();
对象数组的深拷贝 =>  [].concat(JSON.parse(JSON.stringify(paramsDef.QuestionTypeMappings))); 

所谓”深拷贝”，就是能够实现真正意义上的数组和对象的拷贝.

浅拷贝：Object.assign(target, ...sources)  针对第一层key修改有用，对象的对象属性值修改，原数据也会改变。
深拷贝：  let obj3 = JSON.parse(JSON.stringify(target));  这样的对象的对象属性值改变也不会有什么影响。
  let obj1 = { a: 0 , b: { c: 0}};
  let obj2 = Object.assign({}, obj1);  浅拷贝
  let obj3 = JSON.parse(JSON.stringify(obj1));  深拷贝
  
  
  
【jq的方法】:同时可以深拷贝和浅拷贝数组和对象。  
$.extend( [deep ], target, object1 [, objectN ] )
简单对象的浅拷贝 =>  deep为false时,浅拷贝
多层嵌套对象的深拷贝 =>  deep为true时，深拷贝
var arr = [{"key1":1,"key2":2},{"key3":3,"key4":4}];
var obj = {
    "key":{
        "keydemo1":1,
        "keydemo2":2,
    },
    "html":{
        "html1":1,
        "html2":2,
    }
}
var arr1 = $.extend(true, {}, arr);
arr[1].key3 = 100;
console.log(arr1);

var obj1 = $.extend(true, {} , obj);
obj.html.html1 = 100;
console.log(obj1);



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
