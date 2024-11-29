### Love Spider

#### 1. 部署环境
服务器要求：  
**ubuntu 22.04**  
Python环境：**3.8**  
Pillow >= **8.1**

#### 2. 下载与安装
克隆仓库：
```bash
git clone https://github.com/2904202165/LoveSpider.git
```
安装:
```bash
Scrapy：pip install scrapy
```
安装依赖：
```bash
pip install -r requirements.txt
```

#### 3. 连续获取一个或多个微博关键词搜索结果：
**搜索正文中包含指定关键词的微博**，可以指定搜索的时间范围。
举个栗子，比如你可以搜索包含关键词“再见爱人”且发布日期在**2024-11-27**和**2024-11-27**之间的微博。搜索结果数量巨大，对于非常热门的关键词，在一天的指定时间范围，可以获得**1000万**以上的搜索结果。注意这里的一天指的是时间筛选范围，具体多长时间将这1000万微博下载到本地还要看获取的速度。1000万只是一天时间范围可获取的微博数量，如果想获取更多微博，可以加大时间范围，比如10天，最多可以获得1000万X10=1亿条搜索结果，当然你也可以再加大时间范围。对于大多数关键词，微博一天产生的相关搜索结果应该低于1000万，因此可以说**本程序可以获取指定关键词的全部或近似全部的搜索结果**。本程序可以获得几乎全部的微博信息，如微博正文、发布者等。

#### 4. 运行程序
运行命令：
```bash
scrapy crawl search -s JOBDIR=crawls/search
```


#### 5. 连接Mysql
<img width="954" alt="e80ba7b66cea88342f99a335e7353d5" src="https://github.com/user-attachments/assets/baa2f25a-5069-46a9-998f-4360865aaeaa">

#### 6. 数据库备份
**可以通过设置定时任务备份数据库数据**  

<img width="630" alt="2c54ac47c3f7730a32b32a0467128a5" src="https://github.com/user-attachments/assets/dcc7ee17-0d1d-4d84-84b8-ece5658c46d4">

#### 7.爬虫自动化实现
如果爬取的数据量巨大，通过SSH的方法会受到网络等因素影响我们的爬取进度，因此可以通过在宝塔终端进行爬取
<img width="470" alt="1c4ae34fbf5c18c03989b0acbe24559" src="https://github.com/user-attachments/assets/c3b9c153-a1aa-4d4b-8503-cfe35ab776d9">
但是我们不难发现如果爬取的过程中我们只能在这个界面，不能做其他如数据库备份、数据查看等操作，因此我们可以通过在文件执行界面写一个运行脚本之后在PM2管理器上运行我们的脚本就可以实现自动化后台挂起爬取数据了
<img width="462" alt="ac6d3bd9a5badee15e79eef06fa0e42" src="https://github.com/user-attachments/assets/73b23541-9734-4e93-b677-8c9d10c19c74">
结合第六步的操作，我们可以彻底解放双手，让子弹再飞一会儿~
但是爬取的时候因为我们加入了cookie，有时候cookie会刷新，因此如果隔一段时间看到我们的数据库没有数据加入了，要看看是不是cookie更新了等问题所导致
#### 7. 数据库结构展示：


