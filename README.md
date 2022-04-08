local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Kram Life", "Sentinel")
local Tab = Window:NewTab("Main")
local Section = Tab:NewSection("Auto Farm")

function ChangeName()
    for i,v in pairs(game:GetService("Workspace").Shop.place.blinkep:GetChildren()) do -- GetDescendants
a = 3
if a == i then
    v.Name = "GG"
    end
end
end

function FindLocation()
for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack.Location.Handle.SurfaceGui:GetChildren()) do
    if v.Text == "TECHNIC SHOP" then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Inbox.technicshop.Part.CFrame * CFrame.new(0,-4,-5)
        wait(.5)
        fireclickdetector(game:GetService("Workspace").Inbox.technicshop.ClickDetector)
    elseif v.Text == "MINE" then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Inbox.mine.Part.CFrame * CFrame.new(0,-4,-5)
        wait(.5)
        fireclickdetector(game:GetService("Workspace").Inbox.mine.ClickDetector)
    elseif v.Text == "METAL SHOP" then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Inbox.metalshop.Part.CFrame * CFrame.new(0,-4,-5)
        wait(.5)
        fireclickdetector(game:GetService("Workspace").Inbox.metalshop.ClickDetector)
    elseif v.Text == "SAW MILL" then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Inbox.sawmill.Part.CFrame * CFrame.new(0,-4,-5)
        wait(.5)
        fireclickdetector(game:GetService("Workspace").Inbox.sawmill.ClickDetector)
    elseif v.Text == "HUNTING STORE" then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Inbox.huntingstore.Part.CFrame * CFrame.new(0,-4,-5)
        wait(.5)
        fireclickdetector(game:GetService("Workspace").Inbox.huntingstore.ClickDetector)
        wait(.5)
    elseif v.Text == "RICE MILL" then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Inbox.ricemaill.Part.CFrame * CFrame.new(0,-4,-5)
        wait(.5)
        fireclickdetector(game:GetService("Workspace").Inbox.ricemaill.ClickDetector)
    end
    end
end

Section:NewToggle("Auto Farm (Delivery)", "ToggleInfo", function(state)
    if state then
        a1 = true
    else
        a1 = false
    end
end)

spawn(function()
while wait() do
if a1 == true then
pcall(function()
ChangeName()
wait(.25)
fireclickdetector(game:GetService("Workspace").Shop.place.blinkep.GG.click.ClickDetector)
wait(.25)
FindLocation()
end)
end
end
end)


local Tab = Window:NewTab("Player")
local Section = Tab:NewSection("Local Player")
Section:NewSlider("WalkSpeed", "Changes Your Speedwalk.", 500, 16, function(s)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)
Section:NewSlider("JumpPower", "Changes Your Jumppower.", 500, 16, function(s)
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = s
end)
local Section = Tab:NewSection("Select Player!")
Plr = {}
for i,v in pairs(game:GetService("Players"):GetChildren()) do
    table.insert(Plr,v.Name) 
end
local drop = Section:NewDropdown("Select Player!", "Click To Select", Plr, function(t)
   PlayerTP = t
end)
Section:NewButton("Click To TP", "", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[PlayerTP].Character.HumanoidRootPart.CFrame
end)
Section:NewToggle("Auto Tp", "", function(t)
_G.TPPlayer = t
while _G.TPPlayer do wait()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[PlayerTP].Character.HumanoidRootPart.CFrame
end
end)

