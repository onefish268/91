# 改动明细（2026-11-10）

mod：钢铁萌心：狂野法则（`descriptor.mod` version 1.19.3，workshop id 3772620704）

---

## 1. `common/characters/YSS.txt`

### YSS_1_44 八云红 — 内阁顾问 → 理论学家

| 字段 | 改前 | 改后 |
|---|---|---|
| `slot` | `political_advisor` | `theorist` |
| `traits` | `HUN_internationalist_marxist` | `YSS_atom_heart` |
| `cost` | 150 | 300 |

新特质「原子之心」：人海突击学说精通度 +30%（原版 `mass_assault_expert` 的两倍）、陆军经验增长 +0.60。

### YSS_1_47 茗旧 — 内阁顾问 → 理论学家

| 字段 | 改前 | 改后 |
|---|---|---|
| `slot` | `political_advisor` | `theorist` |
| `traits` | `SWI_commander_in_chief` | `YSS_mingjiu_commander_in_chief` + `mass_assault_expert` |
| `cost` | 150 | 300 |

`YSS_mingjiu_commander_in_chief` 是原版「总司令」的进攻版：把 `army_defence_factor = 0.15` 换成 `army_attack_factor = 0.15`，
其余（陆军经验 +40%、指挥点增长 +7%、指挥上限 +30）不变。
`mass_assault_expert` 用原版键，自带 +15% 人海突击精通度。

### YSS_3_6 八云红 — 陆军元帅

- `skill`：2 → 4
- `traits`：原本为空，现为 9 条

```
traits = {
    career_officer          # 职业军官
    trait_cautious          # 谨慎
    armor_officer           # 装甲军官
    politically_connected   # 政治关联者
    aggressive_assaulter    # 凌厉的攻击者
    infantry_leader         # 步兵指挥官
    panzer_leader           # 装甲指挥官
    trait_mountaineer       # 山地专家
    adaptable               # 强于适应
}
```

数值未动：attack 6 / defense 6 / planning 6 / logistics 5。

### YSS_6_11 茗旧 — 军长 → 陆军元帅

- 角色块 `corps_commander` → `field_marshal`（`aggressive_assaulter` 是元帅专属特质，挂在军长上不生效）
- `traits`：原本为空，现为 7 条

```
traits = {
    brilliant_strategist    # 天才战略家
    career_officer          # 职业军官
    aggressive_assaulter    # 凌厉的攻击者
    infantry_leader         # 步兵指挥官
    panzer_leader           # 装甲指挥官
    trait_mountaineer       # 山地专家
    adaptable               # 强于适应
}
```

数值未动：skill 1 / attack 4 / defense 2 / planning 6 / logistics 1。

### 新增 YSS_dihua 荻花 — 陆军元帅 + 内阁顾问

```
YSS_dihua = {
    name = "荻花"
    portraits = {
        civilian = {
            small = "gfx/leaders/YSS/126.png"
            large = "gfx/leaders/YSS/125.png"
        }
    }
    advisor = {
        traits = { YSS_dihua_guard_commander }
        idea_token = YSS_dihua_guard_commander
        slot = political_advisor
        cost = 150
        ai_will_do = { factor = 10 }
    }
    field_marshal = {
        traits = {
            organizer              # 组织专家
            infantry_leader        # 步兵指挥官
            urban_assault_specialist # 巷战专家
            harsh_leader           # 严军统帅
            career_officer         # 职业军官
            inflexible_strategist  # 顽强的防御者
        }
        skill = 4
        attack_skill = 2
        defense_skill = 7
        planning_skill = 4
        logistics_skill = 3
    }
}
```

---

## 2. `common/country_leader/YSS_traits_extra.txt`

新增 3 个领袖特质（写在原有 `leader_traits = { }` 块内）：

```
YSS_mingjiu_commander_in_chief = {
    random = no
    sprite = 9
    experience_gain_army = 0.40
    army_attack_factor = 0.15
    command_power_gain = 0.07
    command_cap_increase = 30
}

YSS_dihua_guard_commander = {
    random = no
    sprite = 9
    intelligence_agency_defense = 0.5
    army_core_defence_factor = 0.15
    communism_drift = 0.05
    drift_defence_factor = 0.10
}

YSS_atom_heart = {
    random = no
    sprite = 9
    mass_assault_mastery_gain_factor = 0.30
    experience_gain_army = 0.60
}
```

---

## 3. `history/countries/YSS.txt`

新增两行招募：

```
recruit_character = YSS_dihua
recruit_character = YSS_1_44
```

`YSS_1_44` 原来是「从未被招募」的状态，所以八云红的内阁顾问在游戏里根本看不到；改成理论学家后补上了招募。

---

## 4. `localisation/simp_chinese/YSS2_l_simp_chinese.yml`

追加 6 行（3 个特质 × 名称 + 描述）：

```
 YSS_mingjiu_commander_in_chief: "总司令"
 YSS_mingjiu_commander_in_chief_desc: "§L此人主张以进攻代替防守，认为最好的防御就是有力的进攻。§!"
 YSS_dihua_guard_commander: "革命近卫军司令"
 YSS_dihua_guard_commander_desc: "§L旧帝国皇帝近卫军的前领队。门柯斯图的革命理念感染了她，她带着一支只忠于自己的近卫部队倒戈，从内部推翻了帝国。§!"
 YSS_atom_heart: "原子之心"
 YSS_atom_heart_desc: "§L她把作战理论命名为「原子之心」：胜负最终取决于谁能在战线上堆出更多的师，以及谁能把它们更快地练成活人。§!"
```

---

## 5. 新增立绘

| 文件 | 规格 | 用途 |
|---|---|---|
| `gfx/leaders/YSS/125.png` | 156×210 | 荻花 大立绘（红底渐变，与其他元帅一致） |
| `gfx/leaders/YSS/126.png` | 65×67 | 荻花 小头像（倾斜卡片 + 暗色描边，与现有顾问头像一致） |

---

## 6. 未保留的改动

`map/railways.txt` 曾加过一条 `1 2 5210 8183`（连通蒙巴萨一带断开的两段铁路），
按要求已还原，**不在本补丁内**。