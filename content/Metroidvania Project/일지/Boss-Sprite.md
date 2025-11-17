[[Boss-Anim]]
## 기능 순서도
- `default`: 돌덩이 들고다니는
	- ⇒ `mode1`: `Golem_AttackA`
	- ⇒ `mode2`: `Golem_Upgrade`
- `mode1`: 돌덩이 없는(Run이 없다?)
	- ⇒ `default`: `Golem_Reset`
- `mode2`: Armor(Upgrade)
	- ⇒ `default`: `Golem_Armor_ArmorBreak`

## 목록
`default`
- `Golem_IdleB`
- `Golem_HitB` 
- `Golem_DeathB`
- `Golem_Run`
- `Golem_AttackA` ⇒ `mode1`
- `Golem_Upgrade` ⇒ `mode2`

`mode1`
- `Golem_IdleA`
- `Golem_HitA`
- `Golem_DeathA`
- `Golem_AttackB`
- `Golem_AttackC`
- `Golem_Reset`

`mode2`
- `Golem_Armor_Idle`                                
- `Golem_Armor_Run`                                 
- `Golem_Armor_Hit`                                 
- `Golem_Armor_AttackA`                             
- `Golem_Armor_AttackB`                             
- `Golem_Armor_AttackC`                             
- `Golem_Armor_Ability`                             
- `Golem_Armor_ArmorBreak`                          

효과
- `Golem_AttackA_FX`                                
- `Golem_AttackB_FX`                                
- `Golem_AttackC_FX`                                
- `Golem_Death_FX`                                  
- `Golem_Armor_AttackA_FX`                          
- `Golem_Armor_AttackB_FX`                          
- `Golem_Armor_AttackC_FX`                          
