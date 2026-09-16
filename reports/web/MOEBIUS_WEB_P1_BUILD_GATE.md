# MOEBIUS_WEB_P1_BUILD_GATE

> P0.5 完成后的最终 build gate 决议
> 2026-09-16

## A1_STATUS

```
A1_STATUS = PARTIALLY_RESOLVED
```

理由：
- timeline_1970s.html 已通过两条链承载 1970s canonical works 的视觉证据：
  - TAOM 1989 reproduction pages（AOM0013-16, AOM0032，5 件）—— publication-level reproduction，acceptable as visual evidence with TAOM 1989 caption
  - moebius.fr harvest（I002, I003, harvest_*, 4 件）—— full_artwork SITE_HARVEST，部分 identity_status=UNRESOLVED
- 6/9 件达到 P1_SAFE=YES（A_CONFIRMED + full_artwork/reproduction + SHA verified）
- 3/9 件 P1_SAFE=NO（B_CONTEXTUAL only: W-70S-ASF-COM, W-70S-DUNE, W-70S-ARZ-01）

## A1_70S_WORKS_WITH_SAFE_VISUALS

```
W-70S-ASF (1975 · Art and Science-Fiction · TAOM 1989 repro)
W-70S-CARNET-76 (1976 · Carnet · moebius.fr harvest · I003)
W-70S-LT-01 (1975-76 · The Long Tomorrow plate 1 · TAOM 1989 repro)
W-70S-LT-02 (1975-76 · The Long Tomorrow cityscape · TAOM 1989 repro)
W-70S-WINTER (1979 · Winter Couple · TAOM 1989 repro)
W-70S-ARZ-02 (1975-76 · Arzak desert village · moebius.fr harvest)
```

## A1_70S_WORKS_WITH_DERIVED_ONLY

```
W-70S-ASF-COM (1975 · commentary page · B_CONTEXTUAL · P1 safe=no)
W-70S-DUNE (1975-76 · Dune concept · B_CONTEXTUAL · P1 safe=no)
W-70S-ARZ-01 (1975-76 · Arzak profile · B_CONTEXTUAL · P1 safe=no)
```

这 3 件不是 SECTION_02 必需 claim 视觉证据：
- W-70S-ASF-COM = commentary page（独立 supporting evidence，非核心 claim 视觉）
- W-70S-DUNE = unrealized Jodorowsky Dune production（边缘 case）
- W-70S-ARZ-01 = moebius.fr Arzak profile（仅 side visual；Arzach 主体已由 W-70S-ARZ-02 覆盖）

故 SECTION_02 5 件核心作品（Déviation/Bandard/Arzach/Long Tomorrow/Winter Couple）核心视觉证据齐全；
P0 记录的 5 件核心作品中：
- **Déviation** 已有 P1 visual: 6 张 P6B-R2 Stel 等价的 book-page scans（不对——Stel 是 90s；Déviation 无本地 raw scans）
- **Bandard Fou** 同上，无本地 raw scans
- **Arzach** = W-70S-ARZ-02 ✅
- **Long Tomorrow** = W-70S-LT-01 + LT-02 ✅
- **Garage Hermétique** = 无 canonical 在 70s timeline 中（Garage 主在 80s timeline.html）

## SECTION_02 视觉缺口（修正）

重新评估 SECTION_02 真实需要：
- **La Déviation**（5B 唯一证据 = C1+C7 POROUS 自反结构）—— 无本地 raw scan；
  SECTION_02 P1 safe visual = **TEXT_ONLY_IN_P1**（仅引用 5B claim ledger + La Déviation P4 verified 7p）
- **Le Bandard Fou** —— 无本地 raw scan；
  P1 safe visual = **TEXT_ONLY_IN_P1**（仅引用 phase 3B claim ledger）
- **Arzach** ✅ W-70S-ARZ-02 (P1_SAFE)
- **Long Tomorrow** ✅ W-70S-LT-01 + LT-02 (P1_SAFE)
- **Garage Hermétique** —— 70s timeline 未列 Garage；
  Garage 主证据在 Phase 3B 的 1980s Garage Hermétique pages（122p verified，1979-80 跨期）；
  SECTION_02 P1 safe visual = **TEXT_ONLY_IN_P1** + 5A Strange Object Readability case
- **其他 70s works**（WINTER 1979）✅

## A2_STATUS

```
A2_STATUS = RESOLVED_FROM_EXISTING_EVIDENCE
```

W-S019-615 = 1985 Aedena portfolio publication year；SECTION_03_80S 候选；
creation year unresolved 但 P1 不需要。
**不阻塞 P1。**

## W_S019_615_REQUIRED_FOR_P1

```
W_S019_615_REQUIRED_FOR_P1 = YES
```

（保留为 SECTION_03_80S 1985 portfolio + Geof Darrow 协作 + 替代上色稿 = 1985 task-conditioned variation 证据；
caption 必须标注 "1985 Aedena portfolio publication; creation year unresolved"）

## HTML_STRATEGY

```
HTML_STRATEGY = C
```

