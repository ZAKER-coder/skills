# ZAKER News Skills

本项目包含了一组基于 ZAKER 权威资讯库开发的 AI 技能（Skills），旨在为 AI Agent 提供实时、真实、权威的新闻资讯能力。涵盖 24 小时热点头条、行业分类新闻以及精准的关键词新闻检索。

依托权威信源，这些技能能够有效降低 AI 产生信息幻觉（AI 投毒）的风险，非常适合需要快速获取高质量、真实世界新闻的场景。

## 📦 包含的技能 (Included Skills)

本项目 `skills` 目录下包含以下三个核心技能：

### 1. ZAKER 24小时头条新闻 (`zaker-hot-news`)

- **功能**：获取 ZAKER 聚合权威媒体的最新头条新闻与热点资讯。
- **特点**：每 30 分钟更新一次，覆盖国内外重大事件、突发新闻与热点话题。
- **使用场景**：“今天有什么新闻”、“最新头条”、“最近发生了什么大事”。
- **详情文档**：[SKILL.md](./skills/zaker-hot-news/SKILL.md)

### 2. ZAKER 行业热门新闻 (`zaker-category-news`)

- **功能**：按行业维度获取最新热门新闻。
- **支持分类**：科技、财经、体育、娱乐、汽车、国内、国际、军事、互联网等。
- **使用场景**：“科技圈最近有什么趋势”、“股市最近怎么了”、“AI 最近有什么新闻”。
- **详情文档**：[SKILL.md](./skills/zaker-category-news/SKILL.md)

### 3. ZAKER 新闻检索 (`zaker-news-search`)

- **功能**：基于 ZAKER 海量资讯库进行高质量关键词新闻检索，支持指定时间范围（近 30 天内）。
- **特点**：提供精准匹配，避免通用搜索引擎可能带来的低质量信息干扰，适合事实核查。
- **使用场景**：“搜索关于苹果发布会的新闻”、“查一下上周关于股市的报道”。
- **详情文档**：[SKILL.md](./skills/zaker-news-search/SKILL.md)

## ✨ 核心优势 (Core Advantages)

- **权威信源**：数据均来自权威信源，确保信息真实、及时、可信。
- **降低幻觉**：直接调用 ZAKER 接口返回确切的真实新闻数据，从根本上避免 AI 编造新闻。
- **开箱即用**：所有 API 接口均为公开 GET 请求，无需配置 API Key，无鉴权门槛。
- **多维度查询**：支持“全局热点”、“垂直行业”、“精准搜索”三种互补的查询维度，满足不同颗粒度的信息获取需求。

## 🚀 安装与使用 (Installation & Usage)

### 快速安装 (Quick Install)

如果你的开发环境（如 Trae 等 AI Agent 平台）支持 `skills` CLI 工具，你可以直接从 GitHub 快捷安装这些技能：

```bash
# 安装所有 ZAKER 新闻技能
npx skills add <your-github-username>/<your-repo-name>

# 仅安装特定的技能（例如：头条新闻）
npx skills add <your-github-username>/<your-repo-name> --skill zaker-hot-news
npx skills add <your-github-username>/<your-repo-name> --skill zaker-category-news
```

*(请将* *`<your-github-username>`* *和* *`<your-repo-name>`* *替换为你的 GitHub 用户名和本项目所在的仓库名)*

### 手动使用 (Manual Usage)

1. 将本仓库中的 `skills` 目录下的各个技能文件夹导入到您的 Trae 项目或 AI Agent 平台中。
2. 确保运行环境支持执行对应的 Python 或 Shell 脚本（各技能下均提供 `scripts/` 目录）。
3. 在对话中通过自然语言触发对应的意图（例如：“帮我看看今天的头条新闻”），Agent 即会自动匹配并调用相应的技能接口获取数据。

## 📁 目录结构 (Directory Structure)

```text
.
└── skills/
    ├── zaker-category-news/
    │   ├── SKILL.md
    │   └── scripts/
    │       ├── get_category.py
    │       └── get_category.sh
    ├── zaker-hot-news/
    │   ├── SKILL.md
    │   └── scripts/
    │       ├── get_hot.py
    │       └── get_hot.sh
    └── zaker-news-search/
        ├── SKILL.md
        └── scripts/
            ├── search.py
            └── search.sh
```

## 📄 许可证 (License)

MIT License
