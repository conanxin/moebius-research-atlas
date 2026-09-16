# MOEBIUS_WEB_P0_BUILD_HANDOFF

> 下一阶段交接（不写最终 HTML；只给出现状评估与建议下一步单一动作）
> 2026-09-16

---

## BUILD_READINESS

```
BUILD_READINESS = READY_WITH_GAPS
```

理由：
- 主体内容架构（P0_CONTENT_ARCHITECTURE.md）已建立且与现有研究 verdict 严格一致
- 60 项 candidate assets 已审计（30 INDIVIDUAL_PLATE_FRONT + 9 INDIVIDUAL_ARTWORK_RENDER + 21 DERIVED_BOARD）
- 11 项 claim-evidence matrix 已建立（与现有 studies/METHODS 一致）
- 缺口（A 类 BLOCKING / B 类 DESIRABLE）已在 MISSING_DATA.md 显式登记
- C 类 INTENTIONAL_UNRESOLVED 全部按研究纪律保留
- 现有 HTML 文件（index.html / timeline_1970s.html / timeline.html / publications.html）未读取内容——本 P0 未触动

不允许直接进入最终 HTML 制作阶段，除非：
- 用户明示允许
- 或先解决 A 类 BLOCKING（70s 核心作品原作扫描缺失）

---

## HTML_STRATEGY（建议，不修改）

**推荐方案：C. index 作为 portal + 新建 research-atlas.html**

理由：
- A. 替换 index：风险高；现有 index.html / timeline_1970s.html / timeline.html / publications.html 内容未读；可能破坏现有研究浏览工具
- B. 新建 research-atlas.html 但不动 index：避免破坏，但入口分散
- **C. portal 模式**：保留现有 HTML 作为内容入口（index.html 加一行 research atlas 链接），research-atlas.html 作为新主页面——双层结构清晰，对外链接单一
- D. 其他方案（iframe / 静态生成器）：未评估

入口链接建议（index.html 末尾新增一行）：
```
→ Mœbius Research Atlas / 莫比乌斯视觉语言数字研究图谱（推荐作为主页面入口）
```

---

## NEXT_SINGLE_ACTION

```
NEXT_SINGLE_ACTION = 
1. 读取现有 HTML 文件内容（index.html / timeline_1970s.html / timeline.html / publications.html）
2. 评估现有结构是否与 P0 architecture 兼容
3. 如兼容：保留 portal 模式（C），index.html 末尾新增一行入口
4. 如不兼容：单独评估（保留旧 HTML / 改造 / 替换）
```

后续单一动作（非本 P0）：
- 待用户明示后启动 P1 内容与样式实现
- 不下载新图、不修改现有研究 verdict

---

## 本轮输出文件清单

```
reports/web/MOEBIUS_WEB_P0_CONTENT_ARCHITECTURE.md   11 sections + evidence cards + boundaries
reports/web/MOEBIUS_WEB_P0_ASSET_AUDIT.csv           60 candidates (30 PLATE + 9 CATALOG + 21 BOARD)
reports/web/MOEBIUS_WEB_P0_CLAIM_EVIDENCE_MATRIX.csv 11 claims × 6 columns
reports/web/MOEBIUS_WEB_P0_MISSING_DATA.md           A/B/C/D classification + 1 CONFLICT
reports/web/MOEBIUS_WEB_P0_BUILD_HANDOFF.md          this file
```

---

## 停机纪律确认

- 未写最终 HTML ✓
- 未触动现有 HTML ✓
- 未下载新图 ✓
- 未启动新研究 Phase ✓
- 未修改现有研究 verdict ✓
- 未为填网页猜测 unresolved metadata ✓
- 未覆盖旧报告 ✓
- 未删除历史修正记录 ✓

冲突已登记（CONFLICT_01）——works.jsonl 不含核心叙事作品 work_id。
