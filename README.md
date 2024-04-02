_G.ImageUIButton = "rbxassetid://12862171447"


local Update = loadstring(game:HttpGet("https://raw.githubusercontent.com/NaJaxHub/ser/main/UIfreeNaJabat"))()

local Library = Update:Window("MrMaxNaJa Community","",Enum.KeyCode.RightControl);--"MrMaxNaJa Hub | Map Blox Fruits - Free Script Version 0.1.15.1 By MrMaxNaJa"
Main = Library:Tab("Main")

Main:Line()

Main:Label("Welcome MrMaxNaJa Community")

local Time = Main:Label("Executor Time");spawn(function() getgenv().Time = true;while true do wait(.1) UpdateTime() end end);function UpdateTime() local date = os.date("*t");local hour = (date.hour) % 24;local ampm = hour < 12 and "AM" or "PM";local timezone = string.format("%02i:%02i:%02i %s", ((hour -1) % 12) + 1, date.min, date.sec, ampm);local datetime = string.format("%02d/%02d/%04d", date.day, date.month, date.year);local LocalizationService = game:GetService("LocalizationService");local Players = game:GetService("Players");local player = Players.LocalPlayer;local name = player.Name;local result, code = pcall(function()   return LocalizationService:GetCountryRegionForPlayerAsync(player)  end);Time:Set(" : " .. timezone);Time:Set("Executor Time: " .. datetime .. " [ " .. code .. " ]");spawn(function() if getgenv().Time then pcall(function()  while wait() do  Time()  end end) end end) end

Main:Seperator("Main")

Main:Toggle("AutoFarm Lv.",_G.AutoFarm,function(value)
    _G.AutoFarm = value
    StopTween(_G.AutoFarm)
end)

spawn(function()
    while wait() do
        if _G.AutoFarm then
            pcall(function()
                local BanditIsland = CFrame.new(-973.992798, 34.5999947, -530.916992, 0.0224915557, -6.85506363e-09, 0.999747038, -1.5485039e-08, 1, 7.20516891e-09, -0.999747038, -1.56431774e-08, 0.0224915557)
                if (BanditIsland.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 300 then
                for i,v in pairs(game:GetService("Workspace").Lives:GetChildren()) do
                    if v.ClassName == "Model" then
                        if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                                repeat wait()
                                    --PosMon = v.HumanoidRootPart.CFrame
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = (v.HumanoidRootPart.CFrame * CFrame.new(0,2,2))
                                    v.HumanoidRootPart.CanCollide = false
                                    v.Humanoid.WalkSpeed = 0
                                    v.HumanoidRootPart.Size = Vector3.new(80,80,80)
                                    v.HumanoidRootPart.Transparency = 0.7
                                    game:GetService("VirtualUser"):CaptureController()
                                    game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
                                until not _G.AutoFarm or not v.Parent or v.Humanoid.Health <= 0
                        end
                    end
                end
                end
            end)
        end
    end
end)
