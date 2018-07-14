# Log modifications in YR

## 历史

### 反击平民袭击

```ini
[CombatDamage]
AutoRepel=yes  ; Ares 0.7
[CombatDamage]
PlayerAutoRepel=yes  ; Ares 0.7
```

### Bounty 赏金规则

```ini
[General]
BountyEnablers=none ; Ares 0.C (list of BuildingTypes)
[AudioVisual]
BountyDisplay=yes  ; Ares 0.C
[TANY],[BORIS]
Bounty=yes  ; Ares 0.C
[TechnoType]  ; remaining to mod
Bounty.Value=  ; default 0, Ares 0.C
```

### 中立建筑归还

```ini
[General]
ReturnStructures=yes  ; Ares 0.6
```

### 替换间谍逻辑

```ini
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.StolenTechIndex=  ; Ares 0.B  (list of integers)
[GACNST],[NACNST],[YACNST],[GAROBO],[GASPYSAT],[NAINDP],[NACLON],[GAOREP],[CAOILD],[CAAIRP]
Spyable=yes
```

- 原有基础功能

```ini
; 步兵/载具升级
[GAPILE],[GAWEAP],[NAHAND],[NAWEAP],[YABRCK],[YAWEAP]
SpyEffect.UnitVeterancy=yes  ; Ares 0.1
; 矿场偷钱
[GAREFN],[NAREFN],[YAREFN]
SpyEffect.StolenMoneyPercentage=.5 ; Ares 0.1
; 重置视野
[GAAIRC],[NARADR],[AMRADR],[NAPSIS]
SpyEffect.ResetRadar=yes  ; Ares 0.1
```

- 窥视信息 (需渗透后再选中该建筑)

```ini
[GACNST],[NACNST],[YACNST],  ; 建筑建造
[GAPILE],[NAHAND],[YABRCK],  ; 步兵动员
[GAWEAP],[NAWEAP],[YAWEAP],[GAAIRC],[AMRADR],  ; 载具/飞机生产
[GAREFN],[NAREFN],[YAREFN],  ; 当前金钱
[GAPOWR],[NAPOWR],[NANRCT],[YAPOWR]  ; 当前电力
SpyEffect.RevealProduction=yes  ; Ares 0.B
```

- 偷钱

```ini
[GAOREP]
SpyEffect.StolenMoneyPercentage=.6 ; Ares 0.1 (float - multiplier) (.5) see [General]
[NAINDP],[NACLON],[CAOILD]
SpyEffect.StolenMoneyAmount= ; Ares 0.1 (integer - credits)
```

- 获得雷达视野

```ini
[GASPYSAT]
SpyEffect.RevealRadar=yes  ; Ares 0.1
```

- 断电时间分化

```ini
[GAPOWR],[NAPOWR],[NANRCT],[YAPOWR]
SpyEffect.PowerOutageDuration=  ; Ares 0.1 (integer - frames) (1000) see [General]
```

- 超武重置 + 获得一发

```ini
[AMRADR],[GACSPH],[NARADR],[NAIRON],[NAPSIS],[YAGNTC],[CAAIRP]
SpyEffect.ResetSuperweapons=yes  ; Ares 0.B
SpyEffect.SuperWeapon= ; Ares 0.B (SuperWeaponType)
```

- 建筑爆破

```ini
[GAROBO]
SpyEffect.SabotageDelay=300  ; Ares 0.E (integer - frames)
```

### 箱子金钱浮动 (未验证)

```ini
[CrateRules]
RandomCrateMoney=1000  ; Ares 0.C
```

### 游戏中光标

#### 重新定义

> Import following cursors from Command & Conquer: Tiberian Sun  
> StealCash (Sell), Sabotage, NoTogglePower, RepairDepot (UnitRepair)

