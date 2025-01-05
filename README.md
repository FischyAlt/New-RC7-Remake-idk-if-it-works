-- Roblox GUI Script

local player = game.Players.LocalPlayer
local playerGui = player.PlayerGui
local screenGui = Instance.new("ScreenGui")
local mainFrame = Instance.new("Frame")
local textBox = Instance.new("TextBox")
local attachButton = Instance.new("TextButton")
local deleteButton = Instance.new("TextButton")
local executeButton = Instance.new("TextButton")
local sideBarButton = Instance.new("TextButton")
local sidePanel = Instance.new("Frame")
local injectButton = Instance.new("TextButton")
local w33pButton = Instance.new("TextButton")
local comingSoonButton1 = Instance.new("TextButton")
local comingSoonButton2 = Instance.new("TextButton")
local statusLabel = Instance.new("TextLabel")

-- Setup ScreenGui
screenGui.Name = "MainGUI"
screenGui.Parent = playerGui

-- Setup the main frame
mainFrame.Size = UDim2.new(0, 600, 0, 400)
mainFrame.Position = UDim2.new(0.25, 0, 0.25, 0)
mainFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 139) -- Dark blue
mainFrame.Parent = screenGui
mainFrame.Active = true
mainFrame.Draggable = true

-- Setup TextBox
textBox.Size = UDim2.new(0, 450, 0, 320)
textBox.Position = UDim2.new(0, 0, 0, 0)
textBox.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
textBox.TextColor3 = Color3.fromRGB(255, 255, 255)
textBox.TextSize = 20
textBox.PlaceholderText = "Enter script here..."
textBox.TextWrapped = true
textBox.ClearTextOnFocus = false
textBox.Parent = mainFrame

-- Setup Attach Button
attachButton.Size = UDim2.new(0, 200, 0, 40)
attachButton.Position = UDim2.new(0, 0, 0, 330)
attachButton.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
attachButton.Text = "Attach"
attachButton.TextColor3 = Color3.fromRGB(0, 0, 0)
attachButton.TextSize = 20
attachButton.Parent = mainFrame

-- Setup Delete Button
deleteButton.Size = UDim2.new(0, 200, 0, 40)
deleteButton.Position = UDim2.new(0, 210, 0, 330)
deleteButton.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
deleteButton.Text = "Delete"
deleteButton.TextColor3 = Color3.fromRGB(255, 255, 255)
deleteButton.TextSize = 20
deleteButton.Parent = mainFrame

-- Setup Execute Button
executeButton.Size = UDim2.new(0, 200, 0, 40)
executeButton.Position = UDim2.new(0, 420, 0, 330)
executeButton.BackgroundColor3 = Color3.fromRGB(255, 165, 0)
executeButton.Text = "Execute"
executeButton.TextColor3 = Color3.fromRGB(0, 0, 0)
executeButton.TextSize = 20
executeButton.Parent = mainFrame

-- Setup Sidebar Button
sideBarButton.Size = UDim2.new(0, 40, 0, 40)
sideBarButton.Position = UDim2.new(1, -40, 0, 0)
sideBarButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
sideBarButton.Text = "☰"
sideBarButton.TextSize = 30
sideBarButton.Parent = mainFrame

-- Setup Side Panel
sidePanel.Size = UDim2.new(0, 160, 1, 0)
sidePanel.Position = UDim2.new(1, 0, 0, 0)
sidePanel.BackgroundColor3 = Color3.fromRGB(0, 0, 139)
sidePanel.Visible = false
sidePanel.Parent = mainFrame

-- Setup the status label
statusLabel.Size = UDim2.new(0, 200, 0, 40)
statusLabel.Position = UDim2.new(0.5, -100, 0.5, -100)
statusLabel.Text = ""
statusLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
statusLabel.TextSize = 20
statusLabel.Parent = mainFrame

-- Setup buttons for the side panel
injectButton.Size = UDim2.new(0, 150, 0, 40)
injectButton.Position = UDim2.new(0, 5, 0, 5)
injectButton.Text = "Inject Console"
injectButton.TextColor3 = Color3.fromRGB(255, 255, 255)
injectButton.TextSize = 20
injectButton.Parent = sidePanel

w33pButton.Size = UDim2.new(0, 150, 0, 40)
w33pButton.Position = UDim2.new(0, 5, 0, 50)
w33pButton.Text = "W33P GUI"
w33pButton.TextColor3 = Color3.fromRGB(255, 255, 255)
w33pButton.TextSize = 20
w33pButton.Parent = sidePanel

comingSoonButton1.Size = UDim2.new(0, 150, 0, 40)
comingSoonButton1.Position = UDim2.new(0, 5, 0, 95)
comingSoonButton1.Text = "Coming Soon"
comingSoonButton1.TextColor3 = Color3.fromRGB(255, 255, 255)
comingSoonButton1.TextSize = 20
comingSoonButton1.Parent = sidePanel

comingSoonButton2.Size = UDim2.new(0, 150, 0, 40)
comingSoonButton2.Position = UDim2.new(0, 5, 0, 140)
comingSoonButton2.Text = "Coming Soon"
comingSoonButton2.TextColor3 = Color3.fromRGB(255, 255, 255)
comingSoonButton2.TextSize = 20
comingSoonButton2.Parent = sidePanel

-- Function to handle attaching
local function attachScript()
    statusLabel.Text = "Attaching..."
    wait(3)
    statusLabel.Text = "Attached"
    wait(3)
    statusLabel.Text = ""
end

-- Function to delete text in the text box
local function deleteText()
    textBox.Text = ""
end

-- Function to execute text in the text box
local function executeText()
    local success, errorMessage = pcall(function()
        loadstring(textBox.Text)()
    end)
    if not success then
        statusLabel.Text = "Error: " .. errorMessage
        wait(3)
        statusLabel.Text = ""
    end
end

-- Function to show/hide the side panel
local function toggleSidePanel()
    sidePanel.Visible = not sidePanel.Visible
end

-- Button Connections
attachButton.MouseButton1Click:Connect(attachScript)
deleteButton.MouseButton1Click:Connect(deleteText)
executeButton.MouseButton1Click:Connect(executeText)
sideBarButton.MouseButton1Click:Connect(toggleSidePanel)

-- Function to handle the Inject Console button
injectButton.MouseButton1Click:Connect(function()
    -- Insert script for Inject Console Access here
end)

-- Function to handle the W33P GUI button
w33pButton.MouseButton1Click:Connect(function()
    -- Insert script for W33P GUI here
end)
