# Modifications in YR

1. [Ares 建议](#ares-advice)
1. [武器相关](#Weapon)
1. [科技相关](#Technology)
1. [升级相关](#Veterancy-and-Promotion)
1. [全局逻辑](#Global)
1. [单位相关](#Units-and-UI)

## Ares Advice

- rulesmd.ini
  > 将 `APOCEXP` 添加到 `[Animations]` 列表;
- artmd.ini
  > 新增 `[TELE]` 的 `SecondaryFireFLH`;
- bombcurs.shp
  > 删除最后一帧;

## Weapon

- 新增精英武器:
  - `HIND`同夜莺;
  - `YURIPR`控制数增至 3;
  - `HOWI`伤害, 攻速, 射程提升; 弹头效果小幅提升; 造价提升;
  - `FV`模式: 工程师, 美国大兵, 防空步兵, 磁暴步兵, 尤里新兵, 重装步兵;
- 新增武器:
  - `AEGIS`: 新增对地武器; 造价提升;
  - `FV`模式: `BORIS`;

## Technology

- 实验室可升级步兵至精英 (1人次):
  - 三方作战实验室;
  - 秘密科技实验室;
- 科技实验室视为高科建筑;
- 科技实验室调整科技:
  - 步兵 (6):
    - \+ `SPY`,
    - \+ `VIRUS` (未验证),
    - \+ `LUNR` (未验证)
    - \- `TERROR`;
  - 飞机&战车&舰船 (9):
    - \+ `HOWI`,
    - \+ `BEAG` (未验证),
    - \+ `SMIN` (未验证),
    - \+ `FV` (未验证),
    - \+ `BFRT` (未验证),
    - \+ `VLAD` (未验证),
    - \+ `NIMITZ` (未验证)
    - \- `DTRUCK`;
  - 建筑 (7):
    - \+ `GAOREP` (未验证),
    - \+ `NAPSIS` (未验证),
    - \+ `NAINDP` (未验证),
    - \+ `NACLON` (未验证),
    - \+ `GASPYSAT` (未验证),
    - \+ `NANRCT` (未验证);

## Veterancy and Promotion

- 单位可升级:
  - `IVAN`;
  - `CIVAN`;
  - `YURI`
- 分享子机经验 (Ares 0.2, spawn/spawner):
  - `DEST`        0.5/0.5;
  - `CDEST`       0.5/0.5;
  - `NIMITZ`      0.6/0.6;
  - `CARRIER`     0.5/0.5;
- 分享空袭经验 (Ares 0.2): BORIS` (0.5);
- 满级后分享驻兵经验 (Ares 0.2):
  - `FV`                 0.6;
  - `TTNK` (新增驻兵)      0.8;
  - `TNKD` (新增驻兵)      0.8;
  - `BFRT`                0.6;
- 分享心控经验 (Ares 0.2, controller/victim):
  - `YURIG`       0.3/0.7;
  - `YURI`        0.1/0.9;
  - `YURIPR`      0.4/0.6;
  - `MIND`        0.2/0.8;
- 升级能力增强:
  - 舰载反潜机:
    - 老兵: 自愈, 火力;
    - 精英: 护甲, 火力;

## Global

- 伞兵增强:
  - (美国) 空降部队配置: 6 大兵 + 2 重装;
- 防御建筑射程显示 (裂缝产生器的效果);
- 箱子金钱浮动 1000 (未验证);
- 伊文炸弹可手动引爆;

## Units and UI

- 重制单位:
  - `NIMITZ` (原`CARRIERB`设定, vxl credit to **Mig Eater** from [*Project Perfect Mod*](https://ppmforums.com/viewtopic.php?highlight=nimitz&t=19484))
  - `HIND` (螺旋桨与机体分离)
- 复刻单位: `YURIG` (RA2尤里改)
- 单位图标调整:
  - 新建图标:
    - `HIND` (YR)
    - `NIMITZ` (网图)
    - `HWTZ` (YR)
    - `VLAD` (无畏镜像)
  - 恢复升级图标:
    - `IVAN` (疯狂伊文),
    - `CIVAN` (超时空伊文)
