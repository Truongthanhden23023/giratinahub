-- Create GUI Button for toggling features in Blox Fruits
local Player = game.Players.LocalPlayer
local PlayerGui = Player:WaitForChild("PlayerGui")

-- Create a ScreenGui if it doesn't exist
local screenGui = Instance.new("ScreenGui")
screenGui.Parent = PlayerGui

-- Create the button to toggle features
local toggleButton = Instance.new("TextButton")
toggleButton.Size = UDim2.new(0, 200, 0, 50)
toggleButton.Position = UDim2.new(0, 10, 0, 10)
toggleButton.Text = "Toggle All Features"
toggleButton.BackgroundColor3 = Color3.fromRGB(0, 128, 255)
toggleButton.Parent = screenGui

-- Initialize settings for features
local AutoFarm = false
local AutoQuest = false
local AutoStat = false
local AutoSkill = false
local TeleportToBoss = false
local AutoFruit = false
local AutoInventory = false
local AutoCollectFruits = false
local AutoShop = false
local AutoUpgrade = false
local AutoBossFight = false
local AutoHeal = false
local AutoStun = false
local AutoFarmArea = workspace:WaitForChild("SomeFarmArea") -- Change to your farm area
local AutoSeaTeleport = false

-- Function to start farming
function StartFarming()
    while AutoFarm do
        local target = getClosestEnemy(AutoFarmArea)
        if target then
            attack(target)
        end
        wait(1)
    end
end

-- Function to attack the enemy
function attack(target)
    if target and target:FindFirstChild("Humanoid") then
        target.Humanoid.Health = 0
    end
end

-- Function to get the closest enemy
function getClosestEnemy(area)
    local closestEnemy = nil
    local minDist = math.huge
    for _, enemy in pairs(area:GetChildren()) do
        if enemy:IsA("Model") and enemy:FindFirstChild("HumanoidRootPart") then
            local distance = (Player.Character.HumanoidRootPart.Position - enemy.HumanoidRootPart.Position).Magnitude
            if distance < minDist then
                closestEnemy = enemy
                minDist = distance
            end
        end
    end
    return closestEnemy
end

-- Function to teleport to different seas (Sea 1, Sea 2, Sea 3)
function teleportToSea(seaNumber)
    if seaNumber == 1 then
        local sea1Location = workspace:WaitForChild("Sea1Location")  -- Vị trí của Sea 1
        if sea1Location then
            Player.Character.HumanoidRootPart.CFrame = CFrame.new(sea1Location.Position)
        end
    elseif seaNumber == 2 then
        local sea2Location = workspace:WaitForChild("Sea2Location")  -- Vị trí của Sea 2
        if sea2Location then
            Player.Character.HumanoidRootPart.CFrame = CFrame.new(sea2Location.Position)
        end
    elseif seaNumber == 3 then
        local sea3Location = workspace:WaitForChild("Sea3Location")  -- Vị trí của Sea 3
        if sea3Location then
            Player.Character.HumanoidRootPart.CFrame = CFrame.new(sea3Location.Position)
        end
    else
        print("Invalid sea number.")
    end
end

-- Example: Call the function to teleport to Sea 1, Sea 2, or Sea 3
teleportToSea(1)  -- Di chuyển đến Sea 1
teleportToSea(2)  -- Di chuyển đến Sea 2
teleportToSea(3)  -- Di chuyển đến Sea 3

-- Function for auto quest
function startAutoQuest()
    if AutoQuest then
        local questGiver = workspace:WaitForChild("QuestGiver")
        if questGiver then
            -- Example quest interaction (adjust based on quest system)
            Mouse.Button1Click:Connect(function()
                -- Handle quest interaction logic here
            end)
        end
    end
end

-- Function to auto stat allocation
function autoStatAllocation()
    if AutoStat then
        -- Add logic for auto stat allocation
        while AutoStat do
            -- Example of allocating stat points (adjust based on actual game mechanics)
            local statButton = game:GetService("ReplicatedStorage"):WaitForChild("StatButton")
            if statButton then
                statButton:Click()  -- Adjust this according to your game's UI
            end
            wait(0.5)  -- Adjust the wait time for stat allocation
        end
    end
end

-- Function to auto use skills
function autoUseSkills()
    if AutoSkill then
        -- Example of auto skill use (adjust according to your skills)
        local skills = Player.Character:FindFirstChild("Skills")
        if skills then
            for _, skill in pairs(skills:GetChildren()) do
                -- Use the skill (adjust based on how the skill system works)
                skill:Activate()  -- Placeholder, adjust as needed
            end
        end
    end
