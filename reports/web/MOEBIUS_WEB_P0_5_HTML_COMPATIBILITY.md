# MOEBIUS_WEB_P0_5 · HTML 兼容性 + 既有页面关系

2026-09-16 · 完整读取 index.html / timeline_1970s.html / timeline.html / publications.html

## 一、4 个 HTML 完整结构摘要

### index.html（82,411 bytes）

**页面作用**：portal + 1980s core corpus 入口 + 1986 machine investigation 状态展示

**HTML structure**：
- 完整 inline `<style>`（无外部 CSS）—— 含 `.section / .disclaimer / .card / .work-card / .badge / .pdf-card / .timeline-row / .cand-table` 等
- 字体：`14px/1.5 -apple-system,Segoe UI,Roboto,sans-serif` · background `#f7f6f2` · 浅米黄基调
- 完全纯静态、无 build system、无 JS 框架；唯一 JS 是过滤卡片显示（约 20 行 vanilla JS）
- `viewport: width=device-width,initial-scale=1` —— mobile/desktop 可读（CSS 已有 `auto-fill,minmax(220px,1fr)` grid）

**navigation**：硬编码入口链接（无 shared nav）
- Mœbius Research Model 卡片 → studies/MOEBIUS_MASTER_MODEL.md, METHODS/MOEBIUS_ARCHIVE_RESEARCH_PROTOCOL.md, studies/1970S_FIRST_PASS_LOCK.md 等 8 个 .md 文件
- Start Here 卡片 → timeline_1970s.html / timeline.html / publications.html / studies/STUDY-02-1980S-TRANSFORMATIONS.md / notes/LEAD-1986-MACHINE-CANDIDATES.md 等
- 底部 Phase 2A 链接 → timeline.html / publications.html / studies/READING_QUEUE_1980S.md / studies/STUDY-01-MACHINES-1980S.md
- 重要：**P1D/P1C 1986 machine investigation 块已 inline 在 index.html**（含 Tumblr/Pinterest 调查 + 19 evidence matrix）

**inline data**：所有内容 inline，无 JSON loading

**asset references**：
- images: `raw/images/I00X.jpg` + `thumbs/I00X.jpg`（缩略图）+ `raw/books/the_art_of_moebius_1989/pages/AOM00XX.jpg`
- notes/works/ PDF 内嵌链接：`raw/pdfs/S018.pdf#page=77` 等

**shared components**：NONE（所有样式 inline，无 partials）

**external dependencies**：NONE（无 CDN、无 Google Fonts、无外部 CSS/JS）

**font handling**：纯 system-ui stack；无 webfont

**responsive behavior**：CSS grid `auto-fill,minmax()`；无 media queries —— **依靠 grid 自适应**

### timeline_1970s.html（6,026 bytes）

**页面作用**：1970s First-Pass LOCK 浏览工具 + 视觉证据入口

**HTML structure**：
- inline `<style>`：dark theme（`background:#14120f;color:#e8e0d0` · accent `#d8b25a`）
- `.card / .A_CONFIRMED / .B_CONTEXTUAL / .C_UNRESOLVED` 三级视觉证据分级（left border colors）
- 完全纯静态，无 JS

**asset references**：12 张图：
- `studies/1970S_MASTER_ARC.jpg / 1970S_INFORMATION_REGIMES.jpg / 1970S_STABLE_HAND.jpg`（derived boards）
- `../raw/books/the_art_of_moebius_1989/pages/AOM0013-16/AOM0032.jpg`（**TAOM 1989 reproduction pages**——TAOM 是 1989 Moebius Production 出版的 repro 选集，作为 1975-79 works 的合法来源）
- `../raw/images/I002/I003/I003.jpg` + `7c3a762b2bda6a6d.jpg` + `1be6406530a915c1.jpg`（harvested from moebius.fr）

**核心发现**：9 件 1970s canonical works 的视觉证据来自两条链：
- TAOM 1989 reproduction（A_CONFIRMED 5 件：W-70S-ASF, W-70S-LT-01/02, W-70S-WINTER）—— **publication-level reproduction page**
- moebius.fr harvest（A_CONFIRMED 3 件：W-70S-CARNET-76, W-70S-ARZ-02；B_CONTEXTUAL 1 件：W-70S-DUNE）

### timeline.html（19,399 bytes）

**页面作用**：1980s timeline 浏览（同一 dark theme，但内容不同）

