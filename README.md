local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

local Window = Library.CreateLib("MKXHUB", "DarkTheme")

local Tab = Window:NewTab("ฟามดาวตึงตึง")

local Section = Tab:NewSection("กด")

Section:NewButton("ButtonText", "ButtonInfo", function()

    game:GetService("ReplicatedStorage").RemoteFunction:InvokeServer("SetTeam", "Police")

wait(.70)

game:GetService("RunService").RenderStepped:Connect(function()

for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do

  if v.Name == "Handcuffs" then v.Parent = game:GetService("Players").LocalPlayer.Character

  end

end

game:GetService("ReplicatedStorage").Event:FireServer("Eject", game:GetService("Players").LocalPlayer)

end)

end)
