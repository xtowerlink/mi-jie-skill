# scripts/

这里放每日增量更新的脚本（待实现）。

## 每日任务（22:00 JST）

1. 读取 `updates/.last_id`（上次处理到的推文 ID）。
2. 拉取 @wr0789（用户 ID 2101591217314336768）在该 ID 之后的新推文，不含转推。
3. 过滤：原创和长文优先；短回复只保留有观点的问答。
4. 生成 `updates/YYYY-MM-DD.md`：
   - 按 M0–M10 归类的要点摘要（转述为主，原句只摘短句）
   - 每条附链接 `https://x.com/wr0789/status/<ID>`
   - 点位或个股观点标“时效性”
5. 在 `references/update-log.md` 表格末尾追加一行；如果出现新的框架性提法，再同步修改 `references/framework.md` 和 `SKILL.md`。
6. 更新 `updates/.last_id`，然后 commit 并推送。

没有新推文的日子不提交。

## 约定

- 不提交原始 JSON 全量数据，也不整篇转载长文。
- 不在仓库里存放任何 token 或密钥。
