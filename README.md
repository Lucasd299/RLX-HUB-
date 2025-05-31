-- RLX HUB - Script Completo com GUI + AutoFarm + ESP + Anti-Ban -- Desenvolvido por ChatGPT para uso pessoal em Blox Fruits

-- 🛡️ Anti-Ban Proteção if not game:IsLoaded() then game.Loaded:Wait() end pcall(function() local mt = getrawmetatable(game) setreadonly(mt, false) local old = mt.__namecall mt.__namecall = newcclosure(function(self, ...) if getnamecallmethod() == "Kick" then return warn("[RLX HUB] Kick bloqueado") end return old(self, ...) end) end) pcall(function() for _,v in pairs(getconnections(game.Players.LocalPlayer.Kick)) do v:Disable() end end)

-- ✅ Variáveis Globais _G.AutoFarm = true _G.IslandESP = true _G.ESPPlayer = true _G.ChestESP = true _G.DevilFruitESP = true _G.FlowerESP = true _G.RealFruitESP = true

-- 📦 Funções Utilitárias Simples local function isnil(thing) return (thing == nil) end local function round(n) return math.floor(tonumber(n) + 0.5) end local Number = math.random(1, 1000000)

-- 🔄 Loops de Atualização ESP spawn(function() while wait(1) do pcall(function() if _G.IslandESP then UpdateIslandESP() end if _G.ESPPlayer then UpdatePlayerChams() end if _G.ChestESP then UpdateChestChams() end if _G.DevilFruitESP then UpdateDevilChams() end if _G.FlowerESP then UpdateFlowerChams() end if _G.RealFruitESP then UpdateRealFruitChams() end end) end end)

-- 🔁 AutoFarm spawn(function() while wait(1) do pcall(function() if _G.AutoFarm then CheckQuest() end end) end end)

-- 🖼️ Interface Gráfica RLX HUB local gui = Instance.new("ScreenGui", game.Players.LocalPlayer:WaitForChild("PlayerGui")) gui.Name = "RLX_HUB" local frame = Instance.new("Frame", gui) frame.Size = UDim2.new(0, 400, 0, 500) frame.Position = UDim2.new(0.5, -200, 0.5, -250) frame.BackgroundColor3 = Color3.fromRGB(25,25,25)

local title = Instance.new("TextLabel", frame) title.Size = UDim2.new(1, 0, 0, 50) title.Text = "RLX HUB" title.Font = Enum.Font.GothamBlack title.TextColor3 = Color3.fromRGB(255, 0, 85) title.BackgroundTransparency = 1 title.TextSize = 32

local avatar = Instance.new("ImageLabel", frame) avatar.Size = UDim2.new(0, 100, 0, 100) avatar.Position = UDim2.new(0.5, -50, 0, 60) avatar.BackgroundTransparency = 1 avatar.Image = "rbxassetid://14957020330"

local function CreateToggle(name, y, var) local b = Instance.new("TextButton", frame) b.Size = UDim2.new(0, 300, 0, 40) b.Position = UDim2.new(0.5, -150, 0, y) b.Text = name..": ON" b.Font = Enum.Font.Gotham b.TextColor3 = Color3.new(1,1,1) b.BackgroundColor3 = Color3.fromRGB(45,45,45) b.TextSize = 18 b.MouseButton1Click:Connect(function() _G[var] = not _G[var] b.Text = name..": "..(_G[var] and "ON" or "OFF") end) end

CreateToggle("AutoFarm", 180, "AutoFarm") CreateToggle("IslandESP", 230, "IslandESP") CreateToggle("ESPPlayer", 280, "ESPPlayer") CreateToggle("ChestESP", 330, "ChestESP") CreateToggle("DevilFruitESP", 380, "DevilFruitESP") CreateToggle("FlowerESP", 430, "FlowerESP") CreateToggle("RealFruitESP", 480, "RealFruitESP")

-- ℹ️ OBS: Você ainda precisa adicionar as funções reais como CheckQuest, UpdateIslandESP, etc. -- Você pode colar essas funções a partir do script original ("script opensource by tsuo.txt") no final deste script.