```ini
[MouseCursors]  ; Ares 0.D
; 新建光标
GuardEscort=68,5,4,73,5,Center,Middle
UnDeploy=120,9,4,-1,-1,Center,Middle
Harvest=234,5,4,73,5,Center,Middle
PsiWave=249,10,4,-1,-1,Center,Middle
Rally=269,10,4,-1,-1,Center,Bottom
NoTote=345,1,0,52,1,Center,Middle
DeployMove=413,9,4,-1,-1,Center,Middle
NoRally=432,1,0,52,1,Center,Bottom
StealCash=517,10,4,100,10,Center,Middle
Sabotage=527,10,4,100,10,Center,Middle
NoTogglePower=537,1,0,-1,-1,Center,Middle
RepairDepot=538,20,4,100,10,Center,Middle
; 修改光标
DesolatorDeploy=78,10,4,-1,-1,Center,Middle
Disguise=199,5,4,-1,-1,Center,Middle
IvanBomb=204,5,4,-1,-1,Center,Middle
MindControl=209,5,4,-1,-1,Center,Middle
RemoveSquid=214,5,4,-1,-1,Center,Middle
Crush=219,5,4,-1,-1,Center,Middle
SpyTech=224,5,4,-1,-1,Center,Middle
SpyPower=229,5,4,-1,-1,Center,Middle
GIDeploy=239,10,4,-1,-1,Center,Middle
Paradrop=259,10,4,516,1,Center,Middle
TogglePower=339,6,4,-1,-1,Center,Middle
InfantryHeal=351,5,4,-1,-1,Center,Middle
Disarm=369,15,4,-1,-1,Center,Middle
PsychicDominator=488,8,4,516,1,Center,Middle
```

#### 光标更改

- 进入建筑

```ini
[YAGRND]
Cursor.Enter=SellUnit  ; Ares 0.D
[GADEPT],[GAYARD],[NADEPT],[NAYARD],[YAYARD],[CAOUTP]
Cursor.Enter=RepairDepot  ; Ares 0.D
```

- 建筑集合点 (NoRally无效果)

```ini
[GAPILE],[GAWEAP],[GADEPT],[GAYARD],[NAHAND],[NAWEAP],[NADEPT],[NAYARD],[YABRCK],[YAWEAP],[YAYARD],[NACLON]
Cursor.Move=Rally  ; Ares 0.D
Cursor.NoMove=NoRally  ; Ares 0.D
```

- 无武器单位移动

```ini
[CMIN],[AMCV],[SMCV],[PCV],[LCRF],[SAPC],[YHVR],[ENGINEER],[SPY],[SENGINEER],[YENGINEER]
Cursor.Move=Tote  ; Ares 0.D
Cursor.NoMove=NoTote  ; Ares 0.D
```

- 部署

```ini
[E1],[GGI]
Cursor.Deploy=GIDeploy  ; Ares 0.D
[DESO]
Cursor.Deploy=DesolatorDeploy  ; Ares 0.D
[YURI],[YURIG],[YURIPR]
Cursor.Deploy=PsiWave  ; Ares 0.D
[CAOS]
Cursor.Deploy=DeployMove  ; Ares 0.D
```

- 反部署

```ini
[SCHD]
Cursor.Deploy=UnDeploy  ; Ares 0.D
[GACNST],[NACNST],[YACNST],[YAREFN]
Cursor.Move=UnDeploy  ; Ares 0.D
```

- 间谍渗透

```ini
[GAREFN],[NAREFN],[YAREFN]
Cursor.Spy=StealCash  ; Ares 0.D
[GAAIRC],[AMRADR],[GASPYSAT],[GACSPH],[GAWEAT],[NARADR],[NAIRON],[NAMISL],[NAPSIS],[YAGNTC],[YAPPET]
Cursor.Spy=Sabotage  ; Ares 0.D
[NATECH], [YATECH], [GATECH]
Cursor.Spy=SpyTech  ; Ares 0.D
[GAPOWR],[NAPOWR],[NANRCT],[YAPOWR]
Cursor.Spy=SpyPower  ; Ares 0.D
```

- 生化反应炉人力发电

```ini
[YAPOWR]
Cursor.Enter=InfantryAbsorb  ; Ares 0.D
```

- 武器攻击

