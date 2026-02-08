local Players = game:GetService("Players")
local player = Players.LocalPlayer

local teamSelectGui = player.PlayerGui:FindFirstChild("TeamSelect")

if teamSelectGui then
    teamSelectGui.Enabled = true
    
    local existingClose = teamSelectGui:FindFirstChild("CloseTeamSelect")
    if existingClose then
        existingClose:Destroy()
    end
    
    local closeButton = Instance.new("TextButton")
    closeButton.Name = "CloseTeamSelect"
    closeButton.Size = UDim2.new(0, 60, 0, 60)
    closeButton.Position = UDim2.new(1, -70, 0, 10)
    closeButton.BackgroundColor3 = Color3.fromRGB(255, 50, 50)
    closeButton.Text = "✖"
    closeButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    closeButton.TextSize = 32
    closeButton.Font = Enum.Font.GothamBold
    closeButton.BorderSizePixel = 0
    closeButton.ZIndex = 10000
    closeButton.Parent = teamSelectGui
    
    local closeCorner = Instance.new("UICorner")
    closeCorner.CornerRadius = UDim.new(0, 12)
    closeCorner.Parent = closeButton
    
    local closeStroke = Instance.new("UIStroke")
    closeStroke.Color = Color3.fromRGB(255, 255, 255)
    closeStroke.Thickness = 3
    closeStroke.Parent = closeButton
    
    closeButton.MouseButton1Click:Connect(function()
        teamSelectGui.Enabled = false
        print("✅ TeamSelect fechado!")
    end)
    
    print("✅ TeamSelect aberto com botão X!")
else
    warn("❌ TeamSelect GUI não encontrado!")
end
