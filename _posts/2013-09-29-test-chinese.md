---
layout: post
title: javascript中的类型检查
category: posts
---

# 罗列一下js中的类型检查方法： #
1. 使用typeof运算符 [详细用法](https://developer.mozilla.org/zh-CN/docs/JavaScript/Reference/Operators/typeof)
	* 原理：typeof检查type [ECMA-262对typeof的定义](http://bclary.com/2004/11/07/#a-11.4.3)
	* 语法：

	    ```js
	if(typeof(value) == "number") {...}
	    ```
	* type包括且仅包含六种类型：number, string, boolean, undefined, object（typeof(null)返回object）, function

1. 使用instanceof运算符
	* 原理：instanceof检查私有属性prototype；
	* 语法：

	    ```js
	if(value instanceof Number){...}
	    ```
	* 可以检测基本数据类型，对于复合数据类型（除了function）通通认作object。 
注意，首字母要大写，如Number,String,Boolean,Object,Function。

1. 使用constructor
	* 原理：检查公有属性constructor；
	* 语法：

	    ```js
	if(var1.constructor == Array){...}
	    ```
	* 备注：
		1. 如果尝试```alert(var1.constructor)```，你会发现alert窗口的内容是constructor的实现代码。
		1. 当使用iframe时，constructor检查将会失效，因为iframe和父页面使用不同的js引擎实例。
		1. 对于定义形式为

        	```js
function func1(){
	....
}
            ```
的函数，可以通过 ```func1.constructor.toString().match(/^s*functions*(w+)/)[1];```
来抽取方法名。而对于形式为

            ```js
func1 = function(){
   ....
}
            ```
则无法抽取方法名; 
		1. 实例的constructor属性是可以修改的（除了1，true,"ssss"这几类），所以并不可靠。参见[constructor][1]

1. 使用prototype.toString
	* 原理：检查Object.prototype.toString.call(var1)私有属性class；
	* 语法：

	    ```js
	Object.prototype.toString.call(123) //[object Number]
	    ```
1. 属性检测法。
	* 原理：[duck typing](http://zh.wikipedia.org/zh-cn/%E9%B8%AD%E5%AD%90%E7%B1%BB%E5%9E%8B)
	* 语法：

    	```js
    function isDuck(object) {
        if (typeof object !== "object") return false;
        if (typeof object.quack !== "function") return false;
        return true;
    }
    	```


[1]: https://developer.mozilla.org/en/Core_JavaScript_1.5_Reference/Global_Objects/Object/constructor "constructor"
