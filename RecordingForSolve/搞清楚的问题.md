Js中遍历数组和对象
========

&nbsp;&nbsp;&nbsp;&nbsp;1.for循环
-----

```javascript
//  优化版for循环: 使用变量,将长度缓存起来,避免重复获取长度,数组很大时优化效果明显,相比与普通for循环 ;

for(var i = 0,length = arr.length; i < length; i++){
    console.log(arr[i]);
}
```

&nbsp;&nbsp;&nbsp;&nbsp;2.forEach/map
-----

```javascript
<!-- forEach,性能差,比普通的for还弱 -->
arr.forEach(function(value,i){
    console.log('forEach遍历'+i+'--'+value)
});

<!-- map,与forEach类似,支持return返回值,forEach不支持 -->
```

&nbsp;&nbsp;&nbsp;&nbsp;3.for-in
-----

```javascript
// for-in是为遍历对象而设计的,不适用于遍历数组
// 使用for-in遍历数组的缺点;数组的下标index值是数字,for-in遍历的index值为字符串.
for(var item in arr){
    console.log(arr[item]);
    console.log(item);
}
```

&nbsp;&nbsp;&nbsp;&nbsp;4.for-of
-----

```javascript
// for-of避开了for-in实用的所有缺点  
// 与forEach不同的是,它可以正确响应break,continue,return语句
// for-of同样支持遍历对象和字符串.
for(var i of arr){
    console.log(i);
}
```