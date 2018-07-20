# Modifications to implement in YR

## Ares 新增逻辑

> 单人遭遇战;  
> 升级后的建筑可作为 Prerequisite 和超武的 AuxBuilding;  
> Gate 可置于围墙上;  
> Vehicle 可为建筑充能(overpowering, 如磁暴线圈);  
- 不同气候的建筑皮肤`NewTheater=yes`;
- 超武卖单位动作`Action=SellUnit`;
- 两栖单位可改变外观`[VehicleType]WaterImage=`;
- EMP,可装备磁能坦克;
- Firestorm Wall; Laser Fences;
- Multi Engineer, Multi Engineer Checkbox;
- Spotlights;
- Vehicle Thief,
- 弹头对护甲有效性和攻击行为分开;
- Aircraft-Specific ReloadRate 指定飞机装弹时间;
- AirRate 直升机升空动画;
- AlternateTheaterArt SHP动画单位可根据地图气候换肤;
- AttachEffect 附加持续效果;
- 飞机可空中爆炸而非坠机`[AircraftType]Crashable=`;
- Crush Damage 载具碾压损耗;
- Reverse Engineer logic 技术复制逻辑;
- Hiding Enemy Insignia 隐藏敌军等级;
- Dimming Deactivated Units 自定义非激活等级;
- Disk Laser Animations 飞碟激光动画;
- Tiberian Fiends 野怪;
- Drain Weapon Options 电力瘫痪阈值;
- Drop Pods 召唤步兵超武？
- Factory Plant Effect 造价折扣自定义;
- Forest Fires 森林火灾 (需要动画支持);
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
- Operator 操作员逻辑 (ai不会用);
- Specific Passengers 载具限定乘客;
- Tech Structures Return to Neutral 中立建筑归还与通知；
- Pips 新定义;
- Multiple Alternative Prerequisites Lists 可替代建造前提;
- Radar Jammers 雷达干扰;
- Saboteurs 建筑爆破步兵;
- Self Heal 自定义自愈逻辑;
- Survivors 建筑载具生还;
- Team Retaliate 队伍反击;
- Turret ROT 载具炮塔转速;
- Veteran and Elite Abilities 新升级能力;
- Assaulter 定义爆破等级;
- Custom Building Foundations 自定义建筑占地;
- Enemy Wrench 敌军建筑维修显示;
- Factories and Cloning 指定建造或复制;
- Fakes 伪建筑;
- Force Shield 力场护盾持续时间分化;
- Lightning Rods 避雷针;
- Prism Forwarding 光棱塔逻辑;
- Oil Derricks 油井设置（版本可能变化）;
- Repair and Insufficient Funds 缺钱维修中断;
- Solid Buildings 建筑遮挡逻辑（影响弹道;不遮挡激光武器但承受伤害）;
- Toggle Power 断电逻辑;
- Trivial Structure Damage 建筑停电损耗;
- Tunnel Networks 传送门逻辑（隧道）;
- Urban Combat - Trenches 战壕、废墟逻辑;
- Cloak, Stealth and Sensor Arrays 隐形与反隐逻辑;
- Bounty 各单位赏金;
- Sensor Arrays 探测阵列;
- Projectile Range 导弹航程;
- Ivan Bombs 伊文炸弹自定义;
- Damage Airborne Units 弹头影响空军;
- Nuke Flash 核爆光辐射时间;
- Disable Weapons 沉默;
- Permanent Mind-Control 永久控制;
- Deployed Infantry Damage multiplier 部署步兵防御变化;
- InfDeathAnim 步兵阵亡动画 可设置突变;
- Berserk Reloading Time Modifier 狂暴状态攻速;
- Suppress Death Weapons 熄火死亡武器;
- Suppress Unit Lost Message 静默杀手;
- Cost 超武花费;

## Ares 新增UI

- *uimd.ini* 可增加新战役的任务图标 (至多4个) `[UISettings]CampaignX=`;
- 直接退出游戏,不确认 `[UISettings]QuickExit=`;
- 新增可编辑快捷键:
  - FPS Counter;
  - Toggle Power;
- 自定义主菜单按钮 `[UISettings]WWOnlineButton=`;
- *uimd.ini* (Ares 0.8): 指明 MOD 版本;方便调试,且**影响存档**!
  - `[VersionInfo]Name= (string)`;
  > The name of the modification in unspecified format. Maximum 63 characters. Defaults to *Yuri’s Revenge*.
  - `[VersionInfo]Version= (string)`
  > The version of the modification in unspecified format. Maximum 63 characters. Defaults to *1.001*.

## 单位

- `ARND`
- `STLN`
- `CLNT` (西木之星)

## 科技条件

- `HIND`
- `HOWI`
- `LUNR`
- `NIMITZ`
- `VLAD`
- `YURIG`
