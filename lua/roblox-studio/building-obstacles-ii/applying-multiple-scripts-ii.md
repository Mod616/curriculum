---
author: junoocha
type: normal
category: best-practice
practiceQuestion:
  formats:
    - fill-in-the-gap
  context: standalone
revisionQuestion:
  formats:
    - fill-in-the-gap
  context: standalone

---

# Applying Multiple Scripts Continuation

---

## Content

Now that we have models, we will be **using a pairs loop** to iterate through every part in the model and apply the script to each part. 

For instance, let's code a script such that every part in a model will act as a kill brick.

```lua
local Model = game.Workspace.Model 
--declare Model as a variable

for i,v in pairs(Model:GetChildren()) do 
--use the getChildren() function to iterate through each part

	if v:IsA("BasePart") then
  --if each child in the model is a BasePart

		v.Touched:Connect(function(part)
			local avatar = part.Parent  
			if avatar:FindFirstChild("Humanoid") then
				avatar.Humanoid.Health = 0
			end
		end)
    --the code that kills the avatar

	end
end
```
Through iterations, we are **no longer forced to create a copy of the script for every part** that needs the specific behaviour.

---
