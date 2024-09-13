## 格式检查
- 块前缺少空行的表格：`\S+\n.*?\|.*?\n.*?---`
- 统计参数：
  - `https://meta\.appinn\.net/(?=([^?)# ]+))\1(?!\?u=chaoses_ib)` -> `$0?u=chaoses_ib`
  - `https://resource\.dopus\.com/(?!uploads/)(?=([^?)# ]+))\1(?!\?u=chaoses-ib)` -> `$0?u=chaoses-ib`