# Details of Modifications in Code Files

- [Path](#path)
- [artmd.ini](#artmdini)
- [rulesmd.ini](#rulesmdini)
  - [Global](#global)
  - [House & Side](#house--side)
  - [Infantry](#infantry)
  - [Vehicle](#vehicle)
  - [Aircraft](#aircraft)
  - [Building](#building)
  - [Weapon](#weapon)
  - [Projectile](#projectile)
  - [Particle & Particle System](#particle--particle-system)
  - [Warhead](#warhead)
  - [Terrain & Smudge & Overlay](#terrain--smudge--overlay)
  - [Super Weapon](#super-weapon)
  - [Animation](#animation)

## Path

- cameos:
  - RA2: *language.mix* -> *cameo.mix*
  - YR: *langmd.mix* -> *cameomd.mix*
- mouse cursors & infantry sequence:
  - RA2: *ra2.mix* -> *conquer.mix*
  - YR: *ra2md.mix* -> *conqmd.mix*
- **rules(md).ini** & **art(md).ini** & .VXL & .HVA:
  - RA2: *ra2.mix* -> *local.mix*
  - YR: *ra2md.mix* -> *localmd.mix*

## artmd.ini

```ini
[HYD] ; Sea Scorpion
AltCameo=HOVRUICO ;MOD

[SQD] ; Squid
AltCameo=SQDUICO ;MOD

[BEAG] ; Black Eagle
AltCameo=BEAGUICO ;BEAGICON

[BPLN] ; Boris Attack Plane
AltCameo=BPLNUICO ;BPLNICON

[SUB] ;soviet submarine
AltCameo=SUBUICO ; MOD

[BSUB] ;Yuri Boomer submarine
AltCameo=BSUBUICO ; MOD

[DLPH] ;allied dolphin
AltCameo=DLPHUICO ; MOD

[AEGIS]
AltCameo=AGISUICO ; MOD

[CARRIER]
AltCameo=CARRUICO ; MOD

[DRED]
AltCameo=DREDUICO ; MOD

[DEST]
AltCameo=DESTUICO ; MOD

[TELE] ; Telekenetic Tank
SecondaryFireFLH=85,0,130  ; Ares

[HIND] ; new art for shadow transport
Cameo=HINDICON
AltCameo=HINDUICO
Voxel=yes
UseBuffer=yes
DisableVoxelCache=yes ; SJM: this is a major cache hog
DisableShadowCache=yes ; SJM: this too
Remapable=yes
TurretOffset=40
PrimaryFireFLH=160,0,50
ShadowIndex=1 ;order of voxels got changed

[NIMITZ];[CARRIERB]
Cameo=NMTZICON
AltCameo=NMTZUICO
;PrimaryFireFLH=240,0,20 ; offset for take off
Voxel=yes
Remapable=yes

[YURIG] ; Yuri Prime in RA2
Cameo=YURPICON
AltCameo=YURPUICO
Sequence=YuriPrSequence
Crawls=yes
Remapable=yes
FireUp=6
PrimaryFireFLH=10,0,195
SecondaryFireFLH=10,0,195 ; SJM: brain blast should come from head, not feet

[HWTZ]   ; Howitzer
Cameo=HWTZICON ; TICKICON
AltCameo=HWTZUICO ; MOD

[VLAD]
Cameo=VLADICON ;CARRICON
AltCameo=VLADUICO ; MOD

[IVAN] ; Crazy Ivan
AltCameo=IVANUICO ; Add

[CIVAN] ; Chrono Ivan
AltCameo=IVNCUICO ; Add
```

## rulesmd.ini

### Global

```ini
[General]
BountyEnablers=none ; Ares 0.C (list of BuildingTypes)
TypeSelectUseDeploy=no  ; Ares 0.5 (boolean)
ReturnStructures=yes  ; Ares 0.6

;** Paratroops **

AmerParaDropInf=E1,GGI ;Types of infantry for the planes to drop
AmerParaDropNum=6,2 ;How many of each of those infantry

;********* Building prerequisite categories are specified here.
PrerequisiteTech=GATECH,NATECH,YATECH,CASLAB ; MOD

;***Crazy Ivan stuff***
CanDetonateTimeBomb=yes  ;no ;gs Turn this on to restore double click functionality on enemy bombs (actually easier than pulling out the Event)

[AudioVisual]
BountyDisplay=yes  ; Ares 0.C

[CombatDamage]
AutoRepel=yes  ; Ares 0.7
PlayerAutoRepel=yes  ; Ares 0.7

[CrateRules]
RandomCrateMoney=1000  ; Ares 0.C

[MouseCursors]  ; Ares 0.D
; Name=Frame(start with 0),Count,Interval,MiniFrame,MiniCount,HotSpotX,HotSpotY
GuardEscort=68,5,4,73,5,Center,Middle
DesolatorDeploy=78,10,4,-1,-1,Center,Middle
UnDeploy=120,9,4,-1,-1,Center,Middle
Disguise=199,5,4,-1,-1,Center,Middle
IvanBomb=204,5,4,-1,-1,Center,Middle
MindControl=209,5,4,-1,-1,Center,Middle
RemoveSquid=214,5,4,-1,-1,Center,Middle
Crush=219,5,4,-1,-1,Center,Middle
SpyTech=224,5,4,-1,-1,Center,Middle
SpyPower=229,5,4,-1,-1,Center,Middle
Harvest=234,5,4,73,5,Center,Middle
Paradrop=259,10,4,516,1,Center,Middle
GIDeploy=239,10,4,-1,-1,Center,Middle
PsiWave=249,10,4,-1,-1,Center,Middle
Rally=269,10,4,-1,-1,Center,Bottom
TogglePower=339,6,4,-1,-1,Center,Middle
NoTote=345,1,0,52,1,Center,Middle
InfantryHeal=351,5,4,-1,-1,Center,Middle
Disarm=369,15,4,-1,-1,Center,Middle
DeployMove=413,9,4,-1,-1,Center,Middle
PsychicDominator=488,8,4,516,1,Center,Middle
NoRally=432,1,0,52,1,Center,Bottom
StealCash=517,10,4,100,10,Center,Middle
Sabotage=527,10,4,100,10,Center,Middle
NoTogglePower=537,1,0,-1,-1,Center,Middle
RepairDepot=538,20,4,100,10,Center,Middle
```

### House & Side

(No modifications yet)

### Infantry

Register list below

```ini
[InfantryTypes]
66=YURIG
```

```ini
[IVAN]
Trainable=yes  ;no

[CIVAN] ; anybody gets into a soviet tech center
Trainable=yes  ;no ;gs like regular ivan, since can't gain experience

[ADOG],[YADOG],[YDOG]
GroupAs=DOG  ; Ares 0.5 (string)

[ENGINEER],[SENGINEER],[YENGINEER]
Cursor.Move=Tote  ; Ares 0.D
Cursor.NoMove=NoTote  ; Ares 0.D
GroupAs=ENGINEER  ; Ares 0.5 (string)

[E1],[GGI]
Cursor.Deploy=GIDeploy  ; Ares 0.D

[DESO]
Cursor.Deploy=DesolatorDeploy  ; Ares 0.D

[SPY]
Cursor.Move=Tote  ; Ares 0.D
Cursor.NoMove=NoTote  ; Ares 0.D

[TANY]
Bounty=yes  ; Ares 0.C
Bounty.RookieValue=700  ; Ares 0.C
Bounty.VeteranValue=1000  ; Ares 0.C
Bounty.EliteValue=1500  ; Ares 0.C

[BORIS]
IFVMode=12 ;4
Experience.FromAirstrike=yes ; Ares 0.2
Experience.AirstrikeModifier=0.2 ; Ares 0.2
Bounty=yes  ; Ares 0.C
Bounty.RookieValue=700  ; Ares 0.C
Bounty.VeteranValue=1000  ; Ares 0.C
Bounty.EliteValue=1500  ; Ares 0.C

[YURI] ;Bender of spoons!
Trainable=yes  ;no
ElitePrimary=MindControlV
Cursor.Deploy=PsiWave  ; Ares 0.D
Experience.MindControlSelfModifier=0.1  ; Ares 0.2
Experience.MindControlVictimModifier=0.9  ; Ares 0.2

[YURIG] ; Yuri Prime in RA2
UIName=Name:YURIPR
Name=Yuri G
Category=Soldier
;Image=YURI
Prerequisite=NAHAND
; RequiresStolenSovietTech=yes
Primary=SuperMindControlG
Secondary=PsiWave
CrushSound=InfantrySquish
Crushable=no
TiberiumProof=yes
Strength=200
Armor=flak
TechLevel=-1
Pip=red
Sight=8
Speed=6
Owner=Russians,Confederation,Africans,Arabs
AllowedToStartInMultiplayer=no
Cost=2000
Soylent=1000 ;250
Points=50
IsSelectableCombatant=yes
VoiceSelect=YuriSelect
VoiceMove=YuriMove
VoiceAttack=YuriAttackCommand
VoiceFeedback=
VoiceSpecialAttack=YuriMove
DieSound=YuriDie
Locomotor={4A582744-9839-11d1-B709-00A024DDAFD1};
PhysicalSize=1
MovementZone=Infantry
ThreatPosed=25 ; This value MUST be 0 for all building addons
SpecialThreatValue=1
ImmuneToVeins=yes
VeteranAbilities=STRONGER,FIREPOWER,ROF,SIGHT,FASTER
EliteAbilities=SELF_HEAL,STRONGER,FIREPOWER,ROF
ImmuneToPsionics=yes
;Bombable=no
Deployer=yes
DeployFire=yes
UndeployDelay=75
Size=1
BuildLimit=1
CanPassiveAquire=no ; Won't try to pick up own targets
IFVMode=8
Experience.MindControlSelfModifier=0.3  ; Ares 0.2
Experience.MindControlVictimModifier=0.7  ; Ares 0.2
ursor.Deploy=PsiWave  ; Ares 0.D
Bounty.RookieValue=1000  ; Ares 0.C
Bounty.VeteranValue=1500  ; Ares 0.C
Bounty.EliteValue=2000  ; Ares 0.C

[YURIPR]
ImmuneToPsionicWeapons=yes ;gs Patch
Trainable=yes ;no
ElitePrimary=SuperMindControlE
Experience.MindControlSelfModifier=0.4  ; Ares 0.2
Experience.MindControlVictimModifier=0.6  ; Ares 0.2
Cursor.Deploy=PsiWave  ; Ares 0.D
Bounty.RookieValue=700  ; Ares 0.C
Bounty.VeteranValue=1000  ; Ares 0.C
Bounty.EliteValue=1500  ; Ares 0.C
```

### Vehicle

Register list below

```ini
[VehicleTypes]
29=NIMITZ;CARRIERB
```

```ini
[MIND]
Trainable=yes ;no
ElitePrimary=MultipleMindControlTankE
Experience.MindControlSelfModifier=0.2  ; Ares 0.2
Experience.MindControlVictimModifier=0.8  ; Ares 0.2

[TTNK]
; Add Passenger
PipScale=Passengers
Passengers=1
OpenTopped=yes ;passengers can shoot out
SizeLimit=1
EnterTransportSound=EnterTransport
LeaveTransportSound=ExitTransport
Experience.PromotePassengers=yes ; Ares 0.2
Experience.PassengerModifier=0.8 ; Ares 0.2

; Tank Destroyer
[TNKD]
; Add Passenger
PipScale=Passengers
Passengers=1
OpenTopped=yes ;passengers can shoot out
SizeLimit=1
EnterTransportSound=EnterTransport
LeaveTransportSound=ExitTransport
Experience.PromotePassengers=yes ; Ares 0.2
Experience.PassengerModifier=0.8 ; Ares 0.2

[BFRT]
TrainPassengers=yes;gv score to inf
Experience.PromotePassengers=yes ; Ares 0.2
Experience.PassengerModifier=0.6 ; Ares 0.2

[FV]
Experience.PromotePassengers=yes ; Ares 0.2
Experience.PassengerModifier=0.6 ; Ares 0.2

EliteWeapon2=RepairBulletE  ;Engineer
EliteWeapon3=CRM60E  ;GI
EliteWeapon4=CRFlakGuyGunE    ;Flak Troop ;Rocketeer
EliteWeapon7=CRElectricBoltE  ;ShockTrooper
Weapon13=CRAKM    ;Boris  CowShot    ;Cow
EliteWeapon13=CRAKME    ;Boris  CowShot    ;Cow
EliteWeapon14=CRPsychicJabE    ;Initiate
EliteWeapon17=CRMissileLauncherE    ;Guardian GI

CowTurretIndex=1 ;3

[AEGIS]
Primary=MedusaS ; Anti-surface weapon for Aegis
Secondary=Medusa
; NavalTargeting=6
; LandTargeting=1
Cost=1500 ;1200
Soylent=1500 ;1200
Points=50 ;35
ElitePrimary=MedusaSE ; Anti-surface weapon for Aegis
EliteSecondary=MedusaE

[VLAD]
; ForbiddenHouses=Russians
EliteAbilities=SELF_HEAL,STRONGER,FIREPOWER,ROF,SENSORS,GUARD_AREA
BuildLimit=1

;## Howitzer
[HOWI]
Cost=900 ;750
ElitePrimary=HowitzerGunE

;Aircraft Carrier for the Americans
[NIMITZ];[CARRIERB]
UIName=Name:CARRIERB
Name=Aircraft Carrier Nimitz
; Image=CARRIER
Prerequisite=GAYARD,GATECH
Primary=HornetLauncher
CanPassiveAquire=no ; Won't try to pick up own targets
Spawns=HORNET
SpawnsNumber=4 ;3
SpawnRegenRate=400 ;5000
SpawnReloadRate=100 ;1000 ;150
FireAngle=32
ToProtect=yes
Category=Support
Strength=1500 ;800
Naval=yes ;GS
Armor=heavy
TechLevel=-1
Sight=7
Speed=6 ;4
CrateGoodie=no ;yes
Owner=British,French,Germans,Americans,Alliance
; RequiredHouses=Americans
AllowedToStartInMultiplayer=no
Cost=2500
Turret=no
Points=55
ROT=1
Crusher=yes
Weight=5
Crewed=no
;OmniFire=yes ;GEF moved to weapon
IsSelectableCombatant=yes
Explosion=TWLT070,S_BANG48,S_BRNL58,S_CLSN58,S_TUMU60
VoiceSelect=AircraftCarrierSelect
VoiceMove=AircraftCarrierMove
VoiceAttack=AircraftCarrierAttackCommand
VoiceFeedback=
SinkingSound=GenLargeWaterDie
Locomotor={2BEA74E1-7CCA-11d3-BE14-00104B62A16C};{4A582741-9839-11d1-B709-00A024DDAFD1}
SpeedType=Float
MovementZone=Water
ThreatPosed=30 ;25  ; This value MUST be 0 for all building addons
DamageParticleSystems=SparkSys,SmallGreySSys
VeteranAbilities=STRONGER,FIREPOWER,ROF,SIGHT,FASTER
EliteAbilities=SELF_HEAL,STRONGER,FIREPOWER,ROF,SENSORS,FASTER,GUARD_AREA
TooBigToFitUnderBridge=true
GuardRange=10
BuildLimit=1
Size=50
Trainable=yes ;no
Experience.SpawnOwnerModifier=0.6  ; Ares 0.2
Experience.SpawnModifier=0.6  ; Ares 0.2

[CARRIER]
Trainable=yes
Experience.SpawnOwnerModifier=0.5  ; Ares 0.2
Experience.SpawnModifier=0.5  ; Ares 0.2

[DEST],[CDEST],
Experience.SpawnOwnerModifier=0.5  ; Ares 0.2
Experience.SpawnModifier=0.5  ; Ares 0.2

; Hind Transport
[HIND]
Prerequisite=NAWEAP
TechLevel=-1
RequiredHouses=Confederation
ElitePrimary=BlackHawkCannonE

[CMIN],[AMCV],[SMCV],[PCV],[LCRF],[SAPC],[YHVR]
Cursor.Move=Tote  ; Ares 0.D
Cursor.NoMove=NoTote  ; Ares 0.D

[CMIN]
Bounty.Value=1000  ; Ares 0.C

[HARV]
Bounty.RookieValue=700  ; Ares 0.C
Bounty.VeteranValue=1000  ; Ares 0.C
Bounty.EliteValue=1400  ; Ares 0.C

[SMIN]
Bounty.RookieValue=700  ; Ares 0.C
Bounty.VeteranValue=1000  ; Ares 0.C
Bounty.EliteValue=1500  ; Ares 0.C

[CAOS]
Cursor.Deploy=DeployMove  ; Ares 0.D

[SCHD]
Cursor.Deploy=UnDeploy  ; Ares 0.D

```

### Aircraft

```ini
; Destroyer's helicopter
[ASW]
UIName=Name:ASW
Name=Osprey
VeteranAbilities=SELF_HEAL,FIREPOWER ; MOD
EliteAbilities=STRONGER,FIREPOWER ; MOD
```

### Building

```ini
[NATECH], [YATECH], [GATECH]
Armory=yes
Ammo=1
Cursor.Spy=SpyTech  ; Ares 0.D

[GACNST],[NACNST],[YACNST]
Spyable=yes
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.RevealProduction=yes  ; Ares 0.B
Cursor.Spy=SpyTech  ; Ares 0.D
Cursor.Move=UnDeploy  ; Ares 0.D
SpyEffect.NavalVeterancy=yes  ; Ares 2.0

[GAAIRC]
Cursor.Spy=Sabotage  ; Ares 0.D
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.ResetRadar=yes  ; Ares 0.1
SpyEffect.RevealProduction=yes  ; Ares 0.B
SpyEffect.AircraftVeterancy=yes  ; Ares 2.0

[GAPILE],[GAWEAP],[NAHAND],[NAWEAP],[YABRCK],[YAWEAP]
Cursor.Move=Rally  ; Ares 0.D
Cursor.NoMove=NoRally  ; Ares 0.D
Cursor.Spy=SpyTech  ; Ares 0.D
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.RevealProduction=yes  ; Ares 0.B

[GAPILE],[NAHAND],[YABRCK]
SpyEffect.InfantryVeterancy=yes  ; Ares 2.0

[GAWEAP],[NAWEAP],[YAWEAP]
SpyEffect.VehicleVeterancy=yes  ; Ares 2.0

[GAROBO]
Spyable=yes
Cursor.Spy=Sabotage  ; Ares 0.D
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.SabotageDelay=300  ; Ares 0.E

[AMRADR],[NARADR],[NAPSIS]
Cursor.Spy=Sabotage  ; Ares 0.D
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.ResetRadar=yes  ; Ares 0.1
SpyEffect.ResetSuperweapons=yes  ; Ares 0.B
SpyEffect.SuperWeapon= ; Ares 0.B (SuperWeaponType)
SpyEffect.AircraftVeterancy=yes  ; Ares 2.0

[GASPYSAT]
Spyable=yes
Cursor.Spy=SpyTech  ; Ares 0.D
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.RevealRadar=yes  ; Ares 0.1

[NAINDP],[GAOREP]
Spyable=yes
Cursor.Spy=StealCash  ; Ares 0.D
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.StolenMoneyAmount=2000 ; Ares 0.1

[NACLON]
Cursor.Move=Rally  ; Ares 0.D
Cursor.NoMove=NoRally  ; Ares 0.D
Spyable=yes
Cursor.Spy=StealCash  ; Ares 0.D
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.StolenMoneyAmount=2000 ; Ares 0.1

[GAPOWR],[NAPOWR],[NANRCT]
Cursor.Spy=SpyPower  ; Ares 0.D
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.PowerOutageDuration=  ; Ares 0.1 (1000) see [General]►SpyPowerBlackout
SpyEffect.RevealProduction=yes  ; Ares 0.B

[YAPOWR]
Cursor.Enter=InfantryAbsorb  ; Ares 0.D
Cursor.Spy=SpyPower  ; Ares 0.D
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.PowerOutageDuration=  ; Ares 0.1 (1000) see [General]►SpyPowerBlackout
SpyEffect.RevealProduction=yes  ; Ares 0.B

[GAREFN],[NAREFN],[YAREFN]
Cursor.Spy=StealCash  ; Ares 0.D
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.RevealProduction=yes  ; Ares 0.B
SpyEffect.StolenMoneyPercentage=0.2  ; Ares 0.B

[YAREFN]
Cursor.Move=UnDeploy  ; Ares 0.D
GroupAs=SMIN  ; Ares 0.5 (string)
Bounty.RookieValue=700  ; Ares 0.C
Bounty.VeteranValue=1000  ; Ares 0.C
Bounty.EliteValue=1500  ; Ares 0.C

[GADEPT],[GAYARD],[NADEPT],[NAYARD],[YAYARD]
Cursor.Enter=RepairDepot  ; Ares 0.D
Cursor.Move=Rally  ; Ares 0.D
Cursor.NoMove=NoRally  ; Ares 0.D

[YAGRND]
Cursor.Enter=SellUnit  ; Ares 0.D


[GACSPH],[NAIRON],[YAGNTC]
Cursor.Spy=Sabotage  ; Ares 0.D
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.ResetSuperweapons=yes  ; Ares 0.B
SpyEffect.SuperWeapon= ; Ares 0.B (SuperWeaponType)

[GAWEAT],[NAMISL],[YAPPET]
Cursor.Spy=Sabotage  ; Ares 0.D

[CATHOSP]
Academy.InfantryVeterancy=0.5  ; Ares 0.8

[CAMACH]
Academy.VehicleVeterancy=0.5  ; Ares 0.8

[CAOUTP]
HasRadialIndicator=true ;no
Cursor.Enter=RepairDepot  ; Ares 0.D
Academy.AircraftVeterancy=1.0  ; Ares 0.8

[GAPILL],[NASAM],[ATESLA],[GTGCAN],[NALASR],[NAFLAK],[TESLA],[YAGGUN],[YAPSYT],
HasRadialIndicator=true ;no

[CAAIRP]
Spyable=yes
Cursor.Spy=SpyTech  ; Ares 0.D
SpyEffect.Custom=yes  ; Ares 0.1
SpyEffect.ResetSuperweapons=yes  ; Ares 0.B
SpyEffect.SuperWeapon=ParaDropSpecial ; Ares 0.B

[CASLAB]
Armory=yes
Ammo=1
SecretLab.GenerateOnCapture=yes ; Ares 0.9 (boolean)
SecretLab.PossibleBoons=BEAG,BFRT,FV,GAOREP,GASPYSAT,HOWI,LUNR,NACLON,NAINDP,NANRCT,NAPSIS,NIMITZ,SMIN,SPY,SNIPE,VLAD ; Ares 0.9 (list of TechnoTypes)
Academy.InfantryVeterancy=1.0  ; Ares 0.8
Academy.VehicleVeterancy=1.0  ; Ares 0.8
Academy.Types=DEST,DLPH,AEGIS,CARRIER,HYD,SUB,SQD,DRED,BSUB,VLAD,NIMITZ  ; Ares 0.8
```

### Weapon

```ini
;boris
[CRAKM]
Damage=50 ;65
ROF=15 ;20
Range=8 ;7
Projectile=InvisibleLow
Speed=100
Warhead=BORISWH
Report=BorisAttack
Anim=MGUN-N,MGUN-NE,MGUN-E,MGUN-SE,MGUN-S,MGUN-SW,MGUN-W,MGUN-NW

[CRAKME]
Damage=75 ;90
ROF=15 ;20
Range=10 ;9
Projectile=InvisibleLow
Speed=100
Warhead=BORISWH
Report=BorisAttack
Anim=MGUN-N,MGUN-NE,MGUN-E,MGUN-SE,MGUN-S,MGUN-SW,MGUN-W,MGUN-NW

;GI Missile Launcher
[CRMissileLauncherE]
Damage=35 ;30
ROF=40
Range=8
Burst=4 ;2
Projectile=AAHeatSeeker2  ;AirToGroundMissile
Speed=45 ;30 ;40
Warhead=GUARDWH
Report=GuardianGIDeployedAttack
MinimumRange=1

[CRPsychicJabE]
Damage=30 ;25
ROF=12 ;15
Range=6.5
Projectile=InvisibleLow
Speed=100
Warhead=SAFlame
Report=InitiateAttack

; Fire by Telsa Trooper
[CRElectricBoltE]
Damage=65;60;50
ROF=40;45;40 ;changed on 11/29 from 30 to 45
Range=6;3
Speed=100
Warhead=Shock
Report=TeslaTankAttack
Projectile=Electricbounce;InvisibleLow
IsElectricBolt=true
AssaultAnim=UCELEC;the anim to play when a UC building is cleared (assaulters need this on their primary weapon)

[CRFlakGuyGunE]    ; Anti-surface gun for the Flak Trooper
Damage=35;30;20
ROF=12;15;20
Range=7;5
Projectile=FlakTProj
Speed=50
Report=FlakTrackAttackGround    ; put in new sound for this
Warhead=FlakTWH
Anim=GUNFIRE

[CRM60E]
Damage=40 ;25
ROF=15
Range=6;4
Projectile=InvisibleLow
Speed=100
Warhead=SSA
Report=IFVAttackGround
Anim=MGUN-N,MGUN-NE,MGUN-E,MGUN-SE,MGUN-S,MGUN-SW,MGUN-W,MGUN-NW

; repair bot repairing
[RepairBulletE]
Damage=-50 ;-50
ROF=60 ;80
Range=1.8
Projectile=Invisible
Speed=100
Warhead=Mechanical
Report=IFVRepair
UseSparkParticles=yes
AttachedParticleSystem=WeldingSys

; Anti-surface weapon for Aegis
[MedusaS]
Damage=40  ;100
ROF=75  ;15
Range=6  ;12
Speed=60  ;120
Projectile=MedusaSProjectile ; Anti-surface heatseeker for the Aegis
Warhead=MDSWH ; For anti-surface weapon MedusaS
Report=AegisAttack
; TurboBoost=yes
; OmniFire=yes

; Anti-surface weapon for Aegis
[MedusaSE]
Damage=40  ;100
ROF=50  ;5
Range=7  ;14
Speed=75  ;150
Projectile=MedusaSProjectile ; Anti-surface heatseeker for the Aegis
Warhead=MDSWH ; For anti-surface weapon MedusaS
Report=AegisAttack
TurboBoost=yes
; OmniFire=yes
Burst=2

;Howitzer Elite
[HowitzerGunE]
Damage=80 ;75
ROF=90 ;100
Range=14 ;12
MinimumRange=2
Projectile=Ballistic
Speed=100
Warhead=HowitzerWHE ;HowitzerWH
Report=ApocalypseAttackGround
Anim=GUNFIRE
Bright=yes

[MindControl],[MindControlE],[SuperMindControl],[MultipleMindControlTank],[MultipleMindControlTower],
Cursor.Attack=MindControl  ; Ares 0.D
Cursor.AttackOutOfRange=MindControl  ; Ares 0.D

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

[SuperMindControlE]
Damage=3;1;Number of mind control links
ROF=200
Range=8;7
Projectile=PsychicControl
Speed=100
Warhead=ControllerBuilding
;Report=YuriMindControl
Anim=YURICNTL
FireOnce=yes
Cursor.Attack=MindControl  ; Ares 0.D
Cursor.AttackOutOfRange=MindControl  ; Ares 0.D

[SuperMindControlG]
Damage=10;Needed to be considered offensive unit
ROF=200
Range=30
Projectile=PsychicControl
Speed=100
Warhead=Controller
;Report=YuriMindControl
Anim=YURICNTL
FireOnce=yes
Cursor.Attack=MindControl  ; Ares 0.D
Cursor.AttackOutOfRange=MindControl  ; Ares 0.D


[MakeupKit]
Cursor.Attack=Disguise  ; Ares 0.D
Cursor.AttackOutOfRange=Disguise  ; Ares 0.D

[Demobomb]
Cursor.AttackOutOfRange=Nuke  ; Ares 0.D
```

### Projectile

```ini
; Anti-surface heatseeker for the Aegis
[MedusaSProjectile]
Arm=1
High=yes
Shadow=no
AA=no  ;yes
AG=yes  ;no
;AN=no
Image=MEDUSA
CourseLockDuration=15
ROT=20
Scalable=yes
SubjectToCliffs=yes  ;no
SubjectToElevation=no
SubjectToWalls=yes  ;no
```

### Particle & Particle System

(No modifications yet)

### Warhead

Register list below.

```ini
[Warheads]
106=MDSWH  ; For anti-surface weapon MedusaS
107=HowitzerWHE
```

```ini
[MDSWH]  ; For anti-surface weapon MedusaS
CellSpread=.3
PercentAtMax=1
Verses=100%,75%,50%,75%,50%,25%,0%,0%,0%,100%,100%
; Verses=100%,100%,100%,100%,100%,100%,0%,0%,0%,100%,100%
InfDeath=3
AnimList=XGRYSML1,XGRYSML2,EXPLOSML
ProneDamage=100%
Conventional=yes  ; Go splash in the water.

;Howitzer Elite
[HowitzerWHE]
CellSpread=1
PercentAtMax=.5
Wall=yes
Wood=yes
Verses=100%,90%,80%,60%,50%,40%,50%,40%,25%,100%,100%
Conventional=yes
InfDeath=3
AnimList=S_CLSN16,S_CLSN22,S_CLSN30,S_CLSN42,S_CLSN58
ProneDamage=50%
```

### Terrain & Smudge & Overlay

(No modifications yet)

### Super Weapon

(No modifications yet)

### Animation

Register list below.

```ini
[Animations]
1072=APOCEXP  ; Ares
```
