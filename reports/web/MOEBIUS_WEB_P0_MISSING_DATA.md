# MOEBIUS_WEB_P0_MISSING_DATA

> 资料缺口分类（不称"需要继续研究"——按 A/B/C/D 分类）
> 2026-09-16 · 仅供 Research Atlas 网页制作决策；不驱动新研究 phase

---

## A. BLOCKING_FOR_WEB（没有它页面无法可靠制作）

- **A1. 1970s 核心作品本地原作扫描缺失**：La Déviation（1973）/ Le Bandard Fou（1974-75）/ Arzach（1975-76）/ The Long Tomorrow（1975-76）/ Garage Hermétique（1979-80）——works.jsonl 中无任何 work_id 直接绑定到 raw/books/ 下的本地扫描；只有 derived/catalogue_pages/9 张拍卖目录渲染（图像 match_status=PENDING）。
  - 影响：SECTION_02_70S 当前只能依赖 derived boards（已在 review/studies/ 中存在）作为视觉证据，不能展示"原作高清扫描页"。
  - 当前缓解：1970s First Pass LOCK 包含 page_hash 锁定数据；review boards 已是研究产出，本身可作 evidence 显示。

- **A2. 1970s/1980s 核心作品 period 模糊（W-S019-615 跨期）**：notes/works/W-S019-615_CiteDeFeu.md 注明属 Garage Hermétique 系列但年份未确定；可能属 70s 末或 80s 初。
  - 影响：SECTION_02/03 边界归属不确定。
  - 缓解：标注 "SECTION_02_70S_OR_SECTION_03_80S" 状态——不强行选边。

## B. DESIRABLE（有更好，没有也可上线）

- **B1. notes/works/ 完整列表**：当前 notes/works/ 仅 11 张 work cards（10 张 S018/S019 catalog + W-1986-MACHINE）；works.jsonl 共 100 行，多数 work 缺独立 work_card.md。
  - 影响：图像资产溯源叙事稍弱。

- **B2. timeline_1970s.html / timeline.html / publications.html 内容文本**：未读取内容；未确认内部是否含本研究需要的 chronology/regime 可视化结构。如已有良好结构可复用；如缺则需新制。

- **B3. 70s Long Tomorrow / Garage Hermétique / Bandard Fou raw pages**：4B ledger 应已有 page_hash 锁定数据；如 raw 文件存在则直接可用；如缺需复检 raw/books 目录。

- **B4. 1990s Stel 1992 original planche 高清扫描**：当前只有 catalog-render（S019_p188_lot613，单图）与 2016 重印（raw/books/2016_world_of_edena/pages/）。原版 planche 是 cat. evidence 的二手页；2016 重印为已上色版本（EDITION_CAVEAT）。
  - 影响：5B 自反结构专论中 Stel planche 的页面级分析受限。

- **B5. Cristal Saga individual plate-front assets**：本地 EXHAUSTED；不可能补足。

- **B6. Works → assets 多对多映射表**：当前 works.jsonl（100）+ assets.jsonl（52）之间无稳定 work_id 绑定（多数 assets.work_id=None）。
  - 影响：网页中"作品-图像"关联查询受限。

## C. INTENTIONAL_UNRESOLVED（研究本身要求保持未知）

- **C1. 1986 machine TITLE/PUBLICATION unresolved**：USER LITERAL DIRECTIVE "不得为了网页重新强行指定题名或出版来源"。状态 OPEN_FROZEN_LOW。
  - 影响：SECTION_03_80S 中 1986 machine 必须以"未署名/未出版图像（OPEN_FROZEN_LOW）"呈现，不得伪造 metadata。

- **C2. Cristal Saga item-level LOCAL unavailable**：Phase 5C 已 EXHAUSTED；本地 10/10 contact sheet 视觉证据存在但 individual plate-front 不可逐件导出。
  - 影响：SECTION_07_CRYSTAL 必须以 corpus-level evidence 呈现，不得逐件 plate front 展示。

- **C3. Body as Narrative Resource 第四层升级门关闭**：FOURTH_LAYER_CANDIDATE_STATUS=NOT_READY；Phase 6B-R fresh-context replication 是 NEXT_GATE。
  - 影响：网页中 BODY_AS_NARRATIVE_RESOURCE 表述必须按"PROJECT_LIMITED_WITHIN_CURRENT_NON_COEUR_90S_TEST"措辞，不得暗示 master model 升级。

- **C4. Reading Discipline 非 Cœur 验证不充分**：NON_COEUR_READING_DISCIPLINE_VALIDATION=INSUFFICIENT；CHARACTER_OR_PUBLIC_INTERPRETATION_NE_WORK_INTERPRETATION 维持 FORMALIZATION_READY 但未正式化。
  - 影响：网页中 READING_DISCIPLINE 候选须显式标注 INSUFFICIENT。

## D. OUT_OF_SCOPE（目前不值得为网站投入）

- **D1. Ciguri 1995 / Griffes d'Ange 1994 / Fifth Element 1997**：本地分别 57pp / 76pp / 不存在；其中 Ciguri/Griffes 故事页区间程序化不可靠；Fifth Element 本地缺失。
  - 影响：直接不进 SECTION；如未来需要，由独立 Phase 处理。

- **D2. image_match_status=PENDING 的 9 张 catalog-render 全集**：当前仅作 evidence support 引用；不投入像素级 crosscheck（属 S019/S018 catalog research 范畴）。

- **D3. publications.jsonl 中 1970s/1980s 局部覆盖**：coverage_status 多为 NONE 或 PARTIAL_IMAGES；为网页制作所需的全书扫描覆盖率不足，但本 P0 不启动扩库。

---

## 缺口处置原则

- C 类（C1-C4）按研究纪律保留，不得因网页需要而"补完"。
- A 类（A1-A2）通过 derived boards 缓解；如未来有 raw 原页可替换。
- B 类按必要性引入下一阶段（仅当不与 C 类冲突时）。
- D 类排除。

---

## CONFLICT 记录

- **CONFLICT_01**：works.jsonl 中无 Cœur/Stel/40 Days/Ciguri/Griffes/Fifth Element 作品级 work_id（核心叙事作品不在 works.jsonl 中）。
  - 处置：当前叙事研究使用 notes/ + raw/books/ + session-level 索引；works.jsonl 主要承载 catalog-render works（拍卖目录溯源）；两套体系并行存在，本 P0 不强行合并。
