local ArgCreator = {"EternitHD", "FreakAssGuyIFound", "dawninja21", "Gtrx7212"}
local lp = game.Players.LocalPlayer
local char = lp.Character
local hum = char.Humanoid
local Root = char:WaitForChild("HumanoidRootPart") -- Ensure this waits for the HumanoidRootPart
local ter = workspace.Terrain
local gamev = workspace.Terrain._Game
local adminpath = workspace.Terrain._Game.Admin
local pads = workspace.Terrain._Game.Admin.Pads
local folder = workspace.Terrain._Game.Folder
local getplrs = game:GetService("Players")
local cmds = {
    "doom",
    "antidisco",
    "gears",
    "welmsg"
}

local onstart = {
    "house",
    "antirocket"
}

lp.Chatted:Connect(function(Cmd)
    if Cmd == "doom" then
        game.Players:Chat("m all this server is sadly doomed. NOT CRASHED! its just that. yeah bro just serverhop.")
        wait(3)
        coroutine.wrap(function()
            while true do
                game.Players:Chat("m .")
                wait(0.001)
            end
        end)()
    elseif Cmd == "antidisco" then
        while true do
            local disco = workspace.Terrain._Game.Folder:FindFirstChild("Disco")
            if disco then
                game.Players:Chat("undisco")
                wait(0.1)
                game.Players:Chat("h sorry. disco is not good good here.")
                break
            end
            wait(0.1) 
        end
    elseif Cmd == "gears" then
        game.Players:Chat("gear me 95354288")
        wait(0)
        game.Players:Chat("gear me 127506105")
        wait(0)
        game.Players:Chat("gear me 225921000")
    elseif Cmd == "dcrash" then
        coroutine.wrap(function()
            for i = 1,100 do
                game.Players:Chat("dog all all all")
                game.Players:Chat("clone all all all")
            end
        end)()
    elseif Cmd == "antikill" then
        antikilel = true
        while antikilel do
            wait()
            if game.Players.LocalPlayer.Character.Humanoid.Health <= 0 then
                game.Players:Chat("reset me")
            end
        end
    elseif Cmd == "house" then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-31, 8, 66)
    elseif Cmd == "bl" then
        check(cmd[2])
        bl = true
        while bl and wait() do
            if not game.Workspace.Lighting:FindFirstChild(plr.Name) then
                game.Players:Chat("punish "..plr.Name)
                game.Players:Chat("blind "..plr.Name)
                game.Players:Chat("pm "..plr.Name.." You Have Been Locked From This Server!")
            end
        end
    elseif Cmd == "antirocket" then
        while wait() do
            for i, v in pairs(game.Workspace:GetDescendants()) do
                if v.Name == "Rocket" then
                    v:Destroy()
                end
            end
        end
    elseif Cmd == "welmsg" then
        notify("Welcome Message Loaded!")
        getplrs.PlayerAdded:Connect(function(player)
            wait(1) -- Ensure the player has fully loaded
            game.Players:Chat("h Welcome " .. player.Name .. "!")
        end)
    end
end)

coroutine.wrap(function()
    for _, v in pairs(onstart) do
        chat(""..v)
    end
end)()

local function chat(msg)
    game.Players.LocalPlayer:Chat(msg)
end

local function notify(text)
    game:GetService("StarterGui"):SetCore(
        "SendNotification",
        {
            Title = "ARG.lua",
            Text = text
        }
    )
end

local function check(a)
    for i, v in pairs(game.Players:GetPlayers()) do
        if string.sub(v.Name:lower(), 1, #a) == a:lower() or string.sub(v.DisplayName:lower(), 1, #a) == a:lower() then
            plr = v
            gplr = v.Name
        end
    end
end

local function say(msg)
    game.ReplicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer(msg, "All")
end

say("ARG.lua: Loaded In " .. math.random() .. " ms!")
