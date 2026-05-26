# DailyHot Skill

Claude Code 技能封装 — 聚合 56+ 中文平台热榜数据。

## 快速开始

```bash
npm install
node scripts/start-server.mjs
node scripts/query-hot.mjs zhihu
```

## 目录结构

```
dailyhot-skill/
├── dailyhot.md              # Claude Code skill 定义
├── scripts/
│   ├── start-server.mjs     # 启动 API 服务
│   └── query-hot.mjs        # 查询热榜并格式化输出
├── package.json
└── .gitignore
```

## 安装到 Claude Code

将本仓库 clone 后，把 `dailyhot.md` 复制到项目的 `.claude/skills/` 目录，
或在 Claude Code 中手动引用该文件路径。

## License

本项目代码 MIT，底层 DailyHot API 同样 MIT。
