# Oracle数据库常用函数

## 一、通用函数

### 1. decode 与 case when then else end

* 对查到的数据进行处理,进行可视化显示;
* eg:

```sql
--字典替换
--第一种方法
- select ename, decode(sex,'1','男','0','女') as 性别 from emp;
--第二种方法
    select ename,
        case
            when sex = '1'
            then '男'
            else 'nv' as 性别
        end as 性别
    from emp;
```

### 2. nvl

对值为null的数据进行处理：

* nvl(exp1,exp2);==>exp1的值为null,则取exp2的值,否则取exp1的值;  
* nvl2(exp1,exp2,exp3);=>exp1 != null ? exp2 : exp3;
* eg:

```sql
select sal+comm from emp;
--使用nvl进行处理comm为null的数据
select sal+nvl(comm,0) from emp;
```

## 二、数字函数

### 1.四舍五入 round()

```sql
select round(3.1415926,3) from dual;--结果:3.142
select round(314.15926,-2) from dual;--结果: 300
```

### 2.截断 trunc()

```sql
select trunc(251.5666,2) from dual;--结果: 251.56
select trunc(251.5666,-2) from dual;--结果: 200
```

## 三、转换函数

### 1. to_char()

* 将内容按一定格式转换成字符串

```sql
select sysdate||'' from dual
   select to_char(sysdate,'yyyy-mm-dd') from dual;
   --每隔3位加一个逗号,如果含有小数,默认四舍五入(或者格式设为'999,999,999,999.99')
   select to_char(123456789,'999,999,999,999') from dual;

```

### 2. to_date()

### 3. replace()、trim()

&nbsp;&nbsp;&nbsp;&nbsp;
replace(): 用字符替代字符;  
&nbsp;&nbsp;&nbsp;&nbsp;
trim(): 去掉字段两边的空格,中间的无影响.

```sql
select replace(' 1 2 3 ',' ','') from dual; --结果:  123
```
