---
author: junoocha
type: normal
category: must-know
practiceQuestion:
  formats:
    - fill-in-the-gap
  context: standalone
revisionQuestion:
  formats:
    - fill-in-the-gap
  context: standalone

---

# Making Platforming Interesting

---

## Content

Sure, platforming sounds boring, but this is Roblox! Make it exciting by changing the properties! 

Go for quick design changes by changing color, transparency, even reflection! Maybe try combining properties with specific behaviour, such as removing collision when a platform is fully transparent!

```lua
partVar = game.Workspace.Part
local TweenService = game.TweenService
local PropertyTable1 = {
	Transparency = 1; --first change in making it transparent
}

local PropertyTable2 = {
	Transparency = 0; --second change in making it not transparent
}

local info = TweenInfo.new(10, Enum.EasingStyle.Linear, Enum.EasingDirection.Out, 0, false, 0)
-- rememeber to set repeatCount to 0 since we want one animation to play after the other.
local Tween1 = TweenService:Create(partVar, info, PropertyTable1)
local Tween2 = TweenService:Create(partVar, info, PropertyTable2)

while true do
	Tween1:Play() --making it transparent
	wait(10)
	partVar.CanCollide = false --remember to declare the part variable
	wait(5)
	partVar.CanCollide = true
	Tween2:Play() --making it opaque
	wait(10)
	--wait() here is used to give players time
	--but don't forget that wait() is required for these types of loops
end
```

---

## Practice

---

## Revision


---
## Footnotes