**asset references**：与 timeline_1970s 共享 CSS，但 80s 卡片图源更杂：
- `raw/images/I004/I005` 等
- `raw/books/the_art_of_moebius_1989/pages/AOM0017/0018/0019/0026/0064/0068`
- `raw/web/p1f/fm_124535/124538/124542/124543`（Futurs Magiques contact sheet harvest）
- `raw/web/p1f/cristal_03/05`（**已知 = PACKAGE + MONTAGE**，不可作 PLATE_FRONT** —— 见 Phase 5C 教训）
- `raw/web/p1g/hb_lots-077.png` + abebooks listings
- `raw/web/p1i/70s_target_1280.jpg`

**注意**：timeline.html 含 cristal_03/05 引用 —— 这与 Phase 5C "asset_role must be INDIVIDUAL_PLATE_FRONT" 教训冲突；P1 不得直接复用 timeline.html 的 cristal 引用作为 SECTION_07 视觉证据。

### publications.html（14,325 bytes）

**页面作用**：出版物索引（card-based）

**HTML structure**：
- inline `<style>`：light theme（`background:#fafafa` · accent `#3498db`）
- `.pub-card.full / .partial / .metadata / .none`（coverage 四级）

**asset references**：**无 img 引用** —— 纯文本 + 链接

**导航作用**：publication-level 浏览工具；与 research-atlas.html 无视觉资源冲突

## 二、HTML 关系图

```
                   index.html (82KB)
                    │
        ┌───────────┼────────────┬──────────────┐
        ↓           ↓            ↓              ↓
   timeline_1970s.html  timeline.html  publications.html  studies/*.md
   (6KB · dark theme)  (19KB · dark)  (14KB · light)   (referenced from cards)
        │              │
        └──────┬───────┘
               ↓
       raw/books/the_art_of_moebius_1989/pages/ (TAOM 1989 repro)
       raw/images/I00X.jpg (moebius.fr harvest)
       raw/web/p1f/* (P1F harvest)
```

## 三、HTML_STRATEGY 验证

候选 C（保留现有 HTML 作 portal + 新建 research-atlas.html）**与实际代码兼容**，理由：

- ✅ index.html 已是 portal（Mœbius Research Model 8 卡片 + Start Here 6 卡片 + 底部 Phase 2A 链接）
- ✅ timeline_1970s.html 与 timeline.html 已存在 70s/80s 浏览工具；无需重制
- ✅ publications.html 已提供 publication-level 入口
- ✅ 所有现有 HTML 是纯静态 + 系统字体，无 build system
- ✅ mobile 通过 CSS grid `auto-fill,minmax()` 自适应；无需新框架
- ⚠️ **注意**：timeline_1970s.html 与 timeline.html 的 dark theme 与 index.html / publications.html 的 light theme 不同；**research-atlas.html 应与 index.html 同色系（light theme），与两个 timeline dark theme 形成清晰层级**

## 四、复用 CSS / 共享 nav 评估

**不建议**：现有 CSS 全部 inline + 每页独立；复制到 research-atlas.html 会引入 CSS 重复与不一致。建议 research-atlas.html：
- 使用独立 inline CSS（与 index.html light theme 同色系）
- 不引入 shared nav（保持 portal 简洁）
- image path 用相对路径 `../raw/...` 或 `images/...`（与现有约定一致）

## 五、build system / framework 评估

- 所有 4 个 HTML **零依赖**（无 CDN / 无 build tool / 无 framework / 无 webfont）
- 完全 file:// 兼容
- 完全 static hosting 兼容
- mobile/desktop 通过 CSS grid 自适应

**原则维持**：research-atlas.html 同样保持 plain HTML/CSS/JS；不引入 React / Vue / Next / Tailwind / build tool。

## 六、可行新增入口方式

最小改动方案：

在 index.html **Mœbius Research Model 8 卡片块末尾或 Start Here 块顶部**新增一行卡片：
```html
<a href="research-atlas.html" style="...">
  <strong>▸ Research Atlas</strong><br/>
  <span>...（副标题与简短描述）...</span>
</a>
```

不需要修改任何现有 .md / .csv / .jsonl 文件。

## 七、image path convention 确认

- 现有约定：image refs 用相对路径（`../raw/...` 从 timeline_1970s.html；`raw/images/...` 从 index.html）
- research-atlas.html 建议统一为 `../raw/...`（与两个 timeline 一致；与 publications.html 无图片引用也兼容）
