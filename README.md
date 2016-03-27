#简介

这是一个简单的购物搜索引擎，第一次接触搜索引擎，所以想大概知道基本流程。

#主要流程

##1. 一个爬虫
　　首先先要分析一下网页结构，收集一下商品名称、价格、评论等等，然后收集相关的URL入URL队列。利用宽度优先搜索持续遍历。
　　如果还不会爬虫、可以先去[Python爬虫学习系列教程](http://cuiqingcai.com/1052.html)简单的学习一下，如果没接触过python，建议先去看[Python 2.7教程 - 廖雪峰的官方网站](http://www.liaoxuefeng.com/wiki/001374738125095c955c1e6d8bb493182103fac9270762a000/)
 　　然后基本就可以完成一个简单的爬虫编写了
　　将爬好的数据整理，存入文件，之后都将用文件来进行操作
   
##2.建立索引
　　 这一部分主要是有以下几个步骤：（推荐使用python NLTK的数据包）
   
- 分词：
  将文件内容用分词系统进行分词，去掉禁用词。可以用python的jieba分词
- 建立倒排索引
  如果想写得比较完善的话可以去看《这就是搜索引擎核心技术》这本书。
  如果文件内容比较少的话，可以用python的字典建立倒排索引。把分割出的关键词放到字典中，字典的格式是：key + list.也就是一个关键字对应一个列表，可以在列表中存储单词在文本中出现的行号。
  
  
##3.搜索
　　建立好索引后就可以直接在dict中索引了，可以按照自己的习惯设定为一个词索引，也可以是多个关键词索引，后者需要求一下关键词列表的交集或者并集。
　　到此为止，一个简单的搜索引擎就结束了
   
  