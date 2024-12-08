-- Criação da GUI
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local KeyBox = Instance.new("TextBox")
local VerifyButton = Instance.new("TextButton")
local CopyButton = Instance.new("TextButton")
local InfoLabel = Instance.new("TextLabel")
local UICorner = Instance.new("UICorner")

-- Propriedades da GUI
ScreenGui.Name = "KeySystem"
ScreenGui.Parent = game.CoreGui

Frame.Name = "MainFrame"
Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
Frame.BackgroundTransparency = 0.3
Frame.Position = UDim2.new(0.5, -150, 0.5, -100)
Frame.Size = UDim2.new(0, 300, 0, 200)
Frame.Active = true
Frame.Draggable = true

UICorner.Parent = Frame

KeyBox.Name = "KeyBox"
KeyBox.Parent = Frame
KeyBox.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
KeyBox.BackgroundTransparency = 0.2
KeyBox.Position = UDim2.new(0.1, 0, 0.3, 0)
KeyBox.Size = UDim2.new(0.8, 0, 0.2, 0)
KeyBox.Font = Enum.Font.SourceSans
KeyBox.PlaceholderText = "Digite sua Key aqui"
KeyBox.Text = ""
KeyBox.TextColor3 = Color3.fromRGB(255, 255, 255)
KeyBox.TextSize = 16

VerifyButton.Name = "VerifyButton"
VerifyButton.Parent = Frame
VerifyButton.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
VerifyButton.Position = UDim2.new(0.1, 0, 0.6, 0)
VerifyButton.Size = UDim2.new(0.35, 0, 0.2, 0)
VerifyButton.Font = Enum.Font.SourceSans
VerifyButton.Text = "Verificar"
VerifyButton.TextColor3 = Color3.fromRGB(255, 255, 255)
VerifyButton.TextSize = 16

CopyButton.Name = "CopyButton"
CopyButton.Parent = Frame
CopyButton.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
CopyButton.Position = UDim2.new(0.55, 0, 0.6, 0)
CopyButton.Size = UDim2.new(0.35, 0, 0.2, 0)
CopyButton.Font = Enum.Font.SourceSans
CopyButton.Text = "Copiar Key"
CopyButton.TextColor3 = Color3.fromRGB(255, 255, 255)
CopyButton.TextSize = 16

InfoLabel.Name = "InfoLabel"
InfoLabel.Parent = Frame
InfoLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
InfoLabel.BackgroundTransparency = 1
InfoLabel.Position = UDim2.new(0.1, 0, 0.1, 0)
InfoLabel.Size = UDim2.new(0.8, 0, 0.1, 0)
InfoLabel.Font = Enum.Font.SourceSans
InfoLabel.Text = "Obtenha sua key aqui: https://rekonise.com/teyzhub-key-system-mnzn5"
InfoLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
InfoLabel.TextSize = 14
InfoLabel.TextWrapped = true

-- Key correta
local correctKey = "de1ijhedu891hd78"

-- Funções dos botões
VerifyButton.MouseButton1Click:Connect(function()
    if KeyBox.Text == correctKey then
        -- Destruir a HUD
        ScreenGui:Destroy()
        -- Executar código desejado
        loadstring(game:HttpGet("https://raw.githubusercontent.com/teyzim/wadsdas/refs/heads/main/README.md", true))()
    else
        -- Mensagem de erro (se desejado)
        KeyBox.Text = ""
        KeyBox.PlaceholderText = "Key incorreta. Tente novamente."
    end
end)

CopyButton.MouseButton1Click:Connect(function()
    -- Copiar key correta para a área de transferência
    setclipboard(correctKey)
    KeyBox.PlaceholderText = "Key copiada!"
end)