```ini
[MakeupKit]
Cursor.Attack=Disguise  ; Ares 0.D
Cursor.AttackOutOfRange=Disguise  ; Ares 0.D
[Demobomb]
Cursor.AttackOutOfRange=Nuke  ; Ares 0.D
[MindControl],[MindControlE],[SuperMindControl],[SuperMindControlE],[MultipleMindControlTank],[MultipleMindControlTower],[SuperMindControlG]
Cursor.Attack=MindControl  ; Ares 0.D
Cursor.AttackOutOfRange=MindControl  ; Ares 0.D
```

### 新增精英武器

- [MindControlV]
> Damage=3;1;Number of mind control links
> ROF=150;200
> Range=8;7
> Projectile=PsychicControl
> Speed=100
> Warhead=Controller
> ;Report=YuriMindControl
> Anim=YURICNTL
> FireOnce=yes
> Cursor.Attack=MindControl  ; Ares 0.D
> Cursor.AttackOutOfRange=MindControl  ; Ares 0.D
- [MultipleMindControlTankE]
> Damage=5;3; this is an infinite mind control, so this just affects pips
> InfiniteMindControl=yes; this will let infinite, it will look up on the table of "MasterMind Overload" damage way above (where there is a 0 damage level)
> ROF=10
> Range=7;6
> Projectile=PsychicControl
> Speed=100
> Warhead=Controller
> ;Report=YuriMindControl
> Anim=YURICNTL
> FireOnce=yes
> OmniFire=yes;doesn't need turret to shoot any direction
> Cursor.Attack=MindControl  ; Ares 0.D
> Cursor.AttackOutOfRange=MindControl  ; Ares 0.D

## 待调整

### Ares 新增逻辑

- 单人遭遇战;
- 升级后的建筑可作为 Prerequisite 和超武的 AuxBuilding;
- Gate 可置于围墙上;
- Vehicle 可为建筑充能(overpowering, 如磁暴线圈);
- 不同气候的建筑皮肤;
> NewTheater=yes
- 超武卖单位动作;
> Action=SellUnit
- 两栖单位可改变外观;
- [VehicleType]
WaterImage=
- EMP,可装备磁能坦克;
- Firestorm Wall; Laser Fences;
- Multi Engineer, Multi Engineer Checkbox;
- Spotlights;
- Vehicle Thief,
- 弹头对护甲有效性和攻击行为分开;
- Aircraft-Specific ReloadRate 指定飞机装弹时间;
- AirRate 直升机升空动画;
- AlternateTheaterArt shp动画单位可根据地图气候换肤;
- AttachEffect 附魔特效;
- 飞机可空中爆炸而非坠机;
- [AircraftType]
Crashable=
- 载具碾压损耗;
> Crush Damage
- Reverse Engineer logic 技术复制逻辑;
- Hiding Enemy Insignia 隐藏敌军等级;
- Dimming Deactivated Units 自定义非激活等级;
- Disk Laser Animations 飞碟激光动画;
- Tiberian Fiends 野怪;
- Drain Weapon Options 电力瘫痪阈值;
- Drop Pods 召唤步兵超武？
- Factory Plant Effect 造价折扣自定义;
- Forest Fires 森林火灾（需要动画支持;
- Gattling Enhancements 加特林逻辑调整;
- Gunner IFVs 自定义ifv模式;
- Hijackers 载具劫持;
- Hunter Seeker 载具超武？
- InfantryElectrocuted 自定义电击步兵动画;
- Initial Payload 建筑驻兵？
- No Guard Area on Self 医疗维修单位不自动警戒，可部署;
- Movies List 解锁影片;
- New Powered Unit Logic 建筑支持单位;
- NoAmmoWeapon 装填弹药期间换武器;
- Operator 操作员逻辑，但ai不会用;
- Specific Passengers 载具限定乘客;
- Tech Structures Return to Neutral 中立建筑归还与通知；
- Pips 新定义;
- Multiple Alternative Prerequisites Lists 可替代建造前提;
- Radar Jammers 雷达干扰;
- Saboteurs 建筑爆破步兵;
- Self Heal 自定义自愈逻辑;

