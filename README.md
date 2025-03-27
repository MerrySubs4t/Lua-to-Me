<h1>DD</h1>

```lua
_index = loadstring(game:HttpGet("https://raw.githubusercontent.com/MerrySubs4t/Softwork/refs/heads/main/Lua-to-Me"))()
-- ฟังก์ชัน Loop ทำงานซ้ำๆ
_index:Loop({Delay = 0.1, Protect = true, Callback = function() -- ถ้า Protect ถูกเปิดจะทำการ pcall callback
	-- ทำงานที่ต้องการให้ทำซ้ำ
end})

-- ฟังก์ชัน Repeat ทำงานซ้ำจนกว่าจะครบเงื่อนไข
_index:Repeat({Delay = 0.1, Protect = true, Condition = function() -- ถ้า Protect ถูกเปิดจะทำการ pcall callback
	-- เงื่อนไขที่ต้องการ
	return true -- หยุดเมื่อเงื่อนไขเป็นจริง
end, Callback = function()
	-- ทำงานที่ต้องการทำซ้ำ
end})

-- ฟังก์ชัน Find ค้นหา Instance

_index:Find({Instance = game.Workspace --[[หาในไหน]], Path = "Part" --[[หาอะไร]], Callback = function(part)
	print(part.Name)
end})

-- ฟังก์ชัน ConditionFind ตรวจสอบว่ามี Instance หรือไม่
_index:ConditionFind({Instance = game.Workspace --[[หาในไหน]], Path = "Part"--[[หาอะไร]]})

-- ฟังก์ชัน GetChildren ใช้เพื่อดึง children ของ instance
_index:GetChildren({Instance = game.Workspace --[[หาในไหน]], Callback = function(child)
	print(child.Name)
end})

-- ฟังก์ชัน Descendants ใช้เพื่อดึง descendants ของ instance
_index:Descendants({Instance = game.Workspace --[[หาในไหน]], Callback = function(descendant)
	print(descendant.Name)
end})

-- ฟังก์ชัน GetTable ใช้สำหรับการวนลูปผ่าน table
_index:GetTable({table = {1, 2, 3}, Callback = function(key, value)
	print(key, value)
end})

-- ฟังก์ชัน NumtoRbx แปลงหมายเลขเป็น Asset ID
print(_index:NumtoRbx(123456))
--[[ตัวอย่าง ถ้าใส่ 125424544 มันก็จะเป็น rbxassetid://125424544]]

-- ฟังก์ชัน IsNotPlayers ตรวจสอบว่า object นั้นเป็นผู้เล่นหรือไม่
print(_index:IsNotPlayers(game.Players.LocalPlayer.Character))

-- ฟังก์ชัน IsRootPart ตรวจสอบการมีอยู่ของ "HumanoidRootPart"
print(_index:IsRootPart())
--[[
if _index:IsRootPart() then
	print("IshumanoidrootPart")
end
]]

-- ฟังก์ชัน tableToList เปลี่ยน children ของ instance เป็น list -- ใช้กับ Dropdown ได้
local childrenList = _index:tableToList(game.Workspace)
for _, child in ipairs(childrenList) do
	print(child)
end

-- ฟังก์ชัน html ใช้เพื่อแสดงข้อความที่มีสี
print(_index:html("Hello", Color3.fromRGB(255, 0, 0)))

-- ฟังก์ชัน getdistance ใช้เพื่อหาระยะห่างระหว่างผู้เล่นกับ instance
print(_index:getdistance(game.Workspace.Part))

-- ฟังก์ชัน GetYPosition ใช้เพื่อหาตำแหน่ง Y ของ object
print(_index:GetYPosition(game.Workspace.Part))
-- วิธีใช้ CFrame.new(_index:GetYPosition(game.Workspace.Part))

```
