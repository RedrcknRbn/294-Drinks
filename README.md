# Vending Machine 294 Documentation

This repository contains the documentation and drinks for [Vending Machine 294](https://www.roblox.com/games/106262532227098/Vending-Machine-294)

---
# Documentation

Current properties, Bolded are **Required**:

- **[[#Aliases]]**

*Decoration*
 - **[[#Color]]**
 - **[[#Transparency]]**
 - [[#Glow]]

*Sounds*
 - [[#Drink Sound]]
 - **[[#Dispense Sound]]**

*Messages*
 - [[#Message]]
 - [[#Additional Messages]]

*Effects*
 - [[#Blur]]
 - [[#Damage]]
 - [[#Blood Loss]]
 - [[#Walk Speed]]
 - [[#Gravity]]

*Lethal Effects*
 - [[#Explode]]
 - [[#Lethal]]
 - [[#Death Timer]]
 - [[#Kick]]

---
## Aliases
`aliases:table`
**Required**
List of drink names | Keep in Lowercase
### Alias
`string`
Name for drink
```
{aliases = {"template","temp"}
```

---
## Color
`color:Color3`
**Required**
Color of the liquid | RGB, 0-255
```
color=Color3.fromRGB(255,255,255)
```

---
## Transparency
`transparency:number`
**Required**
Transparency of the liquid | 0 is solid, 1 is invisible/nothing, put 1 if nothing is dispensed
```
transparency=0.5
```

---
## Glow
`glow:bool`
Whether the liquid uses neon
```
glow=true
```

---
## Drink Sound
`drinksound:string`
The sound clip played upon drinking | Drink sound is always required if the drink is drank. Don't put anything if the character doesn't drink it
- ahh
- breath
- burn
- corpse
- decay
- ending
- ew1
- ew2
- inproximity
- nuke2
- retch1
- retch2
- slurp
- spit
- venom
- yeah
```
drinksound="cough"
```

---
## Dispense Sound
`dispensesound:string`
**Required**
The sound clip played upon dispensing
- dispense0 (Used for dispensing nothing/air)
- dispense1 (Regular drinks)
- dispense2 (Slightly irregular drinks)
- dispense3 (Anomalyous drinks)
- horror16 (Extremely loud horror noise)
- horror3
```
dispensesound="dispense3"
```

---
## Message
`message:string`
Message displayed upon drinking | Each message lasts for 9 seconds | %s will use the user's display name
```
message="Ah damn"
```

---
## Additional Messages
`additionalmessages:table`
Table of additional messages | Always use this AFTER [[#Message]], otherwise errors will occur!
### Time
`time:number`
Time to wait before displaying message
###  Message
`message:string`
Message to display
```
additionalmessages={
			{time=9,message="I regret this"},
			{time=18,message="It gets worse and worse!"}
		},
```

---
## Blur
`blur:number`
The amount of blurring the drink causes, changes the blur effect in lighting\*3 | If death is imminent, time the blur by the death time + 3, as it takes 3 seconds to respawn
```
blur=21
```

---
## Damage
`damage:number`
Damage taken upon drinking\*10
```
damage=5
```

---
## Blood Loss
`bloodloss:number`
Increases blood loss upon drinking (damage over time) | Goes down each second using the equation BloodLoss = BloodLoss/15 | Does the current amount of BloodLoss as damage
```
bloodloss=25
```

---
## Walk Speed
`walkspeed:number`
Changes WalkSpeed | WalkSpeed by default is 6
```
walkspeed=1
```

---
## Gravity
`gravity:number`
Changes Gravity | Gravity by default is 35 | 0 is no gravity | Negative gravity is not possible.
```
gravity=10
```

---
## Explode
`explode:bool`
Explodes the drink | Should never be used with messages
```
explode=true
```

---
## Lethal
`lethal:bool`
Kills the user immediately after drinking | Should never be used with messages
```
lethal=true
```

---
## Death Timer
`deathtimer:number`
Time till death after drinking
```
deathtimer=18
```

---
## Kick
`kick:bool`
Kicks the player after drinking | Should never be used with messages
```
kick=true
```