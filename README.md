-- Script para mostrar o nome do jogador na cabeça com cor vermelha

game.Players.PlayerAdded:Connect(function(player)
    -- Espera até o personagem do jogador ser carregado
    player.CharacterAdded:Connect(function(character)
        -- Cria uma parte para ser o nome do jogador
        local nomeTag = Instance.new("BillboardGui")
        nomeTag.Adornee = character:WaitForChild("Head")  -- A parte onde o nome vai aparecer (na cabeça)
        nomeTag.Size = UDim2.new(0, 200, 0, 50)  -- Tamanho da tag
        nomeTag.StudsOffset = Vector3.new(0, 3, 0)  -- Offset para a posição da tag (um pouco acima da cabeça)
        nomeTag.Parent = character.Head  -- A tag é filha da cabeça do jogador

        -- Cria o texto com o nome do jogador
        local texto = Instance.new("TextLabel")
        texto.Text = player.Name  -- O nome do jogador
        texto.Size = UDim2.new(1, 0, 1, 0)  -- Preenche o tamanho da tag
        texto.TextColor3 = Color3.fromRGB(255, 0, 0)  -- Cor vermelha
        texto.TextStrokeTransparency = 0.8  -- Borda para destacar o texto
        texto.TextSize = 18  -- Tamanho do texto
        texto.BackgroundTransparency = 1  -- Torna o fundo transparente
        texto.Parent = nomeTag  -- Coloca o texto dentro da tag

    end)
end)
