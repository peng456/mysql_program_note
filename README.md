# mysql_program_note
sql编程思考记录

数据库编程，这也是一个语言。但是网上基本上就是增删改查的角度去介绍，没有从一个语言的角度去介绍讲解。  
在此记录下，一个语言一般是从  

# 语法、
select、update、delete、INSERT INTO、CREATE DATABASE 、ALTER DATABASE 、CREATE TABLE  
ALTER TABLE、DROP TABLE 、CREATE INDEX、DROP INDEX  
group by,union,like,where字句，order by,INNER JOIN,LEFT JOIN,RIGHT JOIN。  

SELECT * FROM ;

子查询等。

# 变量  
用户变量:@a  
会话变量:只对连接的客户端有效。
全局变量:set GLOBAL a; set @@global.a;(具有super权限才可以)  
局部变量:在begin到end语句块之间.declare语句专门用于定义局部变量  

DECLARE crs INT DEFAULT 0;  
SET @a=0;  
使用变量：  select @a;   a;

declare用来定义局部变量
https://blog.csdn.net/linybo/article/details/38663313
@用来定义会话变量

自定义变量、 field 、table 、index、view 、database

# 数据类型 
主要是 field 的类型; （http://www.runoob.com/mysql/mysql-data-types.html）  
数值类型  
TINYINT,SMALLINT,MEDIUMINT,INT或INTEGER,BIGINT,FLOAT,DOUBLE,DECIMAL  

日期和时间类型  
DATE,TIME,YEAR,DATETIME,TIMESTAMP  

字符串类型  
CHAR,VARCHAR,TINYBLOB,TINYTEXT,BLOB,TEXT,MEDIUMBLOB,MEDIUMTEXT,LONGBLOB,LONGTEXT


# 运算符:  
+  -  * /(或DIV) % (或MOD)  

=  <>,!=  > < <=    >=  between     not between     in   not in   <=>   like  rlike or regexp     is null    is not null  

NOT 或 ！    AND     OR      XOR    

&   |    ^     !      <<      >>  

优先级跟其他语言类似


# 控制流程函数
IF语句、CASE语句、LOOP语句、WHILE语句、LEAVE语句、ITERATE语句、REPEAT语句（参考:https://blog.csdn.net/nangeali/article/details/76285327）

IF:  

IF(expr,v1,v2)；  
IFNULL(v1,v2)  
NULLIF(expr1, expr2)  

CASE:  

SELECT
	CASE
WHEN 1 > 0 THEN
	TRUE
ELSE
	FALSE
END;

等

# 数组  

# sql执行顺序
这个很重要（http://www.cnblogs.com/qanholas/archive/2010/10/24/1859924.html）

