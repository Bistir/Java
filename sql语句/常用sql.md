##常用sql语句

#查询表名以及字段名
-- 查询表名
select * from user_tables;
select * from all_tables;
-- 查询所有表的字段信息
select owner, table_name, column_name, data_type from all_tab_columns;
select table_name, column_name, data_type from user_tab_columns;
-- 查询字段的备注信息
select * from user_col_comments where table_name = 'T_PWYX_PB_ZGZJL_BAK';
select * from all_col_comments where table_name = 'T_PWYX_PB_ZGZJL_BAK';