Section:NewButton("Refresh Dropdown","Refresh Dropdown", function()
  drop:Refresh(Plr)
end)
local Tab = Window:NewTab("Teleport")
local Section = Tab:NewSection("Teleport ( Working Zone )")
Section:NewButton("Blink Express", "Cargo Station", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-12.1769915, 41.7933578, -196.532257, 0.275619656, 7.48005249e-08, 0.961266756, 5.95961183e-08, 1, -9.49022549e-08, -0.961266756, 8.34446965e-08, 0.275619656)
    end)
    Section:NewButton("Mine", "Medium sized tunnel city", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-382.45575, 27.574028, 217.89386, 0.752463698, -5.50460904e-08, 0.658633709, 5.13981782e-08, 1, 2.48557352e-08, -0.658633709, 1.51495332e-08, 0.752463698)
    end)
    Section:NewButton("Technic Shop", "Mechanic equipment", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-8.04250908, 25.9047146, 688.99176, 0.82656765, 1.35540104e-08, 0.562837362, -7.62834684e-09, 1, -1.28787923e-08, -0.562837362, 6.3516743e-09, 0.82656765)
    end)
    Section:NewButton("Metal Shop", "Steel Mill", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-79.518631, 25.9248619, 562.370667, 0.979165077, 3.83550969e-09, -0.203065783, -3.47202178e-09, 1, 2.14623741e-09, 0.203065783, -1.39647205e-09, 0.979165077)
    end)
    Section:NewButton("Hunting Shop", "Forest Shop", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-912.07428, 32.9999886, 610.717896, -0.886540592, 3.8248686e-08, 0.462650806, 5.12051423e-09, 1, -7.28608711e-08, -0.462650806, -6.22251122e-08, -0.886540592)
    end)
    Section:NewButton("Rice Mill", "Agricultural Farm", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-342.838074, 68.0427246, -682.778564, 0.947107136, 9.87832252e-08, 0.320917547, -1.04776191e-07, 1, 1.40551593e-09, -0.320917547, -3.49556935e-08, 0.947107136)
    end)
    Section:NewButton("Saw Mill", "Wood Store", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-39.5336571, 31.9654694, -705.994934, 0.484737992, -1.09760194e-07, 0.874659419, 2.81042354e-08, 1, 1.0991365e-07, -0.874659419, -2.8697686e-08, 0.484737992)
    end)
    Section:NewLabel("Teleport (Station)")
    Section:NewButton("Lottery Office", "Lottery Station", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-97.346962, 25.934864, 453.6586, -0.983258188, -4.29891784e-08, 0.18221797, -2.77564389e-08, 1, 8.61464571e-08, -0.18221797, 7.96464832e-08, -0.983258188)
    end)
    Section:NewButton("Convenience Store", "Grocery Store", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(39.9115601, 30.0000076, 218.195999, -0.989704311, 2.31950441e-08, 0.143127248, 2.13991669e-08, 1, -1.4086746e-08, -0.143127248, -1.08789093e-08, -0.989704311)
    end)
    Section:NewButton("Lala Hotel", "Little Hotel", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-48.0481796, 28.9999943, 177.194946, 0.204907164, -1.80091462e-08, 0.978781402, -1.05973355e-08, 1, 2.06181046e-08, -0.978781402, -1.45972718e-08, 0.204907164)
    end)
    Section:NewButton("Police Station", "Reserved for notification :/", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(61.5674248, 25.1274147, 557.928223, 0.273735642, -1.42904808e-08, 0.961804986, 1.0862804e-08, 1, 1.17663603e-08, -0.961804986, 7.22702698e-09, 0.273735642)
    end)
    Section:NewButton("Book Store", "Read to increase knowledge skills.", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-133.553345, 27.0848007, 615.355957, 0.480833292, -3.88225061e-08, 0.876812041, 1.18248176e-08, 1, 3.77922973e-08, -0.876812041, -7.80365284e-09, 0.480833292)
    end)
    Section:NewButton("Beach", "Relaxation :>", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(161.573853, -5.15731525, 837.083984, -0.721299112, -8.09900484e-08, -0.692623675, -8.44080645e-08, 1, -2.90295947e-08, 0.692623675, 3.75240035e-08, -0.721299112)
    end)
    Section:NewButton("Clinics", "Pharmacy", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(13.3569021, 25.9046268, 613.954468, -0.988415956, -1.38793839e-08, 0.151769236, 3.50997809e-09, 1, 1.14309742e-07, -0.151769236, 1.13518283e-07, -0.988415956)
    end)
    Section:NewButton("Kramion Hotel", "For Relaxation", function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(271.9177551269531, -5.8651323318481445, 427.6654968261719)
    end)
    Section:NewButton("Eazy Shop 1", "For buy Food :> ", function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(37.00658416748047, 30.00000762939453, 218.1997528076172)
    end)
    Section:NewButton("Eazy Shop 2", "For buy Food :> ", function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(207.39645385742188, -6.181451797485352, 649.3421630859375)
    end)
    Section:NewButton("Food Shop", "For buy Food :> ", function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-297.998291015625, 68.80850219726562, -559.6185913085938)
    end)
