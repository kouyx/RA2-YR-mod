# Log modifications in YR

## 反击平民袭击

```ini
[CombatDamage]
AutoRepel=yes  ; Ares 0.7
[CombatDamage]
PlayerAutoRepel=yes  ; Ares 0.7
```

## Bounty 赏金规则

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

## 中立建筑归还

```ini
[General]
ReturnStructures=yes  ; Ares 0.6
```

## 替换间谍逻辑

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

## 箱子金钱浮动 (未验证)

```ini
[CrateRules]
RandomCrateMoney=1000  ; Ares 0.C
```

## 游戏中光标

### 重新定义

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

### 光标更改

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

## 新增精英武器

- 精英尤里武器:
  - 控制数 +2;
  - 射程 +1;
  - 攻击间隔 -20%.

```ini
[MindControlV]
Damage=3;1;Number of mind control links
ROF=150;200
Range=8;7
Projectile=PsychicControl
Speed=100
Warhead=Controller
;Report=YuriMindControl
Anim=YURICNTL
FireOnce=yes
Cursor.Attack=MindControl  ; Ares 0.D
Cursor.AttackOutOfRange=MindControl  ; Ares 0.D
```

- 精英脑车武器:
  - 控制数 +2;
  - 射程 +1;

```ini
[MultipleMindControlTankE]
Damage=5;3; this is an infinite mind control, so this just affects pips
InfiniteMindControl=yes; this will let infinite, it will look up on the table of "MasterMind Overload" damage way above (where there is a 0 damage level)
ROF=10
Range=7;6
Projectile=PsychicControl
Speed=100
Warhead=Controller
;Report=YuriMindControl
Anim=YURICNTL
FireOnce=yes
OmniFire=yes;doesn't need turret to shoot any direction
Cursor.Attack=MindControl  ; Ares 0.D
Cursor.AttackOutOfRange=MindControl  ; Ares 0.D
```