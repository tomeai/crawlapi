## CrawlAPI

```
1. 爬虫调度 调度浏览器
2. 定时任务
3. 任务中心 承接 golang爬虫 浏览器爬虫  scrapy爬虫    scrapy插件
    1. 失败收集  
    2. 下发 从数据库查询 写到redis  任务表统一
4. 解析器注册 拆分？ serverless

--- 暂时不开发？  之前的crawl-let
5. 爬虫注册  golang       可以使用 serverless节省资源吗  调用 http 接口  使用阿里云的消息队列？？？
    1. 调用 解析器中心
    2. 可以接收任务中心下发的任务
```