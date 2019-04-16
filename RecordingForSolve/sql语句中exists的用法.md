sql语句中exists的用法
=====

```sql
-- exists后的子句, 只在乎有没有结果集返回, 不在乎返回的是什么, 只有true和false两种结果
-- exists执行顺序: 将外查询的每一行, 代入内查询作为检验, 如果内查询返回的结果非空, 则返回true, 这一行作为一个结果.
    select id, name from table1 tb1 where exists(select id, name from table2 tb2 where tb1.id = tb2.id );
```

作用
----

在插入记录前, 需要检查这条记录是否存在, 记录不存在时才可以执行插入操作, 可以通过使用:  
insert into table1(name,sex) select 'zhangsan', '1' from table1 where not exists(select 1 from table1 where table1.id = 3)

exists与in
----

exists适用于外表小而内表大的情况, in适用于外表大而内表小的情况
