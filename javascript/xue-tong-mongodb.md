[首页](https://github.com/zhangdhu/blog/blob/master/index.md)

# 学通MongoDB
注：本文来源于[8天学通MongoDB——第一天 基础入门](http://www.cnblogs.com/huangxincheng/archive/2012/02/18/2356595.html)

>Mongo DB是目前在IT行业非常流行的一种非关系型数据库(NoSql),其灵活的数据存储方式备受当前IT从业人员的青睐。Mongo DB很好的实现了面向对象的思想(OO思想),在Mongo DB中 每一条记录都是一个Document对象。Mongo DB最大的优势在于所有的数据持久操作都无需开发人员手动编写SQL语句,直接调用方法就可以轻松的实现CRUD操作。


####一： 下载<br>
    
    上MongoDB官网 ，我们发现有32bit和64bit，这个就要看你系统了，不过这里有两点注意：
    1.1：根据业界规则，偶数为“稳定版”（如：1.6.X，1.8.X），奇数为“开发版”（如：1.7.X，1.9.X)，这两个版本的区别相信大家都知道吧。
    1.2：32bit的mongodb最大只能存放2G的数据，64bit就没有限制。
        我这里就下载"2.0.2版本，32bit“，ok，下载之后我就放到”E盘“，改下文件夹名字为”mongodb“。

####二：启动

    2.1：启动之前，我们要给mongodb指定一个文件夹，这里取名为”db",用来存放mongodb的数据
![](https://github.com/zhangdhu/blog/blob/master/img//5-1.png)
       2.2：微软徽标+R，输入cmd，首先找到“mongodb”的路径，然后运行mongod开启命令，同时用--dbpath指定数据存放地点为“db”文件夹。
![](https://github.com/zhangdhu/blog/blob/master/img/4-1.png)
      2.3：最后要看下是否开启成功，从图中的信息中获知，mongodb采用27017端口，那么我们就在浏览器里面键入“http://localhost:27017/”，

####三：基本操作

       由于是开篇，就大概的说下基本的“增删查改“，我们再开一个cmd，输入mongo命令打开shell，其实这个shell就是mongodb的客户端，
同时也是一个js的编译器，默认连接的是“test”数据库。
#####3.1  insert 操作

        好，数据库有了，下一步就是集合，这里就取集合名为“person”，要注意的就是文档是一个json的扩展（Bson)形式。 

#####3.2 find 操作

       我们将数据插入后，肯定是要find出来，不然插了也白插，这里要注意两点：

       3.2.1 “_id"： 这个字段是数据库默认给我们加的GUID，目的就是保证数据的唯一性。

       3.2.2 严格的按照Bson的形式书写文档，不过也没关系，错误提示还是很强大的。
#####3.3 update操作
      update方法的第一个参数为“查找的条件”，第二个参数为“更新的值”，学过C#，相信还是很好理解的。

#####3.4 remove操作

    remove中如果不带参数将删除所有数据，呵呵，很危险的操作，在mongodb中是一个不可撤回的操作，三思而后行。

![]