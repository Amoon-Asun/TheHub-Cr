local checker = Workspace:FindFirstChild("Queue")
local plyr = game.Players.LocalPlayer;
local character= plyr.Character
local TeleportService = game:GetService("TeleportService")
local units = {
    unit1 = "Naruto Sage Of The Six Paths",
    unit2 = "Enraged Todoroki",
    unit3 = "Usopp TS"
}
repeat
    wait()
until game:IsLoaded() and game.Players.LocalPlayer ~= nil and game.Players.LocalPlayer.Name ~= nil
if checker ~= nil then
    function TeleportTo(place)
         character.HumanoidRootPart.CFrame = place
     end
--the names of the places--
local CandyFarm = CFrame.new(-779.78405761719, 13661.497070312, -8380.818359375)
--only copy the name--
TeleportTo(CandyFarm)--here put the name of the place--
wait(60)
local Servers = game.HttpService:JSONDecode(game:HttpGet("https://games.roblox.com/v1/games/4996049426/servers/Public?sortOrder=Asc&limit=100"))
for i,v in pairs(Servers.data) do
    wait(2)
  if v.playing ~= v.maxPlayers then
      game:GetService('TeleportService'):TeleportToPlaceInstance(game.PlaceId, v.id)
  end
end
        else
            while true do
                for i,v in pairs(units)do
wait(5)
                  local A_1 = "SpawnAllyODD"
                  local A_2 = units[i]
                  local Event = game:GetService("ReplicatedStorage").Remotes.Server
                  Event:InvokeServer(A_1, A_2)
                end
                break
            end
end
