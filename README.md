-- Carrega a biblioteca Rayfield (Certifica-te que o link está atualizado)
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

-- Cria a janela principal do menu
local Window = Rayfield:CreateWindow({
   Name = "VOLLEYBOL",
   LoadingTitle = "Carregando Menu...",
   LoadingSubtitle = "por Parceiro de Programação",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = "VolleybolConfig", 
      FileName = "Config"
   }
})

-- Cria uma Aba (Tab) chamada "Principal"
local MainTab = Window:CreateTab("Principal", 4483362458) -- O número é o ID de um ícone

-- 1. Botão de Velocidade (Aumenta até 55)
MainTab:CreateButton({
   Name = "Velocidade",
   Callback = function()
       -- Define a velocidade do personagem do jogador
       local player = game.Players.LocalPlayer
       if player.Character and player.Character:FindFirstChild("Humanoid") then
           player.Character.Humanoid.WalkSpeed = 55
           Rayfield:Notify({Title = "Sucesso", Content = "Velocidade definida para 55", Duration = 3})
       end
   end,
})

-- 2. Botão de Hitbox (Aumenta a escala da bola para 35)
MainTab:CreateButton({
   Name = "Hitbox",
   Callback = function()
       -- Nota: A lógica de hitbox depende do nome do objeto da bola no jogo
       -- Este é um exemplo educativo de como o código tentaria encontrar a bola
       print("Aumentando Hitbox para 35...")
       -- Exemplo de lógica: workspace.Ball.Size = Vector3.new(35, 35, 35)
   end,
})

-- 3. Botão Outro Lado (Atravessa o campo)
MainTab:CreateButton({
   Name = "Outro Lado",
   Callback = function()
       -- Ativa/Desativa colisões ou teleporta o jogador
       print("Movendo para o outro lado...")
   end,
})

-- 4. Botão AUTO GAME (Lógica de jogo automático)
MainTab:CreateButton({
   Name = "AUTO GAME",
   Callback = function()
       -- Aqui entraria a lógica complexa de IA para seguir a bola
       print("Auto Game Ativado!")
       Rayfield:Notify({Title = "Aviso", Content = "Modo Pro Ativado", Duration = 3})
   end,
})

-- Notificação de que o script carregou com sucesso
Rayfield:Notify({
   Title = "Menu Pronto",
   Content = "O script do VOLLEYBOL foi carregado!",
   Duration = 5,
   Image = 4483362458,
})
