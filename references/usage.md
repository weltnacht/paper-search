# Paper Search Usage Guide

## English

Use `$paper-search` when you want Codex to search for academic literature, verify paper metadata, and produce a compact summary table.

### Good prompts

```text
Use $paper-search to search and summarize papers on Ga2O3 spectroscopic ellipsometry.
```

```text
Use $paper-search to find recent arXiv papers about altermagnetic spintronics from 2025-01-01 to 2025-06-30.
```

```text
Use $paper-search to build a literature table on temperature-dependent dielectric functions in wide-bandgap semiconductors. Include DOI, journal, keywords, and a one-sentence note.
```

### What to specify

- Topic or research question.
- Material, organism, model, algorithm, or field.
- Method keywords, if important.
- Date range, if the search should be recent or bounded.
- Output language.
- Whether to include all scholarly literature or arXiv-only records.
- Whether to create a Markdown file in the current workspace.

### Default output

For journal and mixed literature searches, the default table is:

```markdown
| # | Date | DOI/Source | Journal | Title | Keywords | Note |
|---:|---|---|---|---|---|---|
```

For arXiv-only searches, the default table is:

```markdown
| # | Date | arXiv | Title | Keywords | Note |
|---:|---|---|---|---|---|
```

### Workflow

1. Infer or confirm the search scope.
2. Search with multiple query variants.
3. Verify DOI, arXiv ID, title, date, and journal or venue from primary metadata sources.
4. Deduplicate repeated preprint and journal records.
5. Write short keyword phrases and one-sentence notes.
6. Add a concise synthesis of themes, chronology, and gaps.
7. Save a Markdown artifact when requested or when the table is large.

### Notes and limits

- The skill is for literature discovery and summary tables, not automatic Zotero import.
- For Zotero archiving or PDF attachment workflows, use the dedicated Zotero or arXiv archiving skill.
- If only weak metadata is available, keep the record out of the main table or mark it as an exploratory lead.

## 中文

当你希望 Codex 检索学术文献、校验论文元数据，并生成紧凑的总结表格时，使用 `$paper-search`。

### 推荐提示词

```text
使用 $paper-search 搜索并总结 Ga2O3 光谱椭偏方向的研究文章。
```

```text
使用 $paper-search 检索 2025-01-01 到 2025-06-30 之间关于 altermagnetic spintronics 的 arXiv 新论文。
```

```text
使用 $paper-search 制作宽禁带半导体温度依赖介电函数方向的文献表，包含 DOI、期刊、关键词和一句话简记。
```

### 建议说明的信息

- 主题或研究问题。
- 材料、体系、模型、算法或学科方向。
- 重要实验方法或计算方法关键词。
- 日期范围，尤其是需要“最新”或限定时间段时。
- 输出语言。
- 是否只要 arXiv 条目，还是包含所有正式论文和预印本。
- 是否需要在当前工作区生成 Markdown 文件。

### 默认输出

正式论文或混合文献检索默认使用：

```markdown
| # | 日期 | DOI/来源 | 期刊 | 标题 | 关键词 | 简记 |
|---:|---|---|---|---|---|---|
```

仅 arXiv 检索默认使用：

```markdown
| # | 日期 | arXiv | 标题 | 关键词 | 简记 |
|---:|---|---|---|---|---|
```

### 工作流程

1. 推断或确认检索范围。
2. 使用多个关键词组合检索。
3. 从 DOI、arXiv、出版社页面或其他主元数据源校验题名、日期、期刊和来源。
4. 去重预印本与正式发表版本。
5. 生成简短关键词和一句话简记。
6. 补充简洁的主题脉络、时间趋势和研究空白总结。
7. 当用户要求或表格较大时，在当前工作区保存 Markdown 文件。

### 注意事项

- 这个 skill 用于文献发现和总结表格，不负责自动导入 Zotero。
- 如果需要 Zotero 归档、PDF 附件或 arXiv-to-Zotero 流程，应使用专门的 Zotero 或 arXiv 归档 skill。
- 如果某条记录只能找到弱元数据，不应强行放入主表；可以作为“待核验线索”单独说明。
