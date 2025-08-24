loadstring(game:HttpGet("https://gist.githubusercontent.com/UCT-hub/bbf93622c87d48ae4d35a77e6e83d9be/raw/b14a749a24febc9dc04e2249fce8124ec28af5f7/DISCORD", true))()
local Players = game:GetService("Players")
local player = Players.LocalPlayer or Players.PlayerAdded:Wait()

-- Track Loaded Scripts
local scriptExecuted = false
local loadedScripts = {}
local function loadScript(url)
    if loadedScripts[url] then return end
    loadedScripts[url] = true
    local success, result = pcall(function()
        return loadstring(game:HttpGet(url, true))()
    end)
    if not success then
        warn("[Failed to load]:", url, result)
    end
end

-- Check for special place IDs first
local pid = game.PlaceId
local specialPlaceIds = {
    [109983668079237] = true,
    [128762245270197] = true,
    [96342491571673] = true
}

if specialPlaceIds[pid] then
    local success1, result1 = pcall(function()
        loadScript("https://gist.githubusercontent.com/UCT-hub/be66e87d593be7b17d271a3e09234564/raw/317bb6a246c5d45378a005dc23817a40a46b30e5/LENNONHUBBYUCT.txt")
    end)
    local success2, result2 = pcall(function()
        loadScript("https://gist.githubusercontent.com/UCT-hub/e2cc5514ebf4f97e8e3bf3ac08b8d862/raw/3c5d4203f927c3ea16215e2c9479eba5fe19fdbc/gistfile1.txt")
    end)

    if not success1 then
        warn("Failed to load Stel script:", result1)
    end
    if not success2 then
        warn("Failed to load Warger script:", result2)
    end
    return
end
