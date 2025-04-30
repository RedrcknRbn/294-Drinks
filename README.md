# Vending Machine 294 Documentation

This repository contains the documentation and drinks for [Vending Machine 294](https://www.roblox.com/games/106262532227098/Vending-Machine-294)
If you want to add or edit drinks, make a [Pull Request](https://github.com/RedrcknRbn/294-Drinks/pulls) changing [DrinkModule.luau](https://github.com/RedrcknRbn/294-Drinks/blob/main/DrinkModule.luau), or DM me on [Bluesky](https://bsky.app/profile/acyt.lol)

---
# Documentation

Current properties, Bolded are **Required**:

- ***[Aliases](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#aliases)***

*Decoration*
 - ***[Color](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#color)***
 - ***[Transparency](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#transparency)***
 - [Glow](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#glow)

*Sounds*
 - [Drink Sound](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#drink-sound)
 - ***[Dispense Sound](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#dispense-sound)***

*Messages*
 - [Message](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#message)
 - [Additional Messages](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#additional-messages)

*Effects*
 - [Blur](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#blur)
 - [Damage](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#damage)
 - [Blood Loss](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#blood-loss)
 - [Walk Speed](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#walk-speed)
 - [Gravity](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#gravity)

*Lethal Effects*
 - [Explode](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#explode)
 - [Lethal](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#lethal)
 - [Death Timer](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#death-timer)
 - [Kick](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#kick)

---
## Aliases
`aliases:table`

**Required**

List of drink names | Keep in Lowercase
### Alias
`string`

Name for drink
```lua
{aliases = {"template","temp"}
```

---
## Color
`color:Color3`

**Required**

Color of the liquid | RGB, 0-255
```lua
color=Color3.fromRGB(255,255,255)
```

---
## Transparency
`transparency:number`

**Required**

Transparency of the liquid | 0 is solid, 1 is invisible/nothing, put 1 if nothing is dispensed
```lua
transparency=0.5
```

---
## Glow
`glow:bool`

Whether the liquid uses neon
```lua
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
- vomit
- yeah
```lua
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
```lua
dispensesound="dispense3"
```

---
## Message
`message:string`

Message displayed upon drinking | Each message lasts for 9 seconds | %s will use the user's display name
```lua
message="Ah damn"
```

---
## Additional Messages
`additionalmessages:table`

Table of additional messages | Always use this AFTER [Message](https://github.com/RedrcknRbn/294-Drinks?tab=readme-ov-file#message), otherwise errors will occur!
### Time
`time:number`

Time to wait before displaying message
###  Message
`message:string`

Message to display
```lua
additionalmessages={
			{time=9,message="I regret this"},
			{time=18,message="It gets worse and worse!"}
		},
```

---
## Blur
`blur:number`

The amount of blurring the drink causes, changes the blur effect in lighting\*3 | If death is imminent, time the blur by the death time + 3, as it takes 3 seconds to respawn
```lua
blur=21
```

---
## Damage
`damage:number`

Damage taken upon drinking\*10
```lua
damage=5
```

---
## Blood Loss
`bloodloss:number`

Increases blood loss upon drinking (damage over time) | Goes down each second using the equation BloodLoss = BloodLoss/15 | Does the current amount of BloodLoss as damage
```lua
bloodloss=25
```

---
## Walk Speed
`walkspeed:number`

Changes WalkSpeed | WalkSpeed by default is 6
```lua
walkspeed=1
```

---
## Gravity
`gravity:number`

Changes Gravity | Gravity by default is 35 | 0 is no gravity | Negative gravity is not possible.
```lua
gravity=10
```

---
## Explode
`explode:bool`

Explodes the drink | Should never be used with messages
```lua
explode=true
```

---
## Lethal
`lethal:bool`

Kills the user immediately after drinking | Should never be used with messages
```lua
lethal=true
```

---
## Death Timer
`deathtimer:number`

Time till death after drinking
```lua
deathtimer=18
```

---
## Kick
`kick:bool`

Kicks the player after drinking | Should never be used with messages
```lua
kick=true
```

---
# 294 Drink Guide
This is the guide we follow when creating drinks. It includes info on how drinks should be made, and what the Vending Machine would dispense

SCP-294 prefers to dispense literal material, instead of figurative material. Dispensing flames will LITERALLY dispense a drink made of flames. Dispensing rain will dispense literal rain water.

SCP-294 will often melt metals in order to turn them into a liquid form.
SCP-294 also seems to have an attitude, as requesting "Surprise me" will dispense a drink that burns you.

SCP-294, as a result of dispensing literal elements/materials, can dispense skills, and the drinker will gain that skill temporarily. This also works with memories.

SCP-294 will attempt to grab nearby objects to turn into a drink, meaning if you put "me", it will grab your blood and dispense that, often resulting in fatality.

Do not be afraid to kill the user! Death and damage is a common element of this game, and happens frequently.

You don't need to describe drinks unless they have a unique taste. Not every drink will have a message.

```lua
-- The basic template, at minimum, a drink requires 1 alias, a color, a transparency, and a dispense sound.
{aliases = {"template","temp"},
		color=Color3.fromRGB(255,255,255),
		transparency=0.5,
		dispensesound="dispense0"},

-- Template with all possible options
{aliases = {"template","temp"},
		color=Color3.fromRGB(255,255,255),
		transparency=0.5,
		dispensesound="dispense3",
		drinksound="cough",
		glow=true,
		message="Ah damn",
		additionalmessages={
			{time=9,message="I regret this"},
			{time=18,message="It gets worse and worse!"}
		},
		blur=21,
		damage=5,
		bloodloss=25,
		deathtimer=18,
		walkspeed=1,
		gravity=10,
		explode=true,
		lethal=true,
		kick=true},
```