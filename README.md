
## 一、介绍

### 1. 项目介绍

&emsp;&emsp;HotList是基于Python Spider + FastAPI 实现的今日热榜编程接口，项目灵感来自于 [今日热榜](https://tophub.today/c/news) ，API接口涵盖：微博、今日头条、豆瓣、百度、虎嗅、IT之家、BiliBili等全网热点榜单。

&emsp;&emsp;为了确保服务器安全以及控制使用成本，所有接口在请求时需要在请求头中增加许可证信息进行认证。

> 目前已提供平台：
>
> 百度、微博、知乎、豆瓣、BiliBili、人人都是产品经理、IT之家、抖音、虎扑、澎湃新闻、36Kr、少数派、开眼视频


### 2. 版权说明

&emsp;&emsp;所有API接口提供的信息资料、图片及视频等均来源于公开网络，接口仅提供基于类似搜索引擎类的推荐服务，所有详细信息均跳转到原始网页地址访问，不做任何转码类操作，服务器仅存储标题和链接，正文内容不做任何抓取存储，如果侵犯您的权益 ，请与我们联系,我们会尽快处理。同时请注意原网站的观点不表示我们也认同，信息内容真实性请自己辨别。


### 3. 联系我们

- 博客：https://www.zlinblog.cn

- QQ群：1043787769


## 二、接入

### 1. Licence申请

- 可前往 https://api.zlinblog.cn/index

### 2. API地址

- 接口地址：`https://api.zlinblog.cn`

> 后方拼接请求路径；示例：`https://api.zlinblog.cn/hot/v1b1/douban/book/top250`


### 3. Auth Licence

- 请求头Header

| 名称      | 值              |
| --------- | --------------- |
| X-Licence | 3yVabcd1234d597 |


<img src="https://pic.zlinblog.cn/api_example.jpg" alt="api_example"/>


### 4. API接口

| 平台             | 接口名称       | 请求路径                                 | 请求方式 | 数据更新周期 | 状态  |
| ---------------- | -------------- | ---------------------------------------- | -------- | ------------ | ----- |
| 百度             | 热搜           | `/hot/v1b1/baidu`                        | GET      | 10分钟       | √     |
|                  | 小说榜         | `/hot/v1b1/baidu/novel`                  | GET      | 6小时        | √     |
|                  | 电影榜         | `/hot/v1b1/baidu/movie`                  | GET      | 6小时        | √     |
|                  | 电视剧榜       | `/hot/v1b1/baidu/teleplay`               | GET      | 6小时        | √     |
|                  | 汽车榜         | `/hot/v1b1/baidu/car`                    | GET      | 6小时        | √     |
|                  | 游戏榜         | `/hot/v1b1/baidu/game`                   | GET      | 6小时        | √     |
| 微博             | 热搜           | `/hot/v1b1/weibo`                        | GET      | 5分钟        | √     |
|                  | 文娱榜         | `/hot/v1b1/weibo/entertainment`          | GET      | 10分钟       | √     |
|                  | 要闻榜         | `/hot/v1b1/weibo/news`                   | GET      | 10分钟       | √     |
|                  | 话题榜         | `/hot/v1b1/weibo/topic`                  | GET      | 10分钟       | √     |
| 知乎             | 热榜           | `/hot/v1b1/zhihu`                        | GET      | 15分钟       | √     |
| 豆瓣             | 最受关注图书榜 | `/hot/v1b1/douban/book/attention`        | GET      | 24小时       | √     |
|                  | 畅销图书榜     | `/hot/v1b1/douban/book/sale`             | GET      | 24小时       | √     |
|                  | 图书TOP250     | `/hot/v1b1/douban/book/top250`           | GET      | 24小时       | √     |
|                  | 新片榜         | `/hot/v1b1/douban/movie/new`             | GET      | 24小时       | √     |
|                  | 电影TOP250     | `/hot/v1b1/douban/movie/top250`          | GET      | 24小时       | √     |
|                  | 一周口碑榜     | `/hot/v1b1/douban/movie/prestige`        | GET      | 24小时       | √     |
|                  | 北美票房榜     | `/hot/v1b1/douban/movie/usa`             | GET      | 24小时       | √     |
|                  | 音乐250TOP     | `/hot/v1b1/douban/music/top250`          | GET      | 24小时       | √     |
| BiliBili         | 综合热门       | `/hot/v1b1/bilibili/popular`             | GET      | 10分钟       | √     |
|                  | 全站排行       | `/hot/v1b1/bilibili`                     | GET      | 10分钟       | √     |
|                  | 番剧排行       | `/hot/v1b1/bilibili/bangumi`             | GET      | 1小时        | √     |
|                  | 国产动画排行   | `/hot/v1b1/bilibili/guochan`             | GET      | 1小时        | √     |
|                  | 国创相关排行   | `/hot/v1b1/bilibili/guochuang`           | GET      | 1小时        | √     |
|                  | 纪录片排行     | `/hot/v1b1/bilibili/documentary`         | GET      | 1小时        | √     |
|                  | 动画排行       | `/hot/v1b1/bilibili/douga`               | GET      | 1小时        | √     |
|                  | 音乐排行       | `/hot/v1b1/bilibili/music`               | GET      | 1小时        | √     |
|                  | 舞蹈排行       | `/hot/v1b1/bilibili/dance`               | GET      | 1小时        | √     |
|                  | 游戏排行       | `/hot/v1b1/bilibili/game`                | GET      | 1小时        | √     |
|                  | 知识排行       | `/hot/v1b1/bilibili/knowledge`           | GET      | 1小时        | √     |
|                  | 科技排行       | `/hot/v1b1/bilibili/tech`                | GET      | 1小时        | √     |
|                  | 运动排行       | `/hot/v1b1/bilibili/sports`              | GET      | 1小时        | √     |
|                  | 汽车排行       | `/hot/v1b1/bilibili/car`                 | GET      | 1小时        | √     |
|                  | 生活排行       | `/hot/v1b1/bilibili/life`                | GET      | 1小时        | √     |
|                  | 美食排行       | `/hot/v1b1/bilibili/food`                | GET      | 1小时        | √     |
|                  | 动物圈排行     | `/hot/v1b1/bilibili/animal`              | GET      | 1小时        | √     |
|                  | 鬼畜排行       | `/hot/v1b1/bilibili/kichiku`             | GET      | 1小时        | √     |
|                  | 时尚排行       | `/hot/v1b1/bilibili/fashion`             | GET      | 1小时        | √     |
|                  | 娱乐排行       | `/hot/v1b1/bilibili/ent`                 | GET      | 1小时        | √     |
|                  | 影视排行       | `/hot/v1b1/bilibili/cinephile`           | GET      | 1小时        | √     |
|                  | 电影排行       | `/hot/v1b1/bilibili/movie`               | GET      | 1小时        | √     |
|                  | 电视剧排行     | `/hot/v1b1/bilibili/tv`                  | GET      | 1小时        | √     |
|                  | 综艺排行       | `/hot/v1b1/bilibili/variety`             | GET      | 1小时        | √     |
|                  | 原创排行       | `/hot/v1b1/bilibili/origin`              | GET      | 1小时        | √     |
|                  | 新人排行       | `/hot/v1b1/bilibili/rookie`              | GET      | 1小时        | √     |
| 人人都是产品经理 | 日榜           | `/hot/v1b1/woshipm/daily`                | GET      | 12小时       | √     |
|                  | 周榜           | `/hot/v1b1/woshipm/weekly`               | GET      | 5天          | √     |
|                  | 月榜           | `/hot/v1b1/woshipm/monthly`              | GET      | 20天         | √     |
| IT之家           | 阅读榜         | `/hot/v1b1/ithome/read`                  | GET      | 6小时        | √     |
|                  | 最热榜         | `/hot/v1b1/ithome/hot`                   | GET      | 6小时        | √     |
|                  | 打分榜         | `/hot/v1b1/ithome/scores`                | GET      | 6小时        | √     |
| 抖音             | 热点榜         | `/hot/v1b1/douyin/hot`                   | GET      | 5分钟        | √     |
|                  | 种草榜         | `/hot/v1b1/douyin/grass`                 | GET      | 5分钟        | √     |
|                  | 娱乐榜         | `/hot/v1b1/douyin/entertainment`         | GET      | 5分钟        | √     |
|                  | 社会榜         | `/hot/v1b1/douyin/society`               | GET      | 5分钟        | √     |
|                  | 挑战榜         | `/hot/v1b1/douyin/challenge`             | GET      | 5分钟        | √     |
|                  | 地区榜         | `/hot/v1b1/douyin/area?city_code=xxxxxx` | GET      | 5分钟        | doing |
| 虎扑             | 步行街热帖     | `/hot/v1b1/hupu`                         | GET      | 10分钟       | √     |
| 澎湃新闻         | 热榜           | `/hot/v1b1/pengpai`                      | GET      | 20分钟       | √     |
| 36Kr             | 综合榜         | `/hot/v1b1/36kr`                         | GET      | 5分钟        | √     |
|                  | 人气榜         | `/hot/v1b1/36kr/popular`                 | GET      | 5分钟        | √     |
|                  | 收藏榜         | `/hot/v1b1/36kr/collect`                 | GET      | 5分钟        | √     |
| 少数派           | 热榜           | `/hot/v1b1/sspai`                        | GET      | 2小时        | √     |
| 开眼视频         | 日报           | `/hot/v1b2/eye`                          | GET      | 6小时        | √     |


### 5. 返回成功示例

```json
{
  "code": 200,
  "msg": "ok",
  "name": "百度热搜",
  "data":{
      "version": "v1b1",
      "count": 2,
      "date_time": 1698658626,
      "stable": true,
      "list": [
        {
          "title": "  中国将始终是世界发展的重要机遇 "
          "heat": 4966581,
          "link": "https://www.baidu.com/s?wd=%E4%B8%AD%E5%9B%BD%E5%B0%86%E5%A7%8B%E7%BB%88%E6%98%AF%E4%B8%96%E7%95%8C%E5%8F%91%E5%B1%95%E7%9A%84%E9%87%8D%E8%A6%81%E6%9C%BA%E9%81%87&sa=fyb_news&rsv_dl=fyb_news",
          "update_time": 1698658626
        },
        {
          "title": "  中央军委副主席张又侠谈台湾问题 ",
          "heat": 4969282,
          "link": "https://www.baidu.com/s?wd=%E4%B8%AD%E5%A4%AE%E5%86%9B%E5%A7%94%E5%89%AF%E4%B8%BB%E5%B8%AD%E5%BC%A0%E5%8F%88%E4%BE%A0%E8%B0%88%E5%8F%B0%E6%B9%BE%E9%97%AE%E9%A2%98&sa=fyb_news&rsv_dl=fyb_news",
          "update_time": 1698658626
        }
      ]
    }
}
```

| 名称        | 类型       | 说明                      |
| ----------- | ---------- | ------------------------- |
| code        | int        | 返回状态码，成功返回为200 |
| msg         | str        | 返回说明，成功返回为OK    |
| name        | str        | 数据源名称                |
| data        | list[dict] | 数据结果集                |
| version     | str        | 当前接口版本号            |
| count       | int        | 结果数量                  |
| date_time   | datetime   | 数据更新时间（时间戳）    |
| stable      | bool       | 接口是否为稳定版本        |
| list        | list[dict] | 返回结果集                |
| title       | str        | 标题                      |
| heat        | int        | 热度，部分接口没有该字段  |
| link        | str        | 源地址                    |
| update_time | datetime   | 数据爬取时间（时间戳）    |

### 6. 请求报错示例

```json
{
  "code": 100001,
  "msg": "证书不存在",
  "data": [
    {
      "version": "v1b1",
      "stable": true,
      "list": "null"
    }
  ]
}
```

| 名称    | 类型       | 说明                                   |
| ------- | ---------- | -------------------------------------- |
| code    | int        | 返回状态码，详见下方正文错误码         |
| msg     | str        | 返回说明，详见下方正文错误码           |
| data    | list[dict] | 数据结果集                             |
| version | str        | 当前接口版本号                         |
| stable  | bool       | 接口是否为稳定版本                     |
| list    | str        | 返回结果集，接口报错时该字段始终为null |

### 7. 错误码

| 错误码 | 描述                                                   |
| ------ | ------------------------------------------------------ |
| 100001 | 证书不存在                                             |
| 100002 | 证书为未申请状态，请先申请证书                         |
| 100003 | 证书已过期，请重新申请证书                             |
| 100004 | 总请求次数不足，请续费或重新申请证书                   |
| 100005 | 当日剩余请求次数不足，请明日再试                       |
| 100101 | 接口列表获取失败                                       |
| 100102 | 请在请求头中定义X-Licence证书进行认证(X-Licence=xxxxx) |
| -      | -                                                      |
| 200001 | 证书列表为空                                           |
| 200002 | 未找到该证书                                           |
| 200003 | 删除证书失败                                           |
| 200004 | 申请证书失败                                           |
| 200100 | 您已申请过许可证，不可重复申请                         |
| 200200 | 重置免费版每日剩余请求次数：暂无数据可重置             |
| 200201 | 添加证书失败                                           |
| 200202 | 传入证书类型错误                                       |
| 200203 | 证书库存不足，请联系管理员进行补充                     |
| 200204 | 传入证书数量错误                                       |
| 200205 | 目前仅支持申请包月版证书(可免费申请)                   |
| 200206 | 当日剩余数量不足                                       |
| 200207 | 总剩余数量不足                                         |
| -      | -                                                      |
| 300001 | 爬虫数据异常，请联系管理员                             |
| 300002 | 主体网页爬取失败，请检查异常                           |
| 300003 | 部分HTML字段信息爬取失败，请检查异常                   |
| 300004 | HTML网页解析失败，请检查异常                           |
| 300005 | JSON网址解析失败，请检查异常                           |
| 300006 | 网址解析方式出错，请更换网页解析方式                   |
| 300007 | 部分JSON字段信息爬取失败，请检查异常                   |
| 300008 | 请传入地级市区域代码，如110000、440100等               |
| 300100 | 历史过期数据删除失败，请检查异常                       |
| 300110 | 爬虫数据提取失败，请检查异常                           |
| 300120 | 爬虫检查更新失败，请检查异常                           |
| 300130 | 数据读取失败，请检查异常                               |
| -      | -                                                      |
| 400001 | 文件类型错误，仅支持 xls\|xlsx\|csv                    |
| 400002 | 解析失败，请确认是否按照模板正确填写                   |
| 400003 | 解析失败，未解析到Licence证书内容                      |
| 400004 | 证书认证失败，请确认该证书已申请                       |
| 400005 | 请传入数据类型                                         |
| 400006 | 批量导入数据失败，请检查错误                           |
| 400007 | 未找到数据                                             |
| 400008 | 数据删除失败，请重试                                   |
| 400009 | 该许可证上传数据条数已达上限                           |

## 三、捐赠

- 捐赠将用于服务器成本及接口维护成本


<img src="https://pic.zlinblog.cn/ali_juanzeng.jpg" style="zoom:32%;" alt="支付宝"/>
<img src="https://pic.zlinblog.cn/we_juanzeng.jpg" style="zoom:50%;" alt="微信"/>

