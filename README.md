# LoveSpider
一款适用于微博爬虫进行舆情分析
1. 下载与安装
克隆仓库：git clone https://github.com/2904202165/LoveSpider.git
安装Scrapy：pip install scrapy
安装依赖：pip install -r requirements.txt
2. 配置设置
设置Cookie：在setting.py中填写DEFAULT_REQUEST_HEADERS的cookie。
设置搜索关键词：修改KEYWORD_LIST参数，可设置为单个关键词、多个关键词或包含特定话题的关键词。
设置搜索时间范围：通过修改START_DATE和END_DATE参数来指定。
设置进一步搜索阈值（可选）：调整FURTHER_THRESHOLD的值以优化搜索结果。
设置结果保存类型（可选）：通过修改ITEM_PIPELINES来选择保存类型，如写入csv文件、数据库等。
设置等待时间（可选）：通过修改DOWNLOAD_DELAY参数来控制访问间隔。
设置微博类型（可选）：通过修改WEIBO_TYPE参数来筛选微博类型。
设置包含内容（可选）：通过修改CONTAIN_TYPE参数来筛选包含特定内容的微博。
筛选微博发布地区（可选）：通过修改REGION参数来筛选微博发布地区。
配置数据库（可选）：填写MongoDB或MySQL的配置信息。
3. 运行程序
运行命令：scrapy crawl search或scrapy crawl search -s JOBDIR=crawls/search（后者可保存进度）。
注意：使用“Ctrl + C”一次来正确保存进度，以便下次继续获取数据。
