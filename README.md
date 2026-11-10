# YSS 人物改动补丁（钢铁萌心：狂野法则 · 91）

生成时间：2026-11-10 23:44:26
只包含改动过的文件；覆盖进 mod 目录即可。

## 目录结构

```
common/characters/YSS.txt                          角色定义（荻花 / 八云红 / 茗旧 / 陵）
common/country_leader/YSS_traits_extra.txt         4 个自定义领袖特质
history/countries/YSS.txt                          开局招募
localisation/simp_chinese/YSS2_l_simp_chinese.yml  特质名与描述
gfx/leaders/YSS/125.png                            荻花元帅立绘 156x210
gfx/leaders/YSS/126.png                            荻花顾问头像 65x67
MANIFEST.txt                                       文件哈希（用来确认覆盖成功）
```

## 怎么用

1. 备份 mod 目录
2. 把 `common/` `history/` `localisation/` `gfx/` 覆盖进
   `C:\Program Files (x86)\Steam\steamapps\workshop\content\394360\91\`
3. **开新档**——人物等级、特质、内阁职位都写在存档里，旧档不会变

## 为什么“陵没有变化”

按可能性排序：

1. **用的旧存档**。陵在旧档里已经是军长，等级和特质存在存档数据里，改文件不会回溯。必须开新游戏。
2. **只覆盖了部分文件**。陵涉及两个文件：`common/characters/YSS.txt`（等级/特质）和 `localisation/…YSS2…yml`（特质名）。少覆盖一个就会显示不对或没变。
3. **覆盖到了错的目录**。Steam 创意工坊的 mod 在 `workshop/content/394360/91/`；如果你有自己的本地副本（`Documents/Paradox Interactive/Hearts of Iron IV/mod/…`），要覆盖的是正在启用的那一份。
4. **上传的是旧包**。用 `MANIFEST.txt` 核对：`common/characters/YSS.txt` 应为 33552 字节，SHA256 以 `F5A6FA91` 开头。

## 生效后应该看到

- 将领列表里，**陵**是元帅（不是军长），特质只有「后勤奇才」
- **荻花**作为新元帅出现，另有内阁「革命近卫军司令」
- **八云红**元帅 4 级 9 特质；理论学家「原子之心」300 点
- **茗旧**元帅 7 特质；理论学家 300 点
- 陵的政治顾问特质显示为「后勤工程师」

## 依赖

需要 `Adorable heart`（workshop 2879371758）作为前置。