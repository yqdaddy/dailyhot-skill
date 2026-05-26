---
name: dailyhot
description: 聚合热榜查询 — 从 56+ 中文平台（知乎、微博、B站、抖音等）获取今日热点数据
---

# DailyHot Skill

查询今日热榜数据，支持 56+ 中文内容平台。

## 触发词

"dailyhot", "热榜", "热搜", "热点", "今日热榜", "今日热搜"

## 用法

```bash
# 列出所有可用平台
node scripts/query-hot.mjs --all

# 查询指定平台（默认显示 10 条）
node scripts/query-hot.mjs <platform>
node scripts/query-hot.mjs zhihu
node scripts/query-hot.mjs bilibili
node scripts/query-hot.mjs weibo

# 自定义条数
node scripts/query-hot.mjs zhihu --limit 20

# 指定 API 地址（默认 localhost:6688）
DAILYHOT_URL=http://localhost:3000 node scripts/query-hot.mjs zhihu
```

## 首次使用

1. `cd` 到 dailyhot-skill 目录
2. `npm install` 安装依赖
3. `node scripts/start-server.mjs` 启动本地 API 服务
4. 然后用 `node scripts/query-hot.mjs <platform>` 查询

服务启动后会常驻后台，后续查询无需重复启动。

## 数据源

全部 56 个平台列表（以 `node scripts/query-hot.mjs --all` 实际输出为准）：
- 综合：知乎、微博、百度、抖音、快手、今日头条
- 科技：B站、CSDN、掘金、GitHub、V2EX、HackerNews、ProductHunt
- 媒体：36氪、虎嗅、少数派、IT之家、澎湃新闻、果壳、爱范儿
- 社区：豆瓣、虎扑、贴吧、NGA、吾爱破解、HostLoc、NodeSeek、LinuxDo
- 游戏：原神、崩坏3、星穹铁道、英雄联盟
- 其他：微信读书、地震速报、气象预警、历史上的今天 等

## 数据来源

底层使用 [DailyHot API](https://github.com/imsyy/DailyHotApi) (MIT 协议)，
各平台通过官方公开 API 或公开页面获取热榜数据，默认 60 分钟缓存。
