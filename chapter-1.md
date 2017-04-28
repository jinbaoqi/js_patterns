## 单一`var`模式
只使用一个`var`在函数顶部进行变量声明：
* 提供一个单一的地址以查找到函数需要的所有局部变量。
* 防止出现变量在定义前就被使用的逻辑错误（变量提升）。

单一`var`模式如下所示：
```javascript
function func() {
  var a=1,
      b=2;
  //函数体...
}
```
## 提升：零散变量的问题
JS允许在函数的任意地方声明多个变量，这就是`变量提升`。
```javascript
myname = "global"
function func() {
  alert(myname)// undefined
  var myname = "local"
  alert(myname)// local
}
func()
```
上面代码，等价于如下：
```javascript
myname="global"
function func() {
  var myname
  alert(myname)
  myname = "local"
  alert(myname)
}
```
