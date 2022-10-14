local UIS = game:GetService("UserInputService")
local camera = game.Workspace.CurrentCamera
function getClosest()
local closestPlayer = nil
local closesDist = math.huge
for i,v in pairs(game.Players:GetPlayers()) do
if v ~= game.Players.LocalPlayer and tostring(v.Team) ~= tostring(game.Players.LocalPlayer.Team) then
local Dist = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Character.HumanoidRootPart.Position).magnitude
if Dist < closesDist then
closesDist = Dist
closestPlayer = v
end
end
end
return closestPlayer
end

--> starting the aimbot
_G.aim = false
UIS.InputBegan:Connect(function(inp)
    if inp.UserInputType == Enum.UserInputType.MouseButton2 then
    _G.aim = true
    while wait() do
        camera.CFrame = CFrame.new(camera.CFrame.Position,getClosest().Character.Head.Position)
        if _G.aim == false then return end
    end
    end
end)
--> ending the aimbot
UIS.InputEnded:Connect(function(inp)
    if inp.UserInputType == Enum.UserInputType.MouseButton2 then
    _G.aim = false
    end
end)

while wait() do
     pcall(function()
       for i,v in pairs(game.Players:GetChildren()) do
            if not v.Character.Head:FindFirstChild("ESP") and tostring(v.Team) ~= tostring(game.Players.LocalPlayer.Team) then
                local BillboardGui = Instance.new("BillboardGui")
                local TextLabel = Instance.new("TextLabel")
                BillboardGui.Parent = v.Character.Head
                BillboardGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
                BillboardGui.Active = true
                BillboardGui.Name = "ESP"
                BillboardGui.AlwaysOnTop = true
                BillboardGui.LightInfluence = 1.000
                BillboardGui.Size = UDim2.new(0, 200, 0, 50)
                BillboardGui.StudsOffset = Vector3.new(0, 2.5, 0)
                TextLabel.Parent = BillboardGui
                TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                TextLabel.BackgroundTransparency = 1.000
                TextLabel.Size = UDim2.new(0, 200, 0, 50)
                TextLabel.Font = Enum.Font.GothamBold
                TextLabel.Text = v.Name
                TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
                TextLabel.TextScaled = true
                TextLabel.TextSize = 14.000
                TextLabel.TextStrokeTransparency = 0.000
                TextLabel.TextWrapped = true
            end
        end
    end) 
end
