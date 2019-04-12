# past_projects
https://selfdrivingcars.mit.edu/wordpress/wp-content/uploads/2017/05/mystery_number_scrambled.jpg
https://selfdrivingcars.mit.edu/wordpress/wp-content/uploads/2017/07/shuffle_indecies.txt
http://selfdrivingcars.mit.edu/wordpress/wp-content/uploads/2017/05/circle.csv

Siri Engineer Phone Screen Questions with Answer

========

Q1 (共3分): 
在Linux操作系统中，有一个本地文本文件input.csv。请回答下面问题：

Q1.1 (1分) 如何将该文件的最后十行输出到屏幕？
```
tail -n 10 input.csv
```

Q1.2 (2分): 如何统计该文件中有多少行带有”banana”这个序列？
```
grep -H "banana" input.csv | wc -l
```
Q2 (3分): 

数据库里有一个表格叫做product，有三列数据product_id, company, price，分别代表产品编码、公司名、价格。保证表里没有重复的行。写一条SQL语句，找到“Apple”这个公司中价格最高的十个产品编码。

 product_id  | company   |  price  
 ------------|-----------|----------

```
select product_id from product order by price desc limit 10;
```

========

Q3 (共6分): 在Python里有一个长度大于10的数组x。请回答下面问题：

Q3.1 (2分) 如何取x的最后十个元素？
x[-1]

Q3.2 (1分): 如何取x中最大的元素？
max(x)

Q3.3 (2分): 如何取x中所有能被3整除的元素：
```
res = []
for i in x:
  if i % 3 == 0:
  res.append(i)
```
Q4 (5分)如何反转一个整数. 比如. 123 -> 321, -123 -> -321
```
class Solution(object):
    def reverse(self, x):
        """
        :type x: int
        :rtype: int
        """
        num = 0
        if x == 0:
            return 0

        if x < 0:
            x = -x
            while x != 0:
                num = num*10 + x%10
                x = x/10
            num = -num
        else:
            while x != 0:
                num = num*10 + x%10
                x = x/10
        if num>pow(2,31)-1 or num < pow(-2,31):
            return 0  
        return num
 
```




Q5 (3分) 翻译下面的文档
Package rand implements pseudo-random number generators.
Random numbers are generated by a Source. Top-level functions, such as Float64 and Int, use a default shared Source that produces a deterministic sequence of values each time a program is run. Use the Seed function to initialize the default Source if different behavior is required for each run. The default Source is safe for concurrent use by multiple goroutines, but Sources created by NewSource are not.
Mathematical interval notation such as [0, n) is used throughout the documentation for this package.
For random numbers suitable for security-sensitive work, see the crypto/rand package.


rand包应用了伪随机数字生成装置。
随机数字从资源产生。顶级功能有，float64和int，每次有程序在跑都会用默认共享资源生成一个决定性序列。如果每次跑需要不同行为，就用Seed功能去初始化默认资源。多次goroutines的同时使用时，默认资源是安全的，但是新资源创建的资源却不安全。
数学区间标注诸如[0, n)  从头到尾一直被这文档使用。
如想了解适用于安全敏感工作的随机数字，请看crypto/rand安装包。