# 方法 
1、户定义函数  (https://www.cnblogs.com/luojianqun/p/4479672.html)

// set global log_bin_trust_function_creators = 1; -- 开启bin_log 复制 函数创建
DROP FUNCTION IF EXISTS hello; -- 删掉已经存在的
DELIMITER $$    -- 定义分隔符，必须要有，可以不是$$
CREATE FUNCTION hello( s varchar(30)) -- 多个参数用,分割 参数的类型必须是mysql列存在的类型
RETURNS VARCHAR(255)                  -- 指定返回值类型，如果你不确定返回文本长度，可以使用text
BEGIN
    DECLARE str varchar(255) default 'hello '; -- 定义一个变量，可以指定默认值
    SET str = concat(str,s);                    -- 设置改边变量的值
    RETURN str;                                 -- 返回值
END $$                                          -- 注意看清楚了，这个end后面有你在前面定义的分割符号
DELIMITER $$                                    -- 好，这里结束。

调用自定义函数
select hello("nihao")

2、存储过程

3、有很多内置方法

4、子程序


# 类
没有
# 命名对象 
没有
# 命名空间 
没有
# 基础函数介绍  （http://www.runoob.com/mysql/mysql-functions.html）  
## MySQL 字符串函数  
ASCII(s)、CHAR_LENGTH(s)、CHARACTER_LENGTH(s)、CONCAT(s1,s2...sn)、CONCAT_WS(x, s1,s2...sn)、  
FIELD(s,s1,s2...)、FIND_IN_SET(s1,s2)、FORMAT(x,n)INSERT(s1,x,len,s2)、LOCATE(s1,s)、LCASE(s)、LEFT(s,n)  
LEFT(s,n),LOCATE(s1,s),LOWER(s),LPAD(s1,len,s2),LTRIM(s),MID(s,n,len)  
POSITION(s1 IN s),repeat(s,n),REPLACE(s,s1,s2),REVERSE(s),RIGHT(s,n)，RPAD(s1,len,s2)  
RTRIM(s),SPACE(n),STRCMP(s1,s2),SUBSTR(s, start, length),SUBSTRING(s, start, length)  
SUBSTRING_INDEX(s, delimiter, number)、TRIM(s),UCASE(s),UPPER(s)

## MySQL 数字函数  
ABS(x),ACOS(x),ASIN(x),ATAN(x),ATAN2(n, m),AVG(expression),CEIL(x),CEILING(x),COS(x),COT(x)  
COUNT(expression),DEGREES(x),n DIV m,EXP(x),FLOOR(x),GREATEST(expr1, expr2, expr3, ...),LEAST(expr1, expr2, expr3, ...)	   
LN,LOG(x),LOG10(x),LOG2(x),MAX(expression),MIN(expression),MOD(x,y),PI()  
POW(x,y),POWER(x,y),RADIANS(x),RAND(),ROUND(x),SIGN(x),SIN(x),SQRT(x),SUM(expression),TAN(x),TRUNCATE(x,y)  

## MySQL 日期函数  
ADDDATE(d,n),ADDTIME(t,n),CURDATE(),CURRENT_DATE(),CURRENT_TIME(),CURRENT_TIMESTAMP(),CURTIME(),DATE()  
DATEDIFF(d1,d2),DATE_ADD(d，INTERVAL expr type),DATE_FORMAT(d,f)  
DATE_SUB(date,INTERVAL expr type),DAY(d),DAYNAME(d)	,DAYOFMONTH(d),DAYOFWEEK(d),DAYOFYEAR(d),EXTRACT(type FROM d)  
FROM_DAYS(n),HOUR(t),LAST_DAY(d),LOCALTIME(),LOCALTIMESTAMP(),MAKEDATE(year, day-of-year),MAKETIME(hour, minute,second)  
MICROSECOND(date),MINUTE(t),MONTHNAME(d),MONTH(d),NOW(),PERIOD_ADD(period, number),PERIOD_DIFF(period1, period2),QUARTER(d)  
SECOND(t),SEC_TO_TIME(s),STR_TO_DATE(string, format_mask),SUBDATE(d,n),SUBTIME(t,n),TIME(expression)  
TIME_FORMAT(t,f),TIME_TO_SEC(t),TIMEDIFF(time1, time2),TIMESTAMP(expression, interval),TO_DAYS(d),WEEK(d)	,WEEKDAY(d)	  
WEEKOFYEAR(d)	,YEAR(d)	,YEARWEEK(date, mode)  

## MySQL 高级函数
BIN(x),BINARY(s)

CASE expression
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
   ...
    WHEN conditionN THEN resultN
    ELSE result
END

CAST(x AS type),COALESCE(expr1, expr2, ...., expr_n),CONNECTION_ID(),CONV(x,f1,f2)  
CONVERT(s USING cs),CURRENT_USER(),DATABASE(),  
IF(expr,v1,v2),IFNULL(v1,v2)  
LAST_INSERT_ID(),NULLIF(expr1, expr2),SESSION_USER(),SYSTEM_USER(),USER(),VERSION()





但是貌似数据库比较特殊，比如 表、索引、
