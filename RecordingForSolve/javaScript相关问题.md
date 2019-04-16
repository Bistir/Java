# JavaScript相关问题

## 1. 字符串转化成数字(praseInt(),parseFloat());

praseInt("blue"); == NaN
praseInt("010", 2); == 8
praseInt("010", 10); == 10

praseFloat();必须以十进制进行转换,无第二个参数;
praseFloat("010.12"); == 10.12;

## 2. ||: 符号的意义

var o = e || "2"; e未定义时 o="2",e定义时 o=e;

## 3. Js中的indexOf()

for String: 正常使用;
for Array[{},{}]: 不可用, toString() ==> [Object,Object] ;

## 4. Js中 null 与 undefined 的区别

```javascript
typeOf(null) //-- object
typeOf(undefined) // -- undefined
null == undefined // -- true
null === undefined // -- false

var object1 = null;
var object2 = undefined;
!object1 --> false
!object2 --> false
```