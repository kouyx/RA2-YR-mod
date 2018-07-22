# Modifications in YR

Modifications in [*IMPLEMENT.md*](./IMPLEMENT.md) would be summarized on the following aspects.

- [Ares 建议](#ares-advice)
- [全局逻辑](#global)
- [UI](#ui)
  - [单位图标](#单位图标)
  - [防卫建筑射程显示](#防卫建筑射程显示)
  - [游戏中光标](#游戏中光标)
- [科技](#technology)
- [建筑](#building)
  - [学院建筑逻辑](#学院建筑逻辑)
  - [间谍渗透逻辑](#间谍渗透逻辑)
- [单位](#units)
  - [混编队伍](#混编队伍)
  - [新增单位](#新增单位)
  - [单位晋升](#单位晋升)
  - [调整单位](#调整单位)
- [武器](#weapon)
  - [精英武器](#精英武器)
  - [新增武器](#新增武器)

## Ares Advice

- rulesmd.ini
  > 将 `APOCEXP` 添加到 `[Animations]` 列表;
- artmd.ini
  > 新增 `[TELE]` 的 `SecondaryFireFLH`;
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
  - `HIND` (YR)
  - `NIMITZ` (网图)
  - `HOWI` (YR)
  - `VLAD` (无畏镜像)
- 恢复升级图标:
  - `IVAN` (疯狂伊文)
  - `CIVAN` (超时空伊文)
- 新增升级图标(未使用):
  - `AEGIS`
  - `BEAG`
  - `BPLN`
  - `BSUB`
  - `CARRIER`
  - `DEST`
  - `DLPH`
  - `DRED`
  - `HYD`
  - `ORCA`
  - `SQD`
  - `SUB`

### 防卫建筑射程显示

扫描半径效果 (裂缝产生器):

- `[GAPILL]`
- `[NASAM]`
- `[ATESLA]`
- `[GTGCAN]`
- `[NALASR]`
- `[NAFLAK]`
- `[TESLA]`
- `[YAGGUN]`
- `[YAPSYT]`
- `[CAOUTP]`

### 游戏中光标

- 移植自 TS:
  - 间谍偷钱 (原卖建筑);
  - 间谍渗透妨碍;
  - 切换断电;
  - 单位返厂维修;
- 新增光标:
  - 反部署 (如建造厂->MCV);
  - 建筑集合点;
  - 尤里脑波武器;
  - 心灵控制;
  - 无武器单位移动;
  - 移动部署 (如神经突击车);
  - 大兵部署;
  - 辐射工兵部署;
  - 间谍伪装;
  - 间谍偷科技;
  - 间谍断电;
  - 卖单位 (部队回收厂);
  - 步兵吸收 (生化炉);
- 更改光标:
  - 自爆卡车射程外攻击 -> 核袭击;

## Technology

- 实验室可升级步兵至精英 (1人次):
  - 三方作战实验室;
  - 秘密科技实验室;
- 科技实验室视为高科建筑;
- 实验室科技将在每次占领后重置;
- 科技实验室调整科技:
  - 步兵 (4):
    - \+ `LUNR`,
    - \+ `SPY`,
    - \+ `SNIPE` (未验证),
    - \+ `YURIG`
    - \- `TERROR`;
  - 飞机&战车&舰船 (8):
    - \+ `BEAG`,
    - \+ `BFRT` (未验证),
    - \+ `HIND`,
    - \+ `HOWI`,
    - \+ `FV` (未验证),
    - \+ `NIMITZ`
    - \+ `SMIN` (未验证),
    - \+ `VLAD`,
    - \- `DTRUCK`;
  - 建筑 (6):
    - \+ `GAOREP` (未验证),
    - \+ `GASPYSAT` (未验证),
    - \+ `NACLON` (未验证),
    - \+ `NAINDP` (未验证),
    - \+ `NANRCT` (未验证);
    - \+ `NAPSIS` (未验证),

## Building

### 学院建筑逻辑

- 科技前哨站升级空军(飞行单位)至老兵等级;
- 科技实验室升级海军至老兵等级;
- 科技医院加生命单位初始经验 50% (新兵至老兵);
- 科技机器商店加生命单位初始经验 50% (新兵至老兵);

### 间谍渗透逻辑

- 窥视生产/建造信息 (渗透后选中)
  - 建筑建造: `[GACNST]`,`[NACNST]`,`[YACNST]`;
  - 步兵动员: `[GAPILE]`,`[NAHAND]`,`[YABRCK]`;
  - 载具/飞机生产: `[GAWEAP]`,`[NAWEAP]`,`[YAWEAP]`,`[GAAIRC]`,`[AMRADR]`;
  - 显示电力: `[GAPOWR]`,`[NAPOWR]`,`[NANRCT]`,`[YAPOWR]`;
- 偷钱 (比例窃取无效果)
  - 定额窃取: `[NAINDP]`,`[NACLON]`,`[GAOREP]`;
- 获得雷达视野: `[GASPYSAT]`
- 断电时间分化: `[GAPOWR]`,`[NAPOWR]`,`[NANRCT]`,`[YAPOWR]`
- 超武重置 + 获得一发
  - 第二超武: `[GACSPH]`,`[NAIRON]`,`[YAGNTC]`
  - 雷达超武: `[NARADR]`,`[NAPSIS]`
  - 伞兵超武: `[AMRADR]`,`[CAAIRP]`
- 建筑爆破: `[GAROBO]`

## Units

### 混编队伍

- 部署后实际不同注册名的单位分组 (如 MCV 和奴矿);
  > `DeploysInto` and `UndeploysInto`
- 实质同类单位合编 (如狗和工程师).

### 新增单位

- 重制单位:
  - `NIMITZ` (原`CARRIERB`设定, vxl credit to **Mig Eater** from [*Project Perfect Mod*](https://ppmforums.com/viewtopic.php?highlight=nimitz&t=19484))
  - `HIND` (螺旋桨与机体分离)
- 复刻单位: `YURIG` (RA2尤里改)

### 单位晋升

- 单位可升级:
  - `IVAN`;
  - `CIVAN`;
  - `YURI`;
  - `YURIPR`;
  - `MIND`;
  - `CARRIER` (未定义精英武器);
  - `NIMITZ` (未定义精英武器);
- 分享子机经验 (Ares 0.2, spawn/spawner):
  - `DEST`        0.5/0.5;
  - `CDEST`       0.5/0.5;
  - `NIMITZ`      0.6/0.6;
  - `CARRIER`     0.5/0.5;
- 分享空袭经验 (Ares 0.2): BORIS` (0.5);
- 满级后分享驻兵经验 (Ares 0.2):
  - `FV`                 0.6;
  - `TTNK`               0.8;
  - `TNKD`               0.8;
  - `BFRT`               0.6;
- 分享心控经验 (Ares 0.2, controller/victim):
  - `YURIG`       0.3/0.7;
  - `YURI`        0.1/0.9;
  - `YURIPR`      0.4/0.6;
  - `MIND`        0.2/0.8;
- 晋升获得能力:
  - 舰载反潜机:
    - 老兵: 自愈, 火力;
    - 精英: 护甲, 火力;

### 调整单位

- 载具可驻兵攻击:
  - `TTNK` (1);
  - `TNKD` (1);

## Weapon

### 精英武器

- 尤里: 控制数 +2; 射程 +1; 攻击间隔 -20%;
- 脑车: 控制数 +2; 射程 +1;
- `HIND`同夜莺;
- `YURIPR`控制数增至 3;
- `HOWI`伤害, 攻速, 射程提升; 弹头效果小幅提升; 造价提升;
- `FV`模式: 工程师, 美国大兵, 防空步兵, 磁暴步兵, 尤里新兵, 重装步兵;

### 新增武器

- `AEGIS`: 新增对地武器; 造价提升;
- `FV`模式: `BORIS`;
