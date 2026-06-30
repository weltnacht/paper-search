# Paper Search

Paper Search is a Codex skill for finding, verifying, and summarizing academic literature. It turns a research question into a compact, source-backed paper table in a Zotero/arXiv-Archive style.

## What It Does

- Searches academic papers, preprints, DOIs, and arXiv records by topic, method, material, date range, or field.
- Verifies metadata from primary sources such as Crossref, arXiv, publisher pages, PubMed, or official repository records.
- Deduplicates overlapping preprint and journal records.
- Produces concise Markdown tables with date, DOI/source, journal, title, keywords, and one-sentence notes.
- Supports all-literature tables and arXiv-only tables.
- Includes a bilingual usage guide in `references/usage.md`.

## When To Use

Use this skill when you want Codex to:

- Search for papers on a research topic.
- Build a literature-review table.
- Summarize recent papers in a field.
- Verify DOI, arXiv, journal, and publication-date metadata.
- Create a reusable Markdown literature-search artifact.

## Example Prompts

```text
Use $paper-search to search and summarize papers on Ga2O3 spectroscopic ellipsometry.
```

```text
Use $paper-search to find recent arXiv papers about altermagnetic spintronics from 2025-01-01 to 2025-06-30.
```

```text
Use $paper-search to build a literature table on temperature-dependent dielectric functions in wide-bandgap semiconductors. Include DOI, journal, keywords, and a one-sentence note.
```

## Default Table Formats

For journal and mixed literature searches:

```markdown
| # | Date | DOI/Source | Journal | Title | Keywords | Note |
|---:|---|---|---|---|---|---|
```

For arXiv-only searches:

```markdown
| # | Date | arXiv | Title | Keywords | Note |
|---:|---|---|---|---|---|
```

## Skill Files

- `SKILL.md`: Core workflow and triggering instructions.
- `agents/openai.yaml`: Codex UI metadata.
- `references/usage.md`: Bilingual usage guide, English first and Chinese second.

## License

This project is released under the MIT License.

# Paper Search 中文介绍

Paper Search 是一个用于文献检索、元数据校验和论文表格总结的 Codex skill。它可以把一个研究问题整理成紧凑、可追溯的 Zotero/arXiv Archive 风格文献表。

## 功能

- 按主题、方法、材料、日期范围或学科方向检索论文、预印本、DOI 和 arXiv 条目。
- 从 Crossref、arXiv、出版社页面、PubMed 或官方仓储记录中校验元数据。
- 去重预印本与正式发表版本。
- 生成包含日期、DOI/来源、期刊、标题、关键词和一句话简记的 Markdown 表格。
- 支持混合文献表和仅 arXiv 文献表。
- 在 `references/usage.md` 中提供英文在前、中文在后的双语使用说明。

## 适用场景

当你希望 Codex 完成以下任务时，可以使用这个 skill：

- 检索某个研究方向的论文。
- 制作文献综述表格。
- 总结某个领域的近期论文。
- 校验 DOI、arXiv、期刊和发表日期等元数据。
- 在当前工作区生成可复用的 Markdown 文献检索结果。

## 示例提示词

```text
使用 $paper-search 搜索并总结 Ga2O3 光谱椭偏方向的研究文章。
```

```text
使用 $paper-search 检索 2025-01-01 到 2025-06-30 之间关于 altermagnetic spintronics 的 arXiv 新论文。
```

```text
使用 $paper-search 制作宽禁带半导体温度依赖介电函数方向的文献表，包含 DOI、期刊、关键词和一句话简记。
```

## 默认表格格式

正式论文或混合文献检索：

```markdown
| # | 日期 | DOI/来源 | 期刊 | 标题 | 关键词 | 简记 |
|---:|---|---|---|---|---|---|
```

仅 arXiv 检索：

```markdown
| # | 日期 | arXiv | 标题 | 关键词 | 简记 |
|---:|---|---|---|---|---|
```

## 文件结构

- `SKILL.md`：核心工作流程和触发说明。
- `agents/openai.yaml`：Codex UI 元数据。
- `references/usage.md`：双语使用说明，英文在前，中文在后。

## 许可证

本项目使用 MIT License 发布。
