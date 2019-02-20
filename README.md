# mysql_program_note
sql编程思考记录

数据库编程，这也是一个语言。但是网上基本上就是增删改查的角度去介绍，没有从一个语言的角度去介绍讲解。  
在此记录下，一个语言一般是从  
语法、变量、数据类型、运算符、  
控制流程  if else;switch;while;for  
数组  
方法  
类  
命名对象  
命名空间  
基础函数介绍  （http://www.runoob.com/mysql/mysql-functions.html）  
MySQL 字符串函数  
ASCII(s)、CHAR_LENGTH(s)、CHARACTER_LENGTH(s)、CONCAT(s1,s2...sn)、CONCAT_WS(x, s1,s2...sn)、  
FIELD(s,s1,s2...)、FIND_IN_SET(s1,s2)、FORMAT(x,n)INSERT(s1,x,len,s2)、LOCATE(s1,s)、LCASE(s)、LEFT(s,n)  
LEFT(s,n),LOCATE(s1,s),LOWER(s),LPAD(s1,len,s2),LTRIM(s),MID(s,n,len)  
POSITION(s1 IN s),repeat(s,n),REPLACE(s,s1,s2),REVERSE(s),RIGHT(s,n)，RPAD(s1,len,s2)  
RTRIM(s),SPACE(n),STRCMP(s1,s2),SUBSTR(s, start, length),SUBSTRING(s, start, length)  
SUBSTRING_INDEX(s, delimiter, number)、TRIM(s),UCASE(s),UPPER(s)

MySQL 数字函数  
ABS(x),ACOS(x),ASIN(x),ATAN(x),ATAN2(n, m),AVG(expression),CEIL(x),CEILING(x),COS(x),COT(x)  
COUNT(expression),DEGREES(x),n DIV m,EXP(x),FLOOR(x),GREATEST(expr1, expr2, expr3, ...),LEAST(expr1, expr2, expr3, ...)	   
LN,LOG(x),LOG10(x),LOG2(x),MAX(expression),MIN(expression),MOD(x,y),PI()  
POW(x,y),POWER(x,y),RADIANS(x),RAND(),ROUND(x),SIGN(x),SIN(x),SQRT(x),SUM(expression),TAN(x),TRUNCATE(x,y)  

MySQL 日期函数  
ADDDATE(d,n),ADDTIME(t,n),CURDATE(),CURRENT_DATE(),CURRENT_TIME(),CURRENT_TIMESTAMP(),CURTIME(),DATE()  
DATEDIFF(d1,d2),DATE_ADD(d，INTERVAL expr type),DATE_FORMAT(d,f)  
DATE_SUB(date,INTERVAL expr type),DAY(d),DAYNAME(d)	,DAYOFMONTH(d),DAYOFWEEK(d),DAYOFYEAR(d),EXTRACT(type FROM d)  
FROM_DAYS(n),HOUR(t),LAST_DAY(d),LOCALTIME(),LOCALTIMESTAMP(),MAKEDATE(year, day-of-year),MAKETIME(hour, minute,second)  
MICROSECOND(date),MINUTE(t),MONTHNAME(d),MONTH(d),NOW(),PERIOD_ADD(period, number),PERIOD_DIFF(period1, period2),QUARTER(d)  
SECOND(t),SEC_TO_TIME(s),STR_TO_DATE(string, format_mask),SUBDATE(d,n),SUBTIME(t,n),TIME(expression)  
TIME_FORMAT(t,f),TIME_TO_SEC(t),TIMEDIFF(time1, time2),TIMESTAMP(expression, interval),TO_DAYS(d),WEEK(d)	,WEEKDAY(d)	  
WEEKOFYEAR(d)	,YEAR(d)	,YEARWEEK(date, mode)  

MySQL 高级函数
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
