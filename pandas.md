#**7月14**
#pandas的使用
##pandas入门
###一、pandas的数据结构介绍
------
pandas中有两种主要的数据结构：Series和DataFrame。它们为大多数应用提供了一种可靠的、抑郁使用的基础。
####1、Series
Series是一种类似于以为数组的对象，由一组数据以及一组与之相关的数据标签（即索引）组成。
'''python
a=Series([4,7,-5,3])
'''
仅有一组数据即可产生最简单的Series。Series的字符串表现形式为：索引在左边，值在右边。
如果没有指定索引，则会自动创建一个0到N-1的索引。可以通过Series的values和index属性得到数组和索引对象。可以将Serise看作一个字典。也可以通过字典来创建Series。
#**7月15**
####1. *Dataframe的合并*
使用函数merge可以将两个Dataframe合并，可以指定按照末一列进行合并，如果没有指定，则会自动寻找重叠列的列名当作键，不过最好指定一下。假如df1和df2分别为两个
Dataframe，且以键“key”合并，则代码为pd.merge(df1,df2,on='key')，得到的结果为有重复的就会按照顺序排列，没有重复的就不会出现
如果两个对象的列名不同，也可以分别进行指定，代码可写为pd.merge(df1,df2,left_on='lkey',right_on='rkey')
####2. *字符串操作*
> * 可以使用split拆分为数段，使用方法为a.split('')，双引号中写入需要分割的字符。通常与strip（以空格为分隔符）一起使用。
> * 几个字符串可以放在一个变量中，如a=['ac','dd','cc']，如果c,d,e=a，则输出为c='ac' d='dd' e='cc'
> * 将子字符串连接起来有两种方法，可以使用“+”，如，c+d+e，输出为'acddcc'。也可以使用join函数，如'::'.join(a)，则输出为'ac::dd::cc'
> * 字符串的子串定位，最好的方法是使用Python中的关键字in，也可以使用index和find这两个函数，如val = 'a,b, guido'
输入代码'guido' in val ，则输出为True。输入代码val.index(',') ，则输出为1，表示为第二个字符。同样使用find也一样，
但是index与find的区别在于，如果子字符串不存在，index会出现异常，find会输出-1.
> * count函数可以返回指定字符串出现的次数，如val.count(',')，输出为2。
> * replace用另一个字符串代替指定的字符串，如val.replace(',','')，则输出为'ab guido'。
> * lower和upper函数可以将字母字符转换为小写或大写。
#**7月16**
####1. *日期和时间数据类型*
Python标准库中包含有用于日期（date）和时间（time）数据的数据类型，而且还有日历方面的功能。我们主要会用到datetime、time和calendar
模块。datetime.datetime(也可以简写为datetime)是用的最多的数据类型。
> * now()函数显示出的是当前时间，如a=datetime.now()输出年、月、日，now.year，可以输出年份。datetime以毫秒的形式存储日期和时间。
> * datetime.time.timedelta可以表示两个datetime对象之间的时间差
####2. *字符串与datetime的互相转换*
> * 使用str或strftime可以将datetime和pandas的Timestamp转化为字符串，使用方法为str(a)或a.strftime('%Y-%m-%d')，第一个为
将datetime全部转化为字符串，第二个只转化年月日。
> * datetime.strptime可以将这些格式化编码将字符串转化为日期
####3. 编码和解码coding和encoding，
使用drop进行删除，
将list数据转换为DataFrame直接使用DataFrame，
使用counts函数进行计数。
loc函数是什么意思
xrange是什么意思。
iloc是什么意思
isnan函数
查找重复的数据使用的函数
.gz文件
ExcelFile读出来的是标签号
to Excel 设置