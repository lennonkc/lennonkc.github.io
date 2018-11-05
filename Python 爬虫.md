# Python 爬虫

# 查找

## find_all

![1540562285986](D:\MarkDownPic\1540562285986.png)

## find

![1540562299970](D:\MarkDownPic\1540562299970.png)

### 查找文档中的<title>元素

![1540562363714](D:\MarkDownPic\1540562363714.png)

### 查找所有a元素

```python
soup = BeautifulSoup(***,"lxml")
tags = soup.find_all("a")
for tag in tags:
    print tag
```

### 查找第一个a元素

```python
soup = BeautifulSoup(***,"lxml")
tags = soup.find("a")
for tag in tags:
    print tag
```

### 查找class="title"的p元素

```python
tag = soup.find_all("p",attrs={"class":"title"})
```

### 查找class="sister"的元素

```python
tag = soup.find_all(name=None,attrs={"class":"sister"})
```

## 获取元素的属性值

```python
soup = BeautifulSoup(***,"lxml")
tags = soup.find_all("a")
for tag in tags:
    print tag["href"]
```

### 获取元素文本值

```python
for tag in tags:
    print tag.text
```

## 高级查找

![1540691827046](D:/MarkDownPic/1540691827046.png)

**高级查找中查找class时需要注意class是一个列表, 只查询其中一个可能会出错**

![1540692073176](D:/MarkDownPic/1540692073176.png)

所以查询的时候要把字符串型"story" "xxx"等的数据转换成列表

# 遍历

## 遍历所有父节点

```python
soup = Beautiful(***,"lxml")
tag=soup.find("p")

while tag:
    print tag.name
    tag = tag.parent
```

## 获得元素节点直接子元素节点

```python
tag = soup.find("p")
for x in tag.children:
    print x
```

![1540692713867](D:/MarkDownPic/1540692713867.png)

程序输出

![1540692731313](D:/MarkDownPic/1540692731313.png)

两个b元素之间是**一个** elements型的子节点, *Once upon a time* 是一个 text 型的子节点! 

## 获取*元素的所有子孙节点

![1540692815116](D:/MarkDownPic/1540692815116.png)



## 获取兄弟节点

![1540692852708](D:/MarkDownPic/1540692852708.png)



# 使用CSS语法查找元素(select)

## CSS语法

![1540791143741](D:/MarkDownPic/1540791143741.png)

![1540791169527](D:/MarkDownPic/1540791169527.png)

## 属性的语法规则(=,^,$,*)

![1540791234416](D:/MarkDownPic/1540791234416.png)

## 查找子孙节点

![1540791370723](D:/MarkDownPic/1540791370723.png)

![1540791386996](D:/MarkDownPic/1540791386996.png)

## 查找直接子节点( > )

![1540791435893](D:/MarkDownPic/1540791435893.png)

## 查找兄弟节点(~)

![1540791674940](D:/MarkDownPic/1540791674940.png)

![1540791550359](D:/MarkDownPic/1540791550359.png)

![1540791561013](D:/MarkDownPic/1540791561013.png)



