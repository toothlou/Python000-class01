# 开发思路
* 通过crontab创建定时任务，周期性执行scrapy crawl myspider。
* 每次爬取前，取出上次这条新闻最新一条评论的时间。爬取评论时，遇到小于等于该时间的，退出爬取。
* 对于查询出的新闻评论，按日期进行分组，查询出每天的数量，传入包含柱状图的模板，进行展示。
* 对于查询出的评论及情感分析得分，设置阈值，确定正负。分别统计出正负的数量，传入包含饼图的模板，进行展示。
* 通过sql的like语法进行筛选，页面上输入关键词，组装sql查询评论内容中包含关键字的数据，在页面上以列表形式展示。