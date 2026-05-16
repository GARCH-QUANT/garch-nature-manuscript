# Nature Manuscript — 高影响力期刊投稿全流程

Nature / Science / Cell 系列期刊投稿准备 pipeline，覆盖从初稿到接收的全链路。

## 投稿 Pipeline

| 阶段 | 技能 | 功能 |
|------|------|------|
| **引用** | `nature-citation` | 精准匹配 Nature/CNS/Science 期刊文献，导出 ENW/RIS/Zotero RDF |
| **数据可用性** | `nature-data` | Data Availability 声明、FAIR 元数据核查、数据存储库选择 |
| **图表** | `nature-figure` | Python/R 出版级图表，SVG/PDF/TIFF 导出 |
| **PPT** | `nature-paper2ppt` | 论文 → Nature 风格中文 PPT（Journal Club / 组会分享）|
| **润色** | `nature-polishing` | 学术英文润色、结构重构、中译英 |
| **审稿回复** | `nature-response` | 逐点审稿意见回复信起草与审计 |

## 子技能详情

### `nature-citation`
触发词：「分段引用」「Nature系列引用」「补引用」「EndNote」「RIS」「Zotero」
- 段落分句 → DOI 检索（仅 Nature Portfolio / AAAS / Cell Press）
- 批量模式支持 >10 段落

### `nature-figure`
触发词：「paper figure」「Nature style」「publication figure」「multi-panel」
- 后端选择（Python 或 R）作为阻塞门
- SVG/PDF/TIFF 出版级导出

### `nature-polishing`
触发词：「polish manuscript」「英文润色」「学术写作」「中译英」
- Academic Phrasebank 短语库支撑
- Introduction / Results / Discussion 等章节结构优化

### `nature-response`
触发词：「审稿意见回复」「逐点回复」「修回信」「rebuttal」
- 编辑/审稿人意见结构化提取
- 输出状态：`ready_to_submit` / `draft_with_placeholders` / `needs_author_input`

## 使用方式

当用户准备、润色、引用、图示、呈现或修改 Nature 系列期刊稿件时触发本技能。