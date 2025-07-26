## CrawlAPI

```
1. 爬虫调度
    1. 调度浏览器
    2. 调度ins 等
    3. 定时调度
2. 定时任务
3. 任务中心 承接 golang爬虫 浏览器爬虫  scrapy爬虫    scrapy插件  （只承接任务）
    1. 失败收集  
    2. 下发 从数据库查询 写到redis  任务表统一

--- 暂时不开发？  之前的crawl-let   这里和crawl-api合并  具体干活交给 scrapy和golang客户端
4. 爬虫注册  golang       可以使用 serverless节省资源吗  调用 http 接口  使用阿里云的消息队列？？？
    1. 调用 解析器中心
    2. 可以接收任务中心下发的任务
    3. 尝试使用serverless进行改造
5. 解析中心   插件化注册
```

## 规划

```
crawlapi 对接 relyapi crawlet scrapy  都是主动查询
    1. crawl-agent   redis lbpop   
        1. crawl-agent 挂载了爬虫 （挂载的真实设备）
    2. crawlet 也是查询 redis   注册更新爬虫 不影响其他爬虫
        1. 挂载 golang爬虫
    3. scrapy也是查询 redis   注册更新爬虫 不影响其他爬虫
        1. 挂载 python爬虫

主动拉取任务  从数据库查询
```

## 设计

```
# blpop  客户端统一使用blpop接收
https://github.com/rmax/scrapy-redis/blob/c3064c2fa74e623bf14448d82cc07ca2da8e183d/src/scrapy_redis/scheduler.py
```

## 参考

```
https://github.com/bxcodec/go-clean-arch/blob/master/internal/repository/mysql/article.go
```