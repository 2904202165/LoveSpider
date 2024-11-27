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
举个栗子，比如你可以搜索包含关键词“再见爱人”且发布日期在**2024-11-26**和**2024-11-27**之间的微博。搜索结果数量巨大，对于非常热门的关键词，在一天的指定时间范围，可以获得**1000万**以上的搜索结果。注意这里的一天指的是时间筛选范围，具体多长时间将这1000万微博下载到本地还要看获取的速度。1000万只是一天时间范围可获取的微博数量，如果想获取更多微博，可以加大时间范围，比如10天，最多可以获得1000万X10=1亿条搜索结果，当然你也可以再加大时间范围。对于大多数关键词，微博一天产生的相关搜索结果应该低于1000万，因此可以说**本程序可以获取指定关键词的全部或近似全部的搜索结果**。本程序可以获得几乎全部的微博信息，如微博正文、发布者等。

#### 4. 运行程序
运行命令：
```bash
scrapy crawl search -s JOBDIR=crawls/search
```

#### 5. 输出说明
- **微博id**：微博的id，为一串数字形式
- **微博bid**：微博的bid
- **微博内容**：微博正文
- **头条文章url**：微博中头条文章的url，若某微博中不存在头条文章，则该值为''
- **原始图片url**：原创微博图片和转发微博转发理由中图片的url，若某条微博存在多张图片，则每个url以英文逗号分隔，若没有图片则值为''
- **视频url**: 微博中的视频url和Live Photo中的视频url，若某条微博存在多个视频，则每个url以英文分号分隔，若没有视频则值为''
- **微博发布位置**：位置微博中的发布位置
- **微博发布时间**：微博发布时的时间，精确到天
- **点赞数**：微博被赞的数量
- **转发数**：微博被转发的数量
- **评论数**：微博被评论的数量
- **微博发布工具**：微博的发布工具，如iPhone客户端、HUAWEI Mate 20 Pro等，若没有则值为''
- **话题**：微博话题，即两个#中的内容，若存在多个话题，每个url以英文逗号分隔，若没有则值为''
- **@用户**：微博@的用户，若存在多个@用户，每个url以英文逗号分隔，若没有则值为''
- **原始微博id**：为转发微博所特有，是转发微博中那条被转发微博的id，那条被转发的微博也会存储，字段和原创微博一样，只是它的本字段为空
- **结果文件**：保存在当前目录“结果文件”文件夹下以关键词为名的文件夹里
- **微博图片**：微博中的图片，保存在以关键词为名的文件夹下的images文件夹里
- **微博视频**：微博中的视频，保存在以关键词为名的文件夹下的videos文件夹里
- **user_authentication**：微博用户类型，值分别是`蓝v`，`黄v`，`红v`，`金v`和`普通用户`
