# MOEBIUS_WEB_P0_5 · W-S019-615 审计

## 元数据记录（verbatim 摘自 works.jsonl + notes/works/W-S019-615_CiteDeFeu.md）

| 字段 | 值 |
|---|---|
| work_id | W-S019-615 |
| 中文描述名 | La Cité de feu 第 6 图 « La Volière/Le Garage »（Aedena 1985 portfolio 替代上色稿） |
| formal_title_source | La Cité de feu — illustration n°6 « La Volière/Le Garage » |
| series | Aedena portfolio（涉及 Starwatcher / Major Fatal / Le Monde d'Edena / Arzach） |
| year | 1985 |
| year_nature | portfolio publication year |
| medium | Encres de couleur sur fond d'impression avec rectificatif à l'encre de Chine et à la gouache blanche |
| dimensions | 52,8 × 35,7 cm |
| signature_observed | 未在该图录条目中标注签名 |
| lot_number | 615 |
| identity_status | SOURCE_IDENTIFIED |
| date_status | PUBLICATION_YEAR_ONLY |
| image_match_status | PENDING |
| publication_verified_by | 无 |
| in_1980s_corpus | True |

## 作品卡片 notes/works/W-S019-615_CiteDeFeu.md 摘录

> La Cité de feu — illustration n°6 « La Volière/Le Garage » —— mise en couleur alternative pour l'illustration publiée aux Éditions Aedena en 1985.
> L'artiste a effectué quelques rectifications pour la version définitive publiée.
> Grande composition où l'on retrouve les personnages de l'univers de Moebius : Starwatcher, Major Fatal, Le Monde d'Edena et Arzach.
> Ce portfolio est une collaboration avec Geof Darrow.

## 在本地研究中的引用

- **index.html**：图录 S019 lot 615 工作卡（详见 index.html 中 `.work-card[data-work-id="W-S019-615"]`）—— 已显示 publication_level_only
- **P0 ASSET_AUDIT.csv**：作为 SECTION_03_80S 候选（catalog-render W-S019-615, INDIVIDUAL_ARTWORK_RENDER, image_match_status=PENDING）
- **timeline.html**：未直接出现 615 引用（80s timeline 主要用 AOM 1989 repro pages）

## IS_W_S019_615_REQUIRED_FOR_P1 判定

**IS_W_S019_615_REQUIRED_FOR_P1 = YES**

理由：
1. SECTION_03_80S 目标 = "same year / different task / different information regime"；该作品 portfolio 性质 + Geof Darrow 协作 + 替代上色稿 是 1985 task-conditioned variation 的明确证据
2. catalogue-render W-S019-615（INDIVIDUAL_ARTWORK_RENDER）是 SECTION_03 候选资产之一
3. 已有 work_card_md + S019 图录 lot 描述 + 1985 Aedena portfolio publication metadata

## period 是否可以可靠修正？

**RESOLVED_FROM_EXISTING_EVIDENCE** —— period = 1980s decade

理由：
- 图录 S019 lot 615 明确：portfolio « La Cité de feu » publié aux Éditions Aedena **en 1985**
- year_nature = "portfolio publication year"（1985 是 portfolio 出版年）
- date_status = PUBLICATION_YEAR_ONLY（creation year 未独立确认）
- in_1980s_corpus = True（projects rule 接受 1985 publication 作为 80s 分类基础）

## 但 creation year 与 publication year 不一致的可能性

图录 S019 未给出 creation year。Geof Darrow 协作（crayonnés sur calque）暗示作品有草图→上色稿→定稿的多阶段过程；creation year 可能在 1984 或 1985。

**为 P1 保留的措辞**：
- publication_year = 1985（已 verified）
- creation_year = UNRESOLVED_1984_OR_1985

**做法**：在 SECTION_03 引用时标注"1985 Aedena portfolio publication；creation year unresolved"。

## A2_STATUS

**A2_STATUS = RESOLVED_FROM_EXISTING_EVIDENCE**

不再阻塞 P1——P1 仅需 decade-level period；1985 publication year 已 verbatim 来自图录 S019。

若未来需要 pixel-level same-work-crosscheck（带 publication_level 独立证据），则仍属于 D2 OUT_OF_SCOPE 类（不为网页投入）。

## A2 是否被 P1 safe set 排除？

不排除。W-S019-615 保留在 SECTION_03_80S 候选中。措辞保留：
- "W-S019-615 — La Cité de feu illustration n°6 (Aedena 1985 portfolio, alternative coloring; creation year unresolved)"
- 配 catalog-render `derived/catalogue_pages/S019_p190_lot615_Moebius_CiteDeFeu-190.jpg` 标注：image_match_status=PENDING
