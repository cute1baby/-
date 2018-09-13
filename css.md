1、解决pc端字体小于12px不生效的问题：
```
<span>看我的字体大小</span>
css:
span{
  font-size:12px;
  display:inline-block;
  tranform:scale(0.5);
}
这样就能完成缩放：因为scale对应的是元素的宽高缩放，所以要设置成行内块元素才有宽高属性。
```

2、文字超过使用省略号的问题：
```
一行的省略号
	div{
		overflow: hidden;
		text-overflow: ellipsis;
		width: 200px;
		height:200px;
		white-space:no-wrap;
	}
  
----------------------------------------------------
多行的省略号
.deviceSet p{
	display: -webkit-box;
	display: box;
	-webkit-box-orient:vertical;
	-webkit-line-clamp: 2;
	overflow: hidden;
}
```
