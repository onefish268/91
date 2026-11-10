# 钢铁萌心：狂野法则 — 将领改动补丁

本仓库不是完整的 mod，只包含 2026-11-10 这一次改动涉及的 **6 个文件**。
完整 mod 约 370 MB，没必要一起上传。

## 改了什么

- 八云红 / 茗旧 两位将领的军衔与特质
- 新增元帅「荻花」（含独立立绘与内阁职位「革命近卫军司令」）
- 茗旧、八云红 进入理论学家槽
- 对应的中文本地化

逐条说明见 [CHANGES.md](CHANGES.md)。

## 怎么用

把本仓库里的 `common/`、`history/`、`localisation/`、`gfx/` 四个目录，
连同原有目录结构覆盖到 mod 根目录即可：

```
C:\Program Files (x86)\Steam\steamapps\workshop\content\394360\91\
```

覆盖前建议先备份同名文件。

## 注意

- `common/characters/YSS.txt` 是**整个文件**，基于 v1.19.3 的版本；如果你那边这个文件已经有别的改动，
  不要直接覆盖，照着 CHANGES.md 手工合并。
- 新增角色靠 `history/countries/YSS.txt` 里的 `recruit_character` 生效，**旧存档看不到，需要新开档**。

## 验证

```
hoi4skill validate . --game-root "C:\Program Files (x86)\Steam\steamapps\common\Hearts of Iron IV" --auto-mod-paths --launcher-dir "C:\Users\andy\Documents\Paradox Interactive\Hearts of Iron IV\mod" --changed-only --changed common/characters/YSS.txt --changed common/country_leader/YSS_traits_extra.txt --changed history/countries/YSS.txt --changed localisation/simp_chinese/YSS2_l_simp_chinese.yml
```

结果：`OK: no static issues found.`