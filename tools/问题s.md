向数据库中，把一个表的select结果作为值插入到其他表。：

insert into sys_user_role (user_role_id,user_id,role_id) 
(SELECT REPLACE(UUID(),'-',''),user_id,(SELECT role_id from sys_role where role_name='普通用户') as role_id 
from sys_user 
where user_id not in (SELECT user_id from sys_user_role where role_id ='user'));
