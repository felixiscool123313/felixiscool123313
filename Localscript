-------------------------------it's basically the same thing but I'm not looking for easy ways---------------------
local PostEffectsEngine = require(game.ReplicatedStorage.PostEffectsEngine)
local logicavisualmodule = require(game.ReplicatedStorage.logicavisualmodule)

-------------------------------------------------------------------------------------------------------------------
local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local player = Players.LocalPlayer
local char = player.Character
local Hm = char:WaitForChild("Humanoid")
local rp = char:WaitForChild("HumanoidRootPart")
local rl = char:WaitForChild("Right Leg")
local ra = char:WaitForChild("Right Arm")
local Mouse = player:GetMouse()
local Debounce = false
local Attack1 = false
local num = 1
local waitForCheckstop = 5
local leght1 = 0.3
local leght2 = 0.3
local leght3 = 0.48
local leght4 = 1
local helper =1
local coldown = 4
local Katana 
local hitbox
local rl1 
local numhelper = nil
local damage =math.random(10,20)
local func = script:WaitForChild("Remote")
local hitDeb =true
local Kt = script:WaitForChild("Remote")
Katana = Kt:InvokeServer(player,nil,{["TypeSelect"]="Start"})
local hitboxkt = Katana:WaitForChild("HitBox")
spawn(function()
	game.ReplicatedStorage.Remotes:WaitForChild("MainSector"):InvokeServer(player,nil)
end)
local function slashremote(num,leght)
	spawn(function()
		wait(leght)
		func:InvokeServer(player,nil,{["TypeSelect"]="Slash",["num"]=num,["Katana"]=Katana})
	end)
