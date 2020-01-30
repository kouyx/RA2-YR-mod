# Modifications in YR

Modifications in [*IMPLEMENT.md*](./IMPLEMENT.md) would be summarized on the following aspects.

- [Ares Advice](#ares-advice)
- [Global](#global)
- [UI](#ui)
  - [单位图标](#%e5%8d%95%e4%bd%8d%e5%9b%be%e6%a0%87)
  - [防卫建筑射程显示](#%e9%98%b2%e5%8d%ab%e5%bb%ba%e7%ad%91%e5%b0%84%e7%a8%8b%e6%98%be%e7%a4%ba)
  - [游戏中光标](#%e6%b8%b8%e6%88%8f%e4%b8%ad%e5%85%89%e6%a0%87)
- [Technology](#technology)
- [Building](#building)
  - [学院建筑逻辑](#%e5%ad%a6%e9%99%a2%e5%bb%ba%e7%ad%91%e9%80%bb%e8%be%91)
  - [间谍渗透逻辑](#%e9%97%b4%e8%b0%8d%e6%b8%97%e9%80%8f%e9%80%bb%e8%be%91)
- [Units](#units)
  - [混编队伍](#%e6%b7%b7%e7%bc%96%e9%98%9f%e4%bc%8d)
  - [新增单位](#%e6%96%b0%e5%a2%9e%e5%8d%95%e4%bd%8d)
  - [单位晋升](#%e5%8d%95%e4%bd%8d%e6%99%8b%e5%8d%87)
  - [调整单位](#%e8%b0%83%e6%95%b4%e5%8d%95%e4%bd%8d)
- [Weapon](#weapon)
  - [精英武器加强](#%e7%b2%be%e8%8b%b1%e6%ad%a6%e5%99%a8%e5%8a%a0%e5%bc%ba)
  - [新增武器](#%e6%96%b0%e5%a2%9e%e6%ad%a6%e5%99%a8)

## Ares Advice

- rulesmd.ini
  > 将 `APOCEXP` 添加到 `Animations` 列表;
- artmd.ini
  > 新增 `TELE` 的 `SecondaryFireFLH`;
- bombcurs.shp
  > 删除最后一帧;

## Global

- 伞兵调整:
  - (美国) 空降部队配置: 6 大兵 + 2 重装;
- 箱子金钱浮动 1000 (未验证);
- 伊文炸弹可手动引爆;
- 单位反击中立单位袭击;
- 遭遇战中战败方返还中立建筑;

## UI

### 单位图标

- 新增图标(带相应升级图标):
  1. `HIND` (YR)
  1. `NIMITZ` (网图)
  1. `HOWI` (YR)
  1. `VLAD` (无畏镜像)
- 恢复升级图标:
  1. `IVAN` (疯狂伊文)
  1. `CIVAN` (超时空伊文)
- 新增升级图标(未使用):
  1. `AEGIS`
  1. `BEAG`
  1. `BPLN`
  1. `BSUB`
  1. `CARRIER`
  1. `DEST`
  1. `DLPH`
  1. `DRED`
  1. `HYD`
  1. `ORCA`
  1. `SQD`
  1. `SUB`

### 防卫建筑射程显示

扫描半径效果 (裂缝产生器):

1. `GAPILL`
1. `NASAM`
1. `ATESLA`
1. `GTGCAN`
1. `NALASR`
1. `NAFLAK`
1. `TESLA`
1. `YAGGUN`
1. `YAPSYT`
1. `CAOUTP`

### 游戏中光标

- 移植自 TS:
  1. 间谍偷钱 (原卖建筑);
  1. 间谍渗透妨碍;
  1. 切换断电;
  1. 单位返厂维修;
- 新增光标:
  1. 反部署 (如建造厂->MCV);
  1. 建筑集合点;
  1. 尤里脑波武器;
  1. 心灵控制;
  1. 无武器单位移动;
  1. 移动部署 (如神经突击车);
  1. 大兵部署;
  1. 辐射工兵部署;
  1. 间谍伪装;
  1. 间谍偷科技;
  1. 间谍断电;
  1. 卖单位 (部队回收厂);
  1. 步兵吸收 (生化炉);
- 更改光标:
  1. 自爆卡车射程外攻击 -> 核袭击;

## Technology

- 实验室可升级步兵至精英 (1人次):
  1. 三方作战实验室;
  1. 秘密科技实验室;
- 科技实验室视为高科建筑;
- 实验室科技将在每次占领后重置;
- 科技实验室调整科技:
  - 步兵:
    1. \+ `LUNR`,
    2. \+ `SPY`,
    3. \+ `SNIPE` (未验证),
    4. \+ `YURIG`
    5. \- `TERROR`;
  - 飞机&战车&舰船:
    1. \+ `BEAG`,
    2. \+ `BFRT` (未验证),
    3. \+ `HIND`,
    4. \+ `HOWI`,
    5. \+ `FV` (未验证),
    6. \+ `NIMITZ`
    7. \+ `SMIN` (未验证),
    8. \+ `VLAD`,
    9. \- `DTRUCK`;
  - 建筑:
    1. \+ `GAOREP` (未验证),
    2. \+ `GASPYSAT` (未验证),
    3. \+ `NACLON` (未验证),
    4. \+ `NAINDP` (未验证),
    5. \+ `NANRCT` (未验证);
    6. \+ `NAPSIS` (未验证),

## Building

### 学院建筑逻辑

- 科技前哨站升级空军(飞行单位)至老兵等级;
- 科技实验室升级海军至老兵等级;
- 科技医院加生命单位初始经验 50% (新兵至老兵);
- 科技机器商店加生命单位初始经验 50% (新兵至老兵);

### 间谍渗透逻辑

- 窥视生产/建造信息 (渗透后选中)
  - 当前资金: `GAREFN`,`NAREFN`,`YAREFN`
  - 建筑建造: `GACNST`,`NACNST`,`YACNST`;
  - 步兵动员: `GAPILE`,`NAHAND`,`YABRCK`;
  - 载具/飞机生产: `GAWEAP`,`NAWEAP`,`YAWEAP`,`GAAIRC`,`AMRADR`;
  - 显示电力: `GAPOWR`,`NAPOWR`,`NANRCT`,`YAPOWR`;
- 窃取资金
  - 定额窃取: `NAINDP`,`NACLON`,`GAOREP`;
- 渗透后训练单位获得老兵等级
  - 海军渗透：`GACNST`,`NACNST`,`YACNST`
  - 空军渗透: `GAAIRC`,`AMRADR`,`NARADR`,`NAPSIS`
- 获得雷达视野: `GASPYSAT`
- 断电时间分化: `GAPOWR`,`NAPOWR`,`NANRCT`,`YAPOWR`
- 超武重置 + 获得一发
  - 第二超武: `GACSPH`,`NAIRON`,`YAGNTC`
  - 雷达超武: `NARADR`,`NAPSIS`
  - 伞兵超武: `AMRADR`,`CAAIRP`
- 建筑爆破: `GAROBO`

## Units

### 混编队伍

- 部署后实际不同注册名的单位分组 (如 MCV 和奴矿);
  > `DeploysInto` and `UndeploysInto`
- 实质同类单位合编 (如不同阵营的警犬和工程师).

### 新增单位

- 重制单位:
  - `NIMITZ` (原`CARRIERB`设定, vxl credit to **Mig Eater** from [*Project Perfect Mod*](https://ppmforums.com/viewtopic.php?highlight=nimitz&t=19484))
  - `HIND` (螺旋桨与机体分离)
- 复刻单位: `YURIG` (RA2尤里改)

### 单位晋升

- 单位可升级:
  1. `IVAN`;
  2. `CIVAN`;
  3. `YURI`;
  4. `YURIPR`;
  5. `MIND`;
  6. `CARRIER` (未定义精英武器);
  7. `NIMITZ` (未定义精英武器);
- 分享子机经验 (Ares 0.2, spawn/spawner):
  1. `DEST`        0.5/0.5;
  2. `CDEST`       0.5/0.5;
  3. `CARRIER`     0.5/0.5;
  4. `NIMITZ`      0.6/0.6;
- 分享空袭经验 (Ares 0.2): `BORIS` (0.2);
- 满级后分享驻兵经验 (Ares 0.2):
  1. `FV`                 0.6;
  2. `BFRT`               0.6;
  3. `TNKD`               0.8;
  4. `TTNK`               0.8;
- 分享心控经验 (Ares 0.2, controller/victim):
  1. `YURI`        0.1/0.9;
  2. `MIND`        0.2/0.8;
  3. `YURIG`       0.3/0.7;
  4. `YURIPR`      0.4/0.6;
- 晋升获得能力:
  1. 舰载反潜机:
     - 老兵: 自愈, 火力;
     - 精英: 护甲, 火力;

### 调整单位

- 载具可驻兵攻击:
  1. `TTNK` (1);
  1. `TNKD` (1);
- 赏金猎人: `TANY`, `BORIS` 消灭以下单位时将获得赏金：
  1. `TANY`
  2. `BORIS`
  3. `YURIG`
  4. `YURIPR`
  5. `CMIN`
  6. `HARV`
  7. `SMIN`
  8. `YAREFN`

## Weapon

### 精英武器加强

- 尤里: 控制数 +2; 射程 +1; 攻击间隔 -20%;
- 脑车: 控制数 +2; 射程 +1;
- `HIND`同夜莺;
- `YURIPR`控制数增至 3;
- `HOWI`伤害, 攻速, 射程提升; 弹头效果小幅提升; 造价提升;
- `FV`模式: 工程师, 美国大兵, 防空步兵, 磁暴步兵, 尤里新兵, 重装步兵;

### 新增武器

- `AEGIS`: 新增对地武器; 造价提升;
- `FV`模式: `BORIS`;
