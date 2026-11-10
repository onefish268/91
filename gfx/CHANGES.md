# 改动明细

基准：Steam 创意工坊 91 号 mod 原版文件。
以下“→”左边是原版，右边是改后。

---

## 1. 新增角色：荻花

**common/characters/YSS.txt** 新增 `YSS_dihua`

- 元帅：skill 4 / 进攻 2 / 防御 7 / 计划 4 / 后勤 3
- 特质：organizer 组织专家、infantry_leader 步兵指挥官、urban_assault_specialist 巷战专家、harsh_leader 严军统帅、career_officer 职业军官、inflexible_strategist 顽强的防御者、war_hero 战争英雄
- 内阁：`slot = political_advisor`，特质 `YSS_dihua_guard_commander`“革命近卫军司令”，cost 150
  - 反间谍 +0.5、核心领土防御 +15%、社会主义支持 +0.05、意识形态变化抵制 +10%
- 立绘：`gfx/leaders/YSS/125.png`（156×210）、`126.png`（65×67）

**history/countries/YSS.txt** 新增 `recruit_character = YSS_dihua`

---

## 2. 八云红

| 位置 | 原版 | 改后 |
|---|---|---|
| `YSS_3_6` 元帅 | skill 2，无特质，后勤 5 | skill 4，9 条特质，后勤 6 |
| `YSS_1_44` 内阁 | political_advisor，JAP 特质 | theorist，`YSS_atom_heart`“原子之心”，cost 300 |

`YSS_3_6` 特质：career_officer 职业军官、trait_cautious 谨慎、armor_officer 装甲军官、harsh_leader 严厉的指挥官、aggressive_assaulter 凌厉的攻击者、infantry_leader 步兵指挥官、panzer_leader 装甲指挥官、trait_mountaineer 山地专家、adaptable 强于适应

**history/countries/YSS.txt** 新增 `recruit_character = YSS_1_44`

---

## 3. 茗旧

| 位置 | 原版 | 改后 |
|---|---|---|
| `YSS_6_11` | corps_commander，无特质 | field_marshal，7 条特质 |
| `YSS_1_47` 内阁 | political_advisor，`SWI_commander_in_chief` | theorist，`YSS_mingjiu_commander_in_chief` + `mass_assault_expert`，cost 150 → 300 |

`YSS_6_11` 特质：brilliant_strategist 天才战略家、career_officer 职业军官、aggressive_assaulter 凌厉的攻击者、infantry_leader 步兵指挥官、panzer_leader 装甲指挥官、trait_mountaineer 山地专家、adaptable 强于适应

原版 `SWI_commander_in_chief` 是“陆军防御 +15%”，改成自建特质后为“陆军进攻 +15%”，其余数值保留（陆军经验获取 +0.40、指挥点数获取 +0.07、指挥上限 +30）。

---

## 4. 陵

| 位置 | 原版 | 改后 |
|---|---|---|
| `YSS_7_1` | corps_commander | field_marshal，特质 `logistics_wizard`“后勤奇才” |
| `YSS_1_45` 内阁 | political_advisor，`JAP_modernist_architect`“现代主义建筑师” | 同槽位，改挂 `YSS_ling_architect`“后勤工程师” |

`YSS_ling_architect` 效果：建造速度 +10%、铁路建设 +10%、补给中心建设 +10%、海军基地建设 +10%、补给消耗 -10%。

---

## 5. 自定义特质（common/country_leader/YSS_traits_extra.txt）

| 特质键 | 显示名 | 效果 |
|---|---|---|
| `YSS_mingjiu_commander_in_chief` | 总司令 | 陆军经验 +0.40、陆军进攻 +15%、指挥点 +0.07、指挥上限 +30 |
| `YSS_dihua_guard_commander` | 革命近卫军司令 | 反间谍 +0.5、核心领土防御 +15%、共产主义支持 +0.05、意识形态抵制 +0.10 |
| `YSS_atom_heart` | 原子之心 | 人海突击学说精通 +30%、陆军经验 +0.60 |
| `YSS_ling_architect` | 后勤工程师 | 建造 +10%、铁路/补给中心/港口各 +10%、补给消耗 -10% |

---

## 6. 本地化（localisation/simp_chinese/YSS2_l_simp_chinese.yml）

在文件末尾追加 8 行：4 个特质名 + 4 段描述（§L…§! 格式），文件保持 UTF-8 BOM。

---

## 提交信息参考

```
YSS: add 荻花, rework 八云红/茗旧/陵 as marshals and advisors

- 新增元帅与内阁顾问「荻花」，含立绘
- 八云红、茗旧转为元帅，八云红/茗旧转任理论学家
- 陵转为元帅（后勤奇才），内阁改为「后勤工程师」
- 新增 4 个自定义领袖特质与本地化
```