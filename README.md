# YSS 改动补丁（荻花 / 砚）

这是「钢铁萌心：狂野法则」（mod 91）的一小组改动，按 mod 根目录结构组织，**只包含改动过的文件**。

## 怎么用

1. 把本目录里的 `common/`、`events/`、`gfx/`、`history/`、`localisation/` 覆盖到 mod 根目录：
   `...\steamapps\workshop\content\394360\91\`
2. 启动器里确认 mod 已启用，**开新档**（旧存档不会更新将领数据，事件也只在开局触发）。
3. 文件结构与本目录一致，见 `CHANGES.md`。

## 目录

```
common/characters/YSS.txt                       将领与顾问
common/country_leader/YSS_traits_extra.txt      新增的 5 个领袖特质
history/countries/YSS.txt                       开局招募新角色
events/YSS_guard_events.txt                     事件 YSS.8001「联盟的命运」
localisation/simp_chinese/YSS2_l_simp_chinese.yml  文案
gfx/leaders/YSS/125-128.png                     荻花 / 白珩立绘
```

## 校验

```
hoi4skill validate . --game-root "<HOI4 安装目录>" --auto-mod-paths --launcher-dir "<Documents>\Paradox Interactive\Hearts of Iron IV\mod" --changed-only
```

`CHANGES.md` 里有逐项改动说明与效果数值。