index.html + timeline_1970s.html + timeline.html + publications.html 保留作 portal；
新建 research-atlas.html 作 Research Atlas 主页面；
最小改动入口：在 index.html Start Here 块顶部新增一行卡片链接到 research-atlas.html。

兼容性确认：
- ✅ 现有 HTML 纯静态、零依赖、file:// 兼容、static hosting 兼容
- ✅ mobile/desktop 通过 CSS grid `auto-fill,minmax()` 自适应
- ✅ research-atlas.html 与 index.html 同 light theme（与两个 timeline dark theme 形成清晰层级）
- ✅ image path 用相对路径 `../raw/...`（与 timeline_1970s 一致）

## SAFE_ASSETS

```
P1_SAFE_ASSETS = 36 (P1_SAFE=YES)
P1_CONDITIONAL_ASSETS = 30 (P1_SAFE=CONDITIONAL — catalog-renders + derived boards)
P1_EXCLUDED_ASSETS = 3 (P1_SAFE=NO — 3 B_CONTEXTUAL 70s cards)
TOTAL = 69
```

## SECTION02_VISUAL_STATUS

```
SECTION02_VISUAL_STATUS = PARTIALLY_VISUAL + PARTIALLY_TEXT_ONLY
```

| 核心作品 | P1 视觉策略 |
|---|---|
| Arzach | ✅ visual (W-70S-ARZ-02) |
| Long Tomorrow | ✅ visual (W-70S-LT-01 + LT-02) |
| Winter Couple (1979) | ✅ visual (W-70S-WINTER) |
| La Déviation | TEXT_ONLY_IN_P1（5B claim ledger 引用 + verified 7p 已 hash 锁定，无 raw 扫描） |
| Le Bandard Fou | TEXT_ONLY_IN_P1（phase 3B claim ledger 引用） |
| Garage Hermétique | TEXT_ONLY_IN_P1（Garage 主期 1979-80 在 timeline_1980s.html；SECTION_02 引用 claim ledger） |

## EXISTING_HTML_COMPATIBILITY

```
EXISTING_HTML_COMPATIBILITY = HIGH
```

- 所有 4 个现有 HTML 纯静态、零依赖
- 完全 file:// + static hosting 兼容
- mobile/desktop 通过 CSS grid 自适应
- 无 build system 干扰
- 不引入框架（保持 plain HTML/CSS/JS）

## P1_BUILD_GATE

```
P1_BUILD_GATE = GO_WITH_EXPLICIT_LIMITATIONS
```

理由：
- P1 可构建（GO）；但以下显式限制必须出现在研究页面：

### Limitations（必须在 research-atlas.html 中显式标注）

1. **SECTION_02 部分作品 TEXT_ONLY**：
   - La Déviation / Bandard Fou / Garage Hermétique 在 P1 无独立原作扫描 visual evidence；
   - 必须以"text-only"形式呈现，引用 5B claim ledger + phase 3B 锁定文档；
   - 不为网页完整性伪造 visual evidence
2. **70s visual evidence caption 必须标注来源**：
   - TAOM 1989 reproduction pages 必须 caption 为 "1989 reproduction from The Art of Moebius (Moebius Production)"；
   - moebius.fr harvest full_artwork 必须 caption 为 "source: moebius.fr · harvest asset";
   - 不得隐去来源
3. **catalog-renders 全部 CONDITIONAL**：
   - W-S018-153 Starwatcher / W-S019-612 Voyage Corps / W-S019-613 Stel planche 23 等 9 件均 caption 为
     "identity SOURCE_IDENTIFIED · image_match_status=PENDING";
   - 不得当作 verified original artwork
4. **cristal_03 / cristal_05 引用清理**：
   - timeline.html 中含 cristal_03/05 引用（已 Phase 5C 证实 = PACKAGE + MONTAGE）；
   - research-atlas.html SECTION_07 不得复用 timeline.html 的 cristal 引用作为 PLATE_FRONT visual evidence
5. **timeline.html 中 1986 machine 调查块**：保持 OPEN_FROZEN_LOW，不更新题名/出版

### Required research-atlas.html 显式边界标注

页面顶部 disclaimer 必须含：
```
Master Model = SUPPORTED_WITH_LIMITS（WORKING_MODEL）
Body as Narrative Resource = PROJECT_LIMITED_WITHIN_CURRENT_NON_COEUR_90S_TEST
Stel = MEETS_THRESHOLD · 40 Days = DOES_NOT_MEET_THRESHOLD
1986 machine：artist confirmed · signed date 1986 · title unresolved · publication unresolved
Cristal Saga：corpus-level evidence strong · item-level local asset mapping EXHAUSTED
```

## NEXT_SINGLE_ACTION

```
NEXT_SINGLE_ACTION = 
研究页面内容与样式实现（research-atlas.html）需用户明示后启动
本轮（Web P0.5）已解决 P1 入口阻塞；
P1 不需新增下载 / 不需修改现有 verdict / 不需修改现有 HTML；
按 GO_WITH_EXPLICIT_LIMITATIONS 决议制作 research-atlas.html
```