end

-- Function for Auto Fruit (using fruit abilities or eating fruits)
function autoUseFruit()
    if AutoFruit then
        local fruit = workspace:FindFirstChild("Fruit") -- Adjust based on fruit system
        if fruit then
            -- Example fruit activation (adjust to how your game handles fruit abilities)
            fruit:Activate()  -- Placeholder for fruit activation
        end
    end
end

-- Function for Auto Inventory (managing inventory, picking up items)
function autoManageInventory()
    if AutoInventory then
        local inventory = Player.Backpack -- Adjust based on inventory system
        for _, item in pairs(inventory:GetChildren()) do
            -- Example item management (pick up, equip, etc.)
            if item:IsA("Tool") then
                -- Equip or use item (adjust as needed)
                item.Parent = Player.Character
            end
        end
    end
end

-- Function to auto collect fruits on the map
function autoCollectFruits()
    if AutoCollectFruits then
        local fruits = workspace:WaitForChild("Fruits")  -- Adjust based on the location of fruits
        for _, fruit in pairs(fruits:GetChildren()) do
            -- Collect fruits (adjust based on how the fruit collection works)
            if fruit:IsA("Model") then
                fruit:Destroy()  -- Example of picking up the fruit (adjust if different action needed)
            end
        end
    end
end

-- Function to auto shop purchases
function autoShop()
    if AutoShop then
        local shop = workspace:WaitForChild("Shop")  -- Adjust to your shop location
        local item = shop:FindFirstChild("Item")  -- Adjust to the item you want to purchase
        if item then
            item:Click()  -- Example of purchasing an item
        end
    end
end

-- Function to auto upgrade skills, stats, or abilities
function autoUpgrade()
    if AutoUpgrade then
        -- Example of upgrading (adjust based on the game mechanics)
        local upgradeButton = workspace:WaitForChild("UpgradeButton")
        if upgradeButton then
            upgradeButton:Click()  -- Simulate upgrade button click
        end
    end
end

-- Function for Auto Boss Fight (teleport and fight boss)
function autoBossFight()
    if AutoBossFight then
        local boss = workspace:WaitForChild("Boss")  -- Adjust to the boss location
        if boss then
            teleportToLocation(boss)
            while boss and boss:FindFirstChild("Humanoid") and boss.Humanoid.Health > 0 do
                attack(boss)
                wait(1)
            end
        end
    end
end

-- Function for Auto Heal (automatically heal if health is low)
function autoHeal()
    if AutoHeal then
        local health = Player.Character:FindFirstChild("Humanoid").Health
        if health < 50 then  -- Adjust the threshold for healing
            -- Example healing (adjust based on the healing mechanics)
            local healItem = Player.Backpack:FindFirstChild("HealPotion")
            if healItem then
                healItem:Activate()  -- Use healing item or ability
            end
        end
    end
end

-- Function for Auto Stun (use stun ability on enemies)
function autoStun()
    if AutoStun then
        local enemy = getClosestEnemy(AutoFarmArea)
        if enemy then
            local stunAbility = Player.Character:FindFirstChild("StunAbility")
            if stunAbility then
                stunAbility:Activate()  -- Example of using stun ability
            end
        end
    end
end

-- Toggle button click event
toggleButton.MouseButton1Click:Connect(function()
    AutoFarm = not AutoFarm
    AutoQuest = not AutoQuest
    AutoStat = not AutoStat
    AutoSkill = not AutoSkill
    TeleportToBoss = not TeleportToBoss
    AutoFruit = not AutoFruit
    AutoInventory = not AutoInventory
    AutoCollectFruits = not AutoCollectFruits
    AutoShop = not AutoShop
    AutoUpgrade = not AutoUpgrade
    AutoBossFight = not AutoBossFight
    AutoHeal = not AutoHeal
    AutoStun = not AutoStun
    AutoSeaTeleport = not AutoSeaTeleport
    
    -- Start/Stop features
    if AutoFarm then
        StartFarming()
    end
    if AutoQuest then
        startAutoQuest()
    end
    if AutoStat then
        autoStatAllocation()
    end
    if AutoSkill then
        autoUseSkills()
    end
    if TeleportToBoss then
        teleportToLocation(workspace:WaitForChild("BossLocation"))  -- Example teleport to a boss location
    end
    if AutoFruit then
        autoUseFruit()
    end
    if AutoInventory then
        autoManageInventory()
    end
    if AutoCollectFruits then
        autoCollectFruits()
    end
    if AutoShop then
        autoShop()