### Ares 新增UI

- 在 uimd.ini 可增加新战役的任务图标(至多4个);
- [UISettings]
CampaignX=
- 直接退出游戏,不确认;
- [UISettings]
QuickExit=
- 新增可编辑快捷键:
  - FPS Counter;
  - Toggle Power;
- 自定义主菜单按钮;
- [UISettings]
WWOnlineButton=
- uimd.ini(Ares 0.8): 指明 MOD 版本;方便调试,且*影响存档*!
- [VersionInfo]
Name= (string)
The name of the modification in unspecified format. Maximum 63 characters. Defaults to *Yuri’s Revenge*.
- [VersionInfo]
Version= (string)
The version of the modification in unspecified format. Maximum 63 characters. Defaults to *1.001*.

### 单位

- ARND
- STLN
- CLNT(西木之星)

### 科技条件

- HIND
- NIMITZ(尼米兹航母)
- YURIG(尤里改)
- HWTZ
- VLAD
- LUNR

## 调整一览

### Ares 建议

- rulesmd.ini: 将 APOCEXP 添加到 [Animations] 列表;
- artmd.ini: 新增 [TELE] 的 SecondaryFireFLH;
- bombcurs.shp: 在 cache.mix 下, 色盘为 RA2 的 mouseXXX; 删除最后一帧;

### 武器相关

- 新增精英武器:
  - HIND        同夜莺;
  - YURIPR      控制数增至3;
  - HOWI        伤害,攻速,射程提升; 弹头效果小幅提升; 造价提升;
  - FV          工程师,美国大兵,防空步兵,磁暴步兵,尤里新兵,重装步兵;
- 新增武器:
  - AEGIS       新增对地武器; 造价提升;
  - FV          BORIS;
- 伊文炸弹可手动引爆;

### 科技相关

- 实验室可升级步兵至精英(1人次): 三方作战实验室,秘密科技实验室;
- 科技实验室视为高科建筑;
- 科技实验室调整科技:
  - 步兵(6): +SPY,+VIRUS(未验证),+LUNR(未验证);-TERROR;
  - 飞机&战车&舰船(9): +HOWI,+BEAG(未验证),+SMIN(未验证),+FV(未验证),+BFRT(未验证),+VLAD(未验证),+NIMITZ(未验证);-DTRUCK;
  - 建筑(7): +GAOREP(未验证),+NAPSIS(未验证),+NAINDP(未验证),+NACLON(未验证),+GASPYSAT(未验证),+NANRCT(未验证);

### 升级相关

- 新增可升级单位: IVAN,CIVAN,YURI
- 分享子机经验(Ares 0.2):
  - DEST        0.5 - 0.5;
  - CDEST       0.5 - 0.5;
  - NIMITZ      0.6 - 0.6;
  - CARRIER     0.5 - 0.5;
  - BORIS       0.5;
- 满级后分享驻兵经验(Ares 0.2):
  - FV                 0.6;
  - TTNK(新增驻兵)      0.8;
  - TNKD(新增驻兵)      0.8;
  - BFRT                0.6;
- 分享心控经验(Ares 0.2):
  - YURIG       0.3 - 0.7;
  - YURI        0.1 - 0.9;
  - YURIPR      0.4 - 0.6;
  - MIND        0.2 - 0.8;
- 升级能力增强:
  - 舰载反潜机: 老兵自愈,火力;精英护甲,火力;

### 全局逻辑

- 伞兵增强:
  - (美国)空降部队配置: 6 大兵 + 2 重装;
- 防御建筑射程显示(裂缝产生器的效果);
- 箱子金钱浮动(未验证);
- [CrateRules]
RandomCrateMoney=1000

### 新增单位及UI

- 重制单位: NIMITZ, HIND
- 复刻单位: YURIG(尤里改)
- 单位图标调整:
  - 新建图标: HIND(原作), NIMITZ(网图), HWTZ(原作), VLAD(无畏镜像)
  - 恢复升级图标: IVAN(疯狂伊文), CIVAN(超时空伊文)