end
UserInputService.InputBegan:Connect(function(input,chat)
	if not chat  then	
		if input.UserInputType  == Enum.UserInputType.MouseButton1 and Debounce == false and Hm.Health >0 and logicavisualmodule.GetState(char) == nil then
	Debounce = true	
				func:InvokeServer(player,nil,{["TypeSelect"]="ReturnChar",["SetStop"]=true})
				if num == 1  then
					logicavisualmodule.SetAnimation(Hm,script.ModAnims.Attack1,0)
					helper = 1
				slashremote(helper,leght1/2)
				spawn(function()
					spawn(function()
						wait(leght1)
						hitDeb =true
					end)
					for i, v in pairs(workspace:GetChildren()) do
						spawn(function()
							if v:FindFirstChild("HumanoidRootPart") and v ~= char and (rp.Position + rp.CFrame.lookVector * 4 - v.HumanoidRootPart.Position).magnitude <= 5 then
								if v:FindFirstChild("Humanoid")  and hitDeb == true and v:FindFirstChild("Humanoid").Health >0 then
							
								local enrp = v:WaitForChild("HumanoidRootPart")
								hitDeb = false

								if logicavisualmodule.GetState(v) == nil or logicavisualmodule.GetState(v) == "Hit"  then
									func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Normal",["Legth"]=leght1*3})
								elseif logicavisualmodule.GetState(v) == "Attacking" then
									func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Attacking",["Legth"]=leght1*3})


								elseif logicavisualmodule.GetState(v) == "Blocking" then
									func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Blocking",["Legth"]=leght1*3})
								elseif logicavisualmodule.GetState(v) == "CutScene" then

								end						
							end
							end
							end)
						end
				
				end)
			
					num = 2
					wait(leght1)
				elseif num == 2  then
					logicavisualmodule.SetAnimation(Hm,script.ModAnims.Attack2,0)
					helper = 2
				slashremote(helper,leght2/2)
				spawn(function()
					spawn(function()
						wait(leght2)
						hitDeb =true
					end)
					for i, v in pairs(workspace:GetChildren()) do
						spawn(function()
							if v:FindFirstChild("HumanoidRootPart") and v ~= char and (rp.Position + rp.CFrame.lookVector * 4 - v.HumanoidRootPart.Position).magnitude <= 5 then
								if v:FindFirstChild("Humanoid")  and hitDeb == true and v:FindFirstChild("Humanoid").Health >0 then
								
									local enrp = v:WaitForChild("HumanoidRootPart")
									hitDeb = false

									if logicavisualmodule.GetState(v) == nil or logicavisualmodule.GetState(v) == "Hit"  then
										func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Normal",["Legth"]=leght2*3})
									elseif logicavisualmodule.GetState(v) == "Attacking" then
										func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Attacking",["Legth"]=leght2*3})


									elseif logicavisualmodule.GetState(v) == "Blocking" then
										
										func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Blocking",["Legth"]=leght2*3})
									elseif logicavisualmodule.GetState(v) == "CutScene" then

									end						
								end
							end
						end)
					end

				end)
					num=3
					wait(leght2)
				elseif num == 3  then
					local count = true
					logicavisualmodule.SetAnimation(Hm,script.ModAnims.Attack3,0)
					helper = 3
				slashremote(helper,0)
				spawn(function()
					for i=1,2 do
						spawn(function()
						for i, v in pairs(workspace:GetChildren()) do
							spawn(function()

								if v:FindFirstChild("HumanoidRootPart") and v ~= char and (rp.Position - v.HumanoidRootPart.Position).magnitude <= 10 then
									if v:FindFirstChild("Humanoid")  and hitDeb == true and v:FindFirstChild("Humanoid").Health >0 then
											hitDeb =false
											local enrp = v:WaitForChild("HumanoidRootPart")
									
										if logicavisualmodule.GetState(v) == nil or logicavisualmodule.GetState(v) == "Hit"  then
											func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Normal",["Legth"]=leght3*2})
										elseif logicavisualmodule.GetState(v) == "Attacking" then
											func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Attacking",["Legth"]=leght3*2})
										elseif logicavisualmodule.GetState(v) == "Blocking" then
												func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Blocking",["Legth"]=leght3*2})
										elseif logicavisualmodule.GetState(v) == "CutScene" then

										end						
									end
								end
							end)
							end
						end)
						wait(0.35)
						hitDeb = true
					end
				

				end)
		
				spawn(function()
					wait(leght3*2)
					hitDeb =true
				end)
					num = 4
					wait(leght3)
				elseif num == 4  then
				local randomattack = math.random(1,2)
				if randomattack == 1 then
				logicavisualmodule.SetAnimation(Hm,script.ModAnims.Attack4,0)
				helper = 4
					slashremote(helper,0)
					wait(0.2)
					spawn(function()
						spawn(function()
							wait(leght4)
							hitDeb =true
						end)
						for i, v in pairs(workspace:GetChildren()) do
							spawn(function()
								if v:FindFirstChild("HumanoidRootPart") and v ~= char and (rp.Position + rp.CFrame.lookVector * 4 - v.HumanoidRootPart.Position).magnitude <= 5 then
									if v:FindFirstChild("Humanoid")  and hitDeb == true and v:FindFirstChild("Humanoid").Health >0 then
										local enrp = v:WaitForChild("HumanoidRootPart")
										hitDeb = false
										if logicavisualmodule.GetState(v) == nil or logicavisualmodule.GetState(v) == "Hit"  then
											func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Normal",["Legth"]=0.6})
										elseif logicavisualmodule.GetState(v) == "Attacking" then
											func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Attacking",["Legth"]=0.6})


										elseif logicavisualmodule.GetState(v) == "Blocking" then
											func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Blocking",["Legth"]=0.6})
										elseif logicavisualmodule.GetState(v) == "CutScene" then

										end		
									end
									
								end
							end)
						end
						end)
		
					
			
				else
					logicavisualmodule.SetAnimation(Hm,script.ModAnims.Attackrand4,0)
					helper = 4
					slashremote(helper,0)
					wait(0.2)
					spawn(function()
						spawn(function()
							wait(leght4)
							hitDeb =true
						end)
						for i, v in pairs(workspace:GetChildren()) do
							spawn(function()
								if v:FindFirstChild("HumanoidRootPart") and v ~= char and (rp.Position + rp.CFrame.lookVector * 4 - v.HumanoidRootPart.Position).magnitude <= 5 then
									if v:FindFirstChild("Humanoid")  and hitDeb == true and v:FindFirstChild("Humanoid").Health >0 then
										local enrp = v:WaitForChild("HumanoidRootPart")
										hitDeb = false
										if logicavisualmodule.GetState(v) == nil or logicavisualmodule.GetState(v) == "Hit"  then
											func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Normal",["Legth"]=0.6})
										elseif logicavisualmodule.GetState(v) == "Attacking" then
											func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Attacking",["Legth"]=0.6})
										elseif logicavisualmodule.GetState(v) == "Blocking" then
											func:InvokeServer(player,nil,{["num"]=helper,["Hit"]=v,["Type"]="Blocking",["Legth"]=0.6})
										elseif logicavisualmodule.GetState(v) == "CutScene" then

										end		
									end

								end
							end)
						end
					end)

			
				end
				wait(leght4)
				logicavisualmodule.StopPlayer(Hm,false)
				num = 1
				wait(coldown)
			end	
				Debounce = false
				func:InvokeServer(player,nil,{["TypeSelect"]="ReturnChar",["SetStop"]=false})
				
				
			Debounce = false
			
		end
			
	end
end)
spawn(function()
	while wait() do 
	if Debounce == false and num ==num and num ~= 1 then
		wait(waitForCheckstop)
		if Debounce == false and num ==num then
			num=1
			end
		end
		end
end)
