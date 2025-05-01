Pastebin
API
ferramentas
Perguntas frequentes
colar
Procurar...

Conecte-se Inscrever-se
COMPARTILHAR
TWEETAR
Usuário convidado
asd
um convidado
5 de abril de 2025
1.403
0
Nunca
Adicionar comentário
Ainda não é membro do Pastebin? Cadastre-se , ele desbloqueia muitos recursos legais!
119,24 KB | Nenhum |  
     
--[[⊹˚₊‧───────────────‧₊˚⊹·͙⁺˚*•̩̩͙✩•̩̩͙*˚⁺‧͙⁺˚*•̩ ̩͙✩•̩̩͙*˚⁺‧͙⁺˚*•̩̩͙✩•̩̩͙*˚ ⁺‧͙⊹˚₊‧───────────────‧₊˚⊹
 
  ______ ______ __ __ __     
/ \ / \| \ | \ | \    
| ▓▓▓▓▓▓\ ______ ______ _______ | ▓▓▓▓▓▓\\▓▓______ ____ | ▓▓____ ______ _| ▓▓_   
| ▓▓ | ▓▓/ \ / \| \ | ▓▓__| ▓▓\\\| ▓▓ \ / \| ▓▓\  
| ▓▓ | ▓▓ ▓▓▓▓▓▓\ ▓▓▓▓▓▓\ ▓▓▓▓▓▓▓\ | ▓▓ ▓▓ ▓▓ ▓▓▓▓▓▓\▓▓▓▓\ ▓▓▓▓▓▓▓\ ▓▓▓▓▓▓\\▓▓▓▓▓▓  
| ▓▓ | ▓▓ ▓▓ | ▓▓ ▓▓ ▓▓ ▓▓ | ▓▓ | ▓▓▓▓▓▓▓▓ ▓▓ ▓▓ | ▓▓ | ▓▓ ▓▓ | ▓▓ ▓▓ | ▓▓ | ▓▓__ 
| ▓▓__/ ▓▓ ▓▓__/ ▓▓ ▓▓▓▓▓▓▓▓ ▓▓ | ▓▓ | ▓▓ | ▓▓ ▓▓ ▓▓ | ▓▓ | ▓▓ ▓▓__/ ▓▓ ▓▓__/ ▓▓ | ▓▓| \
\▓▓ ▓▓ ▓▓ ▓▓\▓▓ \ ▓▓ | ▓▓ | ▓▓ | ▓▓ ▓▓ ▓▓ | ▓▓ | ▓▓ ▓▓ ▓▓\▓▓ ▓▓ \▓▓ ▓▓
  \▓▓▓▓▓▓| ▓▓▓▓▓▓▓ \▓▓▓▓▓▓▓\▓▓ \▓▓ \▓▓ \▓▓\▓▓\▓▓ \▓▓ \▓▓\▓▓▓▓▓▓▓ \▓▓▓▓▓▓ \▓▓▓▓ 
         | ▓▓                                                                                 
         | ▓▓                                                                                 
          \▓▓                                                                                 
 
༺☆༻____________☾✧ ✩ ✧☽____________༺☆༻༺☆༻____________☾✧ ✩ ✧☽____________༺☆༻
 
    ✨Estrutura Universal de Assistência de Mira✨
    Versão 1.9.5
 
    twix.cyou/pix
    twix.cyou/OpenAimbotV3rm
 
    Autor: ttwiz_z (ttwizz) < i@twix.cyou >
    Licença: MIT
    GitHub: https://github.com/ttwizz/Open-Aimbot
 
    Problemas: https://github.com/ttwizz/Open-Aimbot/issues
    Solicitações de pull: https://github.com/ttwizz/Open-Aimbot/pulls
    Discussões: https://github.com/ttwizz/Open-Aimbot/discussions
 
    Wiki: https://moderka.org/Open-Aimbot
 
    Trustpilot: https://www.trustpilot.com/review/moderka.org
 
•───────•°•❀•°•───────•୧‿̩͙ ˖︵ꕀ ⠀𓏶 ̣̣̥⠀ ꕀ︵˖ ̩͙‿୨•───────•°•❀•°•───────•]]
 
 
--! Depurador
 
DEBUG local = falso
 
se DEBUG então
    getfenv().getfenv = função()
        retornar setmetatable({}, {
            __index = função()
                retornar função()
                    retornar verdadeiro
                fim
            fim
        })
    fim
fim
 
 
--! Serviços
 
local HttpService = jogo:GetService("HttpService")
Jogadores locais = jogo:GetService("Jogadores")
Serviço de Entrada de Usuário local = jogo:GetService("Serviço de Entrada de Usuário")
local RunService = jogo:GetService("RunService")
TweenService local = jogo:GetService("TweenService")
 
 
--! Gerenciador de Interface
 
Configurações de interface do usuário locais = {
    Largura da guia = 160,
    Tamanho = { 580, 460 },
    Tema = "VSC Escuro Alto Contraste",
    Acrílico = falso,
    Transparência = verdadeiro,
    MinimizeKey = "Deslocamento Direito",
    ShowNotifications = verdadeiro,
    ShowWarnings = verdadeiro,
    RenderingMode = "Renderização em etapas",
    AutoImportação = verdadeiro
}
 
Gerenciador de Interface local = {}
 
função InterfaceManager:ImportSettings()
    pcall(função()
        se não DEBUG e getfenv().isfile e getfenv().readfile e getfenv().isfile("UISettings.ttwizz") e getfenv().readfile("UISettings.ttwizz") então
            para Chave, Valor no próximo, HttpService:JSONDecode(getfenv().readfile("UISettings.ttwizz")) faça
                UISettings[Chave] = Valor
            fim
        fim
    fim)
fim
 
função InterfaceManager:ExportSettings()
    pcall(função()
        se não DEBUG e getfenv().isfile e getfenv().readfile e getfenv().writefile então
            getfenv().writefile("UISettings.ttwizz", HttpService:JSONEncode(UISettings))
        fim
    fim)
fim
 
Gerenciador de Interface:ImportSettings()
 
UISettings.__LAST_RUN__ = os.date()
Gerenciador de Interface: ExportSettings()
 
 
--! Manipulador de cores
 
Manipulador de cores local = {}
 
função ColorsHandler:PackColour(Cor)
    retornar typeof(Cor) == "Cor3" e { R = Cor.R * 255, G = Cor.G * 255, B = Cor.B * 255 } ou typeof(Cor) == "tabela" e Cor ou { R = 255, G = 255, B = 255 }
fim
 
função ColorsHandler:UnpackColour(Cor)
    retornar typeof(Color) == "table" e Color3.fromRGB(Colour.R, Colour.G, Colour.B) ou typeof(Colour) == "Color3" e Colour ou Color3.fromRGB(255, 255, 255)
fim
 
 
--! Importador de configuração
 
Configuração Importada local = {}
 
pcall(função()
    se não DEBUG e getfenv().isfile e getfenv().readfile e getfenv().isfile(string.format("%s.ttwizz", game.GameId)) e getfenv().readfile(string.format("%s.ttwizz", game.GameId)) e UISettings.AutoImport então
        ImportedConfiguration = HttpService:JSONDecode(getfenv().readfile(string.format("%s.ttwizz", game.GameId)))
        para Chave, Valor em seguida, ImportedConfiguration faça
            se Chave == "FoVColour" ou Chave == "NameESPOutlineColour" ou Chave == "ESPColour" então
                ImportedConfiguration[Chave] = ColorsHandler:UnpackColour(Valor)
            fim
        fim
    fim
fim)
 
 
--! Inicializador de configuração
 
Configuração local = {}
 
--? Robô de alvo
 
Configuration.Aimbot = ImportedConfiguration["Aimbot"] ou falso
Configuration.OnePressAimingMode = ImportedConfiguration["OnePressAimingMode"] ou falso
Configuration.AimKey = ImportedConfiguration["AimKey"] ou "RMB"
Configuration.AimMode = ImportedConfiguration["AimMode"] ou "Câmera"
Configuration.SilentAimMethods = ImportedConfiguration["SilentAimMethods"] ou { "Mouse.Hit / Mouse.Target", "GetMouseLocation" }
Configuration.SilentAimChance = ImportedConfiguration["SilentAimChance"] ou 100
Configuration.OffAimbotAfterKill = ImportedConfiguration["OffAimbotAfterKill"] ou falso
Configuration.AimPartDropdownValues ​​= ImportedConfiguration["AimPartDropdownValues"] ou { "Cabeçalho", "ParteRaizHumanoide" }
Configuration.AimPart = ImportedConfiguration["AimPart"] ou "HumanoidRootPart"
Configuration.RandomAimPart = ImportedConfiguration["RandomAimPart"] ou falso
 
Configuration.UseOffset = ImportedConfiguration["UseOffset"] ou falso
Configuration.OffsetType = ImportedConfiguration["OffsetType"] ou "Estático"
Configuration.StaticOffsetIncrement = ImportedConfiguration["StaticOffsetIncrement"] ou 10
Configuration.DynamicOffsetIncrement = ImportedConfiguration["DynamicOffsetIncrement"] ou 10
Configuration.AutoOffset = ImportedConfiguration["AutoOffset"] ou falso
Configuration.MaxAutoOffset = ImportedConfiguration["MaxAutoOffset"] ou 50
 
Configuration.UseSensitivity = ImportedConfiguration["UseSensitivity"] ou falso
Configuration.Sensitivity = ImportedConfiguration["Sensibilidade"] ou 50
Configuration.UseNoise = ImportedConfiguration["UseNoise"] ou falso
Configuration.NoiseFrequency = ImportedConfiguration["NoiseFrequency"] ou 50
 
--? Robôs
 
Configuration.SpinBot = ImportedConfiguration["SpinBot"] ou falso
Configuration.OnePressSpinningMode = ImportedConfiguration["OnePressSpinningMode"] ou falso
Configuration.SpinKey = ImportedConfiguration["SpinKey"] ou "Q"
Configuration.SpinBotVelocity = ImportedConfiguration["SpinBotVelocity"] ou 50
Configuration.SpinPartDropdownValues ​​= ImportedConfiguration["SpinPartDropdownValues"] ou { "Cabeça", "HumanoidRootPart" }
Configuration.SpinPart = ImportedConfiguration["SpinPart"] ou "HumanoidRootPart"
Configuration.RandomSpinPart = ImportedConfiguration["RandomSpinPart"] ou falso
 
Configuration.TriggerBot = ImportedConfiguration["TriggerBot"] ou falso
Configuration.OnePressTriggeringMode = ImportedConfiguration["OnePressTriggeringMode"] ou falso
Configuration.SmartTriggerBot = ImportedConfiguration["SmartTriggerBot"] ou falso
Configuration.TriggerKey = ImportedConfiguration["TriggerKey"] ou "E"
Configuration.TriggerBotChance = ImportedConfiguration["TriggerBotChance"] ou 100
 
--? Cheques
 
Configuration.AliveCheck = ImportedConfiguration["AliveCheck"] ou falso
Configuration.GodCheck = ImportedConfiguration["GodCheck"] ou falso
Configuration.TeamCheck = ImportedConfiguration["TeamCheck"] ou falso
Configuration.FriendCheck = ImportedConfiguration["FriendCheck"] ou falso
Configuration.FollowCheck = ImportedConfiguration["FollowCheck"] ou falso
Configuration.VerifiedBadgeCheck = ImportedConfiguration["VerifiedBadgeCheck"] ou falso
Configuration.WallCheck = ImportedConfiguration["WallCheck"] ou falso
Configuration.WaterCheck = ImportedConfiguration["WaterCheck"] ou falso
 
Configuration.FoVCheck = ImportedConfiguration["FoVCheck"] ou falso
Configuration.FoVRadius = ImportedConfiguration["FoVRadius"] ou 100
Configuration.MagnitudeCheck = ImportedConfiguration["MagnitudeCheck"] ou falso
Configuration.TriggerMagnitude = ImportedConfiguration["TriggerMagnitude"] ou 500
Configuration.TransparencyCheck = ImportedConfiguration["TransparencyCheck"] ou falso
Configuration.IgnoredTransparency = ImportedConfiguration["IgnoredTransparency"] ou 0,5
Configuration.WhitelistedGroupCheck = ImportedConfiguration["WhitelistedGroupCheck"] ou falso
Configuration.WhitelistedGroup = ImportedConfiguration["WhitelistedGroup"] ou 0
Configuration.BlacklistedGroupCheck = ImportedConfiguration["BlacklistedGroupCheck"] ou falso
Configuration.BlacklistedGroup = ImportedConfiguration["BlacklistedGroup"] ou 0
 
Configuration.IgnoredPlayersCheck = ImportedConfiguration["IgnoredPlayersCheck"] ou falso
Configuration.IgnoredPlayersDropdownValues ​​= ImportedConfiguration["IgnoredPlayersDropdownValues"] ou {}
Configuration.IgnoredPlayers = ImportedConfiguration["IgnoredPlayers"] ou {}
Configuration.TargetPlayersCheck = ImportedConfiguration["TargetPlayersCheck"] ou falso
Configuration.TargetPlayersDropdownValues ​​= ImportedConfiguration["TargetPlayersDropdownValues"] ou {}
Configuration.TargetPlayers = ImportedConfiguration["TargetPlayers"] ou {}
 
Configuration.PremiumCheck = ImportedConfiguration["PremiumCheck"] ou falso
 
--? Visuais
 
Configuration.FoV = ImportedConfiguration["FoV"] ou falso
Configuration.FoVKey = ImportedConfiguration["FoVKey"] ou "R"
Configuration.FoVThickness = ImportedConfiguration["FoVThickness"] ou 2
Configuration.FoVOpacity = ImportedConfiguration["FoVOpacity"] ou 0,8
Configuration.FoVFilled = ImportedConfiguration["FoVFilled"] ou falso
Configuration.FoVColour = ImportedConfiguration["FoVColour"] ou Color3.fromRGB(255, 255, 255)
 
Configuration.SmartESP = ImportedConfiguration["SmartESP"] ou falso
Configuration.ESPKey = ImportedConfiguration["ESPKey"] ou "T"
Configuration.ESPBox = ImportedConfiguration["ESPBox"] ou falso
Configuration.ESPBoxFilled = ImportedConfiguration["ESPBoxFilled"] ou falso
Configuration.NameESP = ImportedConfiguration["NameESP"] ou falso
Configuration.NameESPFont = ImportedConfiguration["NameESPFont"] ou "Monospace"
Configuration.NameESPSize = ImportedConfiguration["NameESPSize"] ou 16
Configuration.NameESPOutlineColour = ImportedConfiguration["NameESPOutlineColour"] ou Color3.fromRGB(0, 0, 0)
Configuration.HealthESP = ImportedConfiguration["HealthESP"] ou falso
Configuration.MagnitudeESP = ImportedConfiguration["MagnitudeESP"] ou falso
Configuration.TracerESP = ImportedConfiguration["TracerESP"] ou falso
Configuration.ESPThickness = ImportedConfiguration["ESPThickness"] ou 2
Configuration.ESPOpacity = ImportedConfiguration["ESPOpacity"] ou 0,8
Configuration.ESPCour = ImportedConfiguration["ESPCour"] ou Color3.fromRGB(255, 255, 255)
Configuration.ESPUseTeamColour = ImportedConfiguration["ESPUseTeamColour"] ou falso
 
Configuration.RainbowVisuals = ImportedConfiguration["RainbowVisuals"] ou falso
Configuration.RainbowDelay = ImportedConfiguration["RainbowDelay"] ou 5
 
 
--! Constantes
 
Jogador local = Jogadores.JogadorLocal
Mouse local = Jogador:ObterMouse()
local IsComputer = UserInputService.KeyboardEnabled e UserInputService.MouseEnabled
 
Etiquetas mensais locais = { "🎅%s❄️", "☃️%s🏂", "🌷%s☘️", "🌺%s🎀", "🐝%s🌼", "🌈%s😎", "🌞%s🏖️", "☀️%s💐", "🌦%s🍁", "🎃%s💀", "🍂%s☕", "🎄%s🎁" }
Etiquetas Premium locais = { "💫PREMIUM💫", "✨PREMIUM✨", "🌟PREMIUM🌟", "⭐PREMIUM⭐", "🤩PREMIUM🤩" }
 
 
--! Manipulador de nomes
 
função local GetPlayerName(String)
    se typeof(String) == "string" e #String > 0 então
        para _, _Player em seguida, Players:GetPlayers() faça
            se string.sub(string.lower(_Player.Name), 1, #string.lower(String)) == string.lower(String) então
                retornar _Player.Name
            fim
        fim
    fim
    retornar ""
fim
 
 
--! Campos
 
Status local = ""
 
Fluente local = nulo
ShowWarning local = falso
 
RobloxActive local = verdadeiro
Relógio local = os.clock()
 
Mira local = falso
Alvo local = nulo
Tween local = nulo
Sensibilidade do Mouse local = UserInputService.MouseDeltaSensitivity
 
Spinning local = falso
Disparo local = falso
Campo de exibição local = falso
local MostrandoESP = falso
 
fazer
    se typeof(script) == "Instance" e script:FindFirstChild("Fluent") e script:FindFirstChild("Fluent"):IsA("ModuleScript") então
        Fluente = require(script:FindFirstChild("Fluente"))
    outro
        Sucesso local, Resultado = pcall(function()
            retornar jogo:HttpGet("https://twix.cyou/Fluent.txt", true)
        fim)
        se Sucesso e typeof(Resultado) == "string" e string.find(Resultado, "dawid") então
            Fluente = getfenv().loadstring(Resultado)()
            se Fluent.Premium então
                retornar getfenv().loadstring(jogo:HttpGet("https://twix.cyou/Aimbot.txt", verdadeiro))()
            fim
            Sucesso local, Resultado = pcall(function()
                retornar jogo:HttpGet("https://twix.cyou/AimbotStatus.json", true)
            fim)
            se Sucesso e typeof(Resultado) == "string" e pcall(HttpService.JSONDecode, HttpService, Resultado) e typeof(HttpService:JSONDecode(Resultado).message) == "string" então
                Status = HttpService:JSONDecode(Resultado).mensagem
            fim
        outro
            retornar
        fim
    fim
fim
 
Sensibilidade local alterada; Sensibilidade alterada = UserInputService:GetPropertyChangedSignal("MouseDeltaSensitivity"):Connect(function()
    se não for fluente então
        Sensibilidade alterada: Desconectar()
    caso contrário, se não for Aiming ou não DEBUG e (getfenv().mousemoverel e IsComputer e Configuration.AimMode == "Mouse" ou getfenv().hookmetamethod e getfenv().newcclosure e getfenv().checkcaller e getfenv().getnamecallmethod e Configuration.AimMode == "Silent") então
        SensibilidadeDoMouse = UserInputService.SensibilidadeDoMouseDelta
    fim
fim)
 
 
--! Inicializador de IU
 
fazer
    Janela local = Fluente:CriarJanela({
        Título = string.format("%s <b><i>%s</i></b>", string.format(MonthlyLabels[os.date("*t").month], "Abrir Aimbot"), #Status > 0 e Status ou "🔥GRÁTIS🔥"),
        Subtítulo = "Por @ttwiz_z",
        TabWidth = Configurações de interface do usuário.TabWidth,
        Tamanho = UDim2.fromOffset(table.unpack(UISettings.Size)),
        Tema = UISettings.Theme,
        Acrílico = UISettings.Acrílico,
        MinimizeKey = Configurações de UI.MinimizeKey
    })
 
    Guias locais = { Aimbot = Janela:AddTab({ Título = "Aimbot", Ícone = "mira" }) }
 
    Janela:SelecionarGuia(1)
 
    Guias.Aimbot:AddParagraph({
        Título = string.format("%s 🔥GRÁTIS🔥", string.format(EtiquetasMensais[os.date("*t").mês], "Abrir Aimbot")),
        Conteúdo = "✨Estrutura Universal de Assistência de Mira✨\nhttps://github.com/ttwizz/Open-Aimbot"
    })
 
    local AimbotSection = Tabs.Aimbot:AddSection("Aimbot")
 
    local AimbotToggle = AimbotSection:AddToggle("Aimbot", { Título = "Aimbot", Descrição = "Alterna o Aimbot", Padrão = Configuration.Aimbot })
    AimbotToggle:OnChanged(função(Valor)
        Configuração.Aimbot = Valor
        se não for IsComputer então
            Objetivo = Valor
        fim
    fim)
 
    se IsComputer então
        local OnePressAimingModeToggle = AimbotSection:AddToggle("OnePressAimingMode", { Título = "Modo de um toque", Descrição = "Usa o Modo de um toque em vez do Modo de espera", Padrão = Configuration.OnePressAimingMode })
        OnePressAimingModeToggle:OnChanged(função(Valor)
            Configuration.OnePressAimingMode = Valor
        fim)
 
        AimKeybind local = AimbotSection:AddKeybind("AimKey", {
            Título = "Chave de mira",
            Descrição = "Altera a tecla de mira",
            Padrão = Configuração.AimKey,
            ChangedCallback = função(Valor)
                Configuração.AimKey = Valor
            fim
        })
        Configuration.AimKey = AimKeybind.Value ~= "RMB" e Enum.KeyCode[AimKeybind.Value] ou Enum.UserInputType.MouseButton2
    fim
 
    local AimModeDropdown = AimbotSection:AddDropdown("AimMode", {
        Título = "Modo de Mira",
        Descrição = "Altera o Modo de Mira",
        Valores = { "Câmera" },
        Padrão = Configuração.AimMode,
        Retorno de chamada = função(Valor)
            Configuração.AimMode = Valor
        fim
    })
    se getfenv().mousemoverel e IsComputer então
        tabela.inserir(AimModeDropdown.Values, "Mouse")
        AimModeDropdown:BuildDropdownList()
    outro
        ShowWarning = verdadeiro
    fim
    se getfenv().hookmetamethod e getfenv().newcclosure e getfenv().checkcaller e getfenv().getnamecallmethod então
        tabela.inserir(AimModeDropdown.Values, "Silencioso")
        AimModeDropdown:BuildDropdownList()
 
        local SilentAimMethodsDropdown = AimbotSection:AddDropdown("MétodosSilentAim", {
            Título = "Métodos de Mira Silenciosa",
            Descrição = "Define os métodos de mira silenciosa",
            Valores = { "Mouse.Hit / Mouse.Target", "GetMouseLocation", "Raycast", "FindPartOnRay", "FindPartOnRayWithIgnoreList", "FindPartOnRayWithWhitelist" },
            Multi = verdadeiro,
            Padrão = Configuração.MétodosDeAimSilencioso
        })
        SilentAimMethodsDropdown:OnChanged(função(Valor)
            Configuração.SilentAimMethods = {}
            para Chave, _ em seguida, Valor faça
                se typeof(Key) == "string" então
                    tabela.inserir(Configuração.MétodosDeAimSilencioso, Chave)
                fim
            fim
        fim)
 
        AimbotSection:AddSlider("ChanceDeAimSilencioso", {
            Título = "Chance de Mira Silenciosa",
            Descrição = "Altera a chance de acerto da Mira Silenciosa",
            Padrão = Configuration.SilentAimChance,
            Mín = 1,
            Máx = 100,
            Arredondamento = 1,
            Retorno de chamada = função(Valor)
                Configuração.SilentAimChance = Valor
            fim
        })
    outro
        ShowWarning = verdadeiro
    fim
 
    local OffAimbotAfterKillToggle = AimbotSection:AddToggle("OffAimbotAfterKill", { Title = "Desligado após matar", Description = "Desativa o modo de mira após matar um alvo", Default = Configuration.OffAimbotAfterKill })
    OffAimbotAfterKillToggle:OnChanged(função(Valor)
        Configuração.OffAimbotAfterKill = Valor
    fim)
 
    local AimPartDropdown = AimbotSection:AddDropdown("AimPart", {
        Título = "Parte Objetivo",
        Descrição = "Altera a parte da mira",
        Valores = Configuration.AimPartDropdownValues,
        Padrão = Configuration.AimPart,
        Retorno de chamada = função(Valor)
            Configuração.AimPart = Valor
        fim
    })
 
    local RandomAimPartToggle = AimbotSection:AddToggle("RandomAimPart", { Title = "Parte de mira aleatória", Description = "Seleciona a cada segundo uma parte de mira aleatória no menu suspenso", Default = Configuration.RandomAimPart })
    RandomAimPartToggle:OnChanged(função(Valor)
        Configuração.RandomAimPart = Valor
    fim)
 
    AimbotSection:AddInput("AdicionarParteAim", {
        Título = "Adicionar parte de mira",
        Descrição = "Após digitar, pressione Enter",
        Concluído = verdadeiro,
        Espaço reservado = "Nome da parte",
        Retorno de chamada = função(Valor)
            se #Value > 0 e não table.find(Configuration.AimPartDropdownValues, Value) então
                tabela.insert(Configuração.AimPartDropdownValues, Valor)
                AimPartDropdown:SetValue(Valor)
            fim
        fim
    })
 
    AimbotSection:AddInput("RemoverAimPart", {
        Título = "Remover parte da mira",
        Descrição = "Após digitar, pressione Enter",
        Concluído = verdadeiro,
        Espaço reservado = "Nome da parte",
        Retorno de chamada = função(Valor)
            se #Value > 0 e table.find(Configuration.AimPartDropdownValues, Value) então
                se Configuration.AimPart == Valor então
                    AimPartDropdown:SetValue(nulo)
                fim
                tabela.remove(Configuração.AimPartDropdownValues, tabela.find(Configuração.AimPartDropdownValues, Valor))
                AimPartDropdown:SetValues(Configuração.AimPartDropdownValues)
            fim
        fim
    })
 
    AimbotSection:AddButton({
        Título = "Limpar todos os itens",
        Descrição = "Remove todos os elementos",
        Retorno de chamada = função()
            Itens locais = #Configuration.AimPartDropdownValues
            AimPartDropdown:SetValue(nulo)
            Configuração.AimPartDropdownValues ​​= {}
            AimPartDropdown:SetValues(Configuração.AimPartDropdownValues)
            Janela:Diálogo({
                Título = string.format(MonthlyLabels[os.date("*t").month], "Abrir Aimbot"),
                Conteúdo = Itens == 0 e "Nada foi limpo!" ou Itens == 1 e "1 item foi limpo!" ou string.format("%s itens foram limpos!", Itens),
                Botões = {
                    {
                        Título = "Confirmar"
                    }
                }
            })
        fim
    })
 
    local AimOffsetSection = Tabs.Aimbot:AddSection("Deslocamento de Mira")
 
    local UseOffsetToggle = AimOffsetSection:AddToggle("UseOffset", { Título = "Usar Offset", Descrição = "Alterna o Offset", Padrão = Configuration.UseOffset })
    UseOffsetToggle:OnChanged(função(Valor)
        Configuração.UseOffset = Valor
    fim)
 
    AimOffsetSection:AddDropdown("Tipo de Deslocamento", {
        Título = "Tipo de deslocamento",
        Descrição = "Altera o tipo de deslocamento",
        Valores = { "Estático", "Dinâmico", "Estático e Dinâmico" },
        Padrão = Configuração.OffsetType,
        Retorno de chamada = função(Valor)
            Configuração.OffsetType = Valor
        fim
    })
 
    AimOffsetSection:AddSlider("Incremento de Offset Estático", {
        Título = "Incremento de deslocamento estático",
        Descrição = "Altera o incremento de deslocamento estático",
        Padrão = Configuration.StaticOffsetIncrement,
        Mín = 1,
        Máx = 50,
        Arredondamento = 1,
        Retorno de chamada = função(Valor)
            Configuration.StaticOffsetIncrement = Valor
        fim
    })
 
    AimOffsetSection:AddSlider("Incremento de Offset Dinâmico", {
        Título = "Incremento de deslocamento dinâmico",
        Descrição = "Altera o incremento de deslocamento dinâmico",
        Padrão = Configuração.DynamicOffsetIncrement,
        Mín = 1,
        Máx = 50,
        Arredondamento = 1,
        Retorno de chamada = função(Valor)
            Configuração.DynamicOffsetIncrement = Valor
        fim
    })
 
    local AutoOffsetToggle = AimOffsetSection:AddToggle("AutoOffset", { Título = "Deslocamento automático", Descrição = "Alterna o deslocamento automático", Padrão = Configuration.AutoOffset })
    AutoOffsetToggle:OnChanged(função(Valor)
        Configuração.AutoOffset = Valor
    fim)
 
    AimOffsetSection:AddSlider("Deslocamento Automático Máximo", {
        Título = "Deslocamento automático máximo",
        Descrição = "Altera o deslocamento automático máximo",
        Padrão = Configuração.MaxAutoOffset,
        Mín = 1,
        Máx = 50,
        Arredondamento = 1,
        Retorno de chamada = função(Valor)
            Configuração.MaxAutoOffset = Valor
        fim
    })
 
    Sensibilidade local RuídoSeção = Tabs.Aimbot:AddSection("Sensibilidade e Ruído")
 
    local UseSensitivityToggle = SensitivityNoiseSection:AddToggle("UseSensitivity", { Título = "Usar Sensibilidade", Descrição = "Alterna a Sensibilidade", Padrão = Configuration.UseSensitivity })
    UseSensitivityToggle:OnChanged(função(Valor)
        Configuração.UseSensitivity = Valor
    fim)
 
    SensitivityNoiseSection:AddSlider("Sensibilidade", {
        Título = "Sensibilidade",
        Descrição = "Suaviza os movimentos do mouse/câmera ao mirar",
        Padrão = Configuração.Sensibilidade,
        Mín = 1,
        Máx = 100,
        Arredondamento = 1,
        Retorno de chamada = função(Valor)
            Configuração.Sensibilidade = Valor
        fim
    })
 
    local UseNoiseToggle = SensitivityNoiseSection:AddToggle("UseNoise", { Title = "Usar Ruído", Description = "Alterna a trepidação da câmera ao mirar", Default = Configuration.UseNoise })
    UseNoiseToggle:OnChanged(função(Valor)
        Configuração.UseNoise = Valor
    fim)
 
    SensibilidadeRuídoSeção:AddSlider("Frequência de Ruído", {
        Título = "Frequência de ruído",
        Descrição = "Altera a frequência do ruído",
        Padrão = Configuração.Frequência de Ruído,
        Mín = 1,
        Máx = 100,
        Arredondamento = 1,
        Retorno de chamada = função(Valor)
            Configuração.FrequênciaDeRuído = Valor
        fim
    })
 
    Tabs.Bots = Janela:AddTab({ Título = "Bots", Ícone = "bot" })
 
    Guias.Bots:AddParagraph({
        Título = string.format("%s 🔥GRÁTIS🔥", string.format(EtiquetasMensais[os.date("*t").mês], "Abrir Aimbot")),
        Conteúdo = "✨Estrutura Universal de Assistência de Mira✨\nhttps://github.com/ttwizz/Open-Aimbot"
    })
 
    Seção SpinBot local = Guias.Bots:AddSection("SpinBot")
 
    SpinBotSection:AddParagraph({
        Título = "NOTA",
        Conteúdo = "O SpinBot não funciona normalmente no Modo de Renderização RenderStepped. Defina um valor diferente de RenderStepped para resolver este problema."
    })
 
    local SpinBotToggle = SpinBotSection:AddToggle("SpinBot", { Título = "SpinBot", Descrição = "Alterna o SpinBot", Padrão = Configuration.SpinBot })
    SpinBotToggle:OnChanged(função(Valor)
        Configuração.SpinBot = Valor
        se não for IsComputer então
            Girando = Valor
        fim
    fim)
 
    se IsComputer então
        local OnePressSpinningModeToggle = SpinBotSection:AddToggle("OnePressSpinningMode", { Título = "Modo de um toque", Descrição = "Usa o modo de um toque em vez do modo de espera", Padrão = Configuration.OnePressSpinningMode })
        OnePressSpinningModeToggle:OnChanged(função(Valor)
            Configuração.OnePressSpinningMode = Valor
        fim)
 
        local SpinKeybind = SpinBotSection:AddKeybind("SpinKey", {
            Título = "Girar Chave",
            Descrição = "Altera a tecla de rotação",
            Padrão = Configuration.SpinKey,
            ChangedCallback = função(Valor)
                Configuração.SpinKey = Valor
            fim
        })
        Configuration.SpinKey = SpinKeybind.Value ~= "RMB" e Enum.KeyCode[SpinKeybind.Value] ou Enum.UserInputType.MouseButton2
    fim
 
    SpinBotSection:AddSlider("Velocidade do SpinBot", {
        Título = "Velocidade do SpinBot",
        Descrição = "Altera a velocidade do SpinBot",
        Padrão = Configuração.SpinBotVelocity,
        Mín = 1,
        Máx = 50,
        Arredondamento = 1,
        Retorno de chamada = função(Valor)
            Configuração.SpinBotVelocity = Valor
        fim
    })
 
    local SpinPartDropdown = SpinBotSection:AddDropdown("SpinPart", {
        Título = "Parte de rotação",
        Descrição = "Altera a parte de rotação",
        Valores = Configuration.SpinPartDropdownValues,
        Padrão = Configuration.SpinPart,
        Retorno de chamada = função(Valor)
            Configuração.SpinPart = Valor
        fim
    })
 
    local RandomSpinPartToggle = SpinBotSection:AddToggle("RandomSpinPart", { Title = "Parte de rotação aleatória", Description = "Seleciona a cada segundo uma parte de rotação aleatória no menu suspenso", Default = Configuration.RandomSpinPart })
    RandomSpinPartToggle:OnChanged(função(Valor)
        Configuração.RandomSpinPart = Valor
    fim)
 
    SpinBotSection:AddInput("AdicionarParteGiratória", {
        Título = "Adicionar parte de rotação",
        Descrição = "Após digitar, pressione Enter",
        Concluído = verdadeiro,
        Espaço reservado = "Nome da parte",
        Retorno de chamada = função(Valor)
            se #Value > 0 e não table.find(Configuration.SpinPartDropdownValues, Value) então
                tabela.insert(Configuração.SpinPartDropdownValues, Valor)
                SpinPartDropdown:SetValue(Valor)
            fim
        fim
    })
 
    SpinBotSection:AddInput("RemoverParteGirar", {
        Título = "Remover parte de rotação",
        Descrição = "Após digitar, pressione Enter",
        Concluído = verdadeiro,
        Espaço reservado = "Nome da parte",
        Retorno de chamada = função(Valor)
            se #Value > 0 e table.find(Configuration.SpinPartDropdownValues, Value) então
                se Configuration.SpinPart == Valor então
                    SpinPartDropdown:DefinirValor(nulo)
                fim
                tabela.remove(Configuração.SpinPartDropdownValues, tabela.find(Configuração.SpinPartDropdownValues, Valor))
                SpinPartDropdown:SetValues(Configuração.SpinPartDropdownValues)
            fim
        fim
    })
 
    SpinBotSection:AddButton({
        Título = "Limpar todos os itens",
        Descrição = "Remove todos os elementos",
        Retorno de chamada = função()
            Itens locais = #Configuration.SpinPartDropdownValues
            SpinPartDropdown:DefinirValor(nulo)
            Configuração.SpinPartDropdownValues ​​= {}
            SpinPartDropdown:SetValues(Configuração.SpinPartDropdownValues)
            Janela:Diálogo({
                Título = string.format(MonthlyLabels[os.date("*t").month], "Abrir Aimbot"),
                Conteúdo = Itens == 0 e "Nada foi limpo!" ou Itens == 1 e "1 item foi limpo!" ou string.format("%s itens foram limpos!", Itens),
                Botões = {
                    {
                        Título = "Confirmar"
                    }
                }
            })
        fim
    })
 
    se getfenv().mouse1click e IsComputer então
        TriggerBotSection local = Guias.Bots:AddSection("TriggerBot")
 
        local TriggerBotToggle = TriggerBotSection:AddToggle("TriggerBot", { Título = "TriggerBot", Descrição = "Alterna o TriggerBot", Padrão = Configuration.TriggerBot })
        TriggerBotToggle:OnChanged(função(Valor)
            Configuração.TriggerBot = Valor
        fim)
 
        local OnePressTriggeringModeToggle = TriggerBotSection:AddToggle("OnePressTriggeringMode", { Título = "Modo de um toque", Descrição = "Usa o Modo de um toque em vez do Modo de espera", Padrão = Configuration.OnePressTriggeringMode })
        OnePressTriggeringModeToggle:OnChanged(função(Valor)
            Configuration.OnePressTriggeringMode = Valor
        fim)
 
        local SmartTriggerBotToggle = TriggerBotSection:AddToggle("SmartTriggerBot", { Título = "Smart TriggerBot", Descrição = "Usa o TriggerBot somente ao mirar", Padrão = Configuration.SmartTriggerBot })
        SmartTriggerBotToggle:OnChanged(função(Valor)
            Configuration.SmartTriggerBot = Value
        end)
 
        local TriggerKeybind = TriggerBotSection:AddKeybind("TriggerKey", {
            Title = "Trigger Key",
            Description = "Changes the Trigger Key",
            Default = Configuration.TriggerKey,
            ChangedCallback = function(Value)
                Configuration.TriggerKey = Value
            end
        })
        Configuration.TriggerKey = TriggerKeybind.Value ~= "RMB" and Enum.KeyCode[TriggerKeybind.Value] or Enum.UserInputType.MouseButton2
 
        TriggerBotSection:AddSlider("TriggerBotChance", {
            Title = "TriggerBot Chance",
            Description = "Changes the Hit Chance for TriggerBot",
            Default = Configuration.TriggerBotChance,
            Min = 1,
            Max = 100,
            Rounding = 1,
            Callback = function(Value)
                Configuration.TriggerBotChance = Value
            end
        })
    else
        ShowWarning = true
    end
 
    Tabs.Checks = Window:AddTab({ Title = "Checks", Icon = "list-checks" })
 
    Tabs.Checks:AddParagraph({
        Title = string.format("%s 🔥FREE🔥", string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot")),
        Content = "✨Universal Aim Assist Framework✨\nhttps://github.com/ttwizz/Open-Aimbot"
    })
 
    local SimpleChecksSection = Tabs.Checks:AddSection("Simple Checks")
 
    local AliveCheckToggle = SimpleChecksSection:AddToggle("AliveCheck", { Title = "Alive Check", Description = "Toggles the Alive Check", Default = Configuration.AliveCheck })
    AliveCheckToggle:OnChanged(function(Value)
        Configuration.AliveCheck = Value
    end)
 
    local GodCheckToggle = SimpleChecksSection:AddToggle("GodCheck", { Title = "God Check", Description = "Toggles the God Check", Default = Configuration.GodCheck })
    GodCheckToggle:OnChanged(function(Value)
        Configuration.GodCheck = Value
    end)
 
    local TeamCheckToggle = SimpleChecksSection:AddToggle("TeamCheck", { Title = "Team Check", Description = "Toggles the Team Check", Default = Configuration.TeamCheck })
    TeamCheckToggle:OnChanged(function(Value)
        Configuration.TeamCheck = Value
    end)
 
    local FriendCheckToggle = SimpleChecksSection:AddToggle("FriendCheck", { Title = "Friend Check", Description = "Toggles the Friend Check", Default = Configuration.FriendCheck })
    FriendCheckToggle:OnChanged(function(Value)
        Configuration.FriendCheck = Value
    end)
 
    local FollowCheckToggle = SimpleChecksSection:AddToggle("FollowCheck", { Title = "Follow Check", Description = "Toggles the Follow Check", Default = Configuration.FollowCheck })
    FollowCheckToggle:OnChanged(function(Value)
        Configuration.FollowCheck = Value
    end)
 
    local VerifiedBadgeCheckToggle = SimpleChecksSection:AddToggle("VerifiedBadgeCheck", { Title = "Verified Badge Check", Description = "Toggles the Verified Badge Check", Default = Configuration.VerifiedBadgeCheck })
    VerifiedBadgeCheckToggle:OnChanged(function(Value)
        Configuration.VerifiedBadgeCheck = Value
    end)
 
    local WallCheckToggle = SimpleChecksSection:AddToggle("WallCheck", { Title = "Wall Check", Description = "Toggles the Wall Check", Default = Configuration.WallCheck })
    WallCheckToggle:OnChanged(function(Value)
        Configuration.WallCheck = Value
    end)
 
    local WaterCheckToggle = SimpleChecksSection:AddToggle("WaterCheck", { Title = "Water Check", Description = "Toggles the Water Check if Wall Check is enabled", Default = Configuration.WaterCheck })
    WaterCheckToggle:OnChanged(function(Value)
        Configuration.WaterCheck = Value
    end)
 
    local AdvancedChecksSection = Tabs.Checks:AddSection("Advanced Checks")
 
    local FoVCheckToggle = AdvancedChecksSection:AddToggle("FoVCheck", { Title = "FoV Check", Description = "Toggles the FoV Check", Default = Configuration.FoVCheck })
    FoVCheckToggle:OnChanged(function(Value)
        Configuration.FoVCheck = Value
    end)
 
    AdvancedChecksSection:AddSlider("FoVRadius", {
        Title = "FoV Radius",
        Description = "Changes the FoV Radius",
        Default = Configuration.FoVRadius,
        Min = 10,
        Max = 1000,
        Rounding = 1,
        Callback = function(Value)
            Configuration.FoVRadius = Value
        end
    })
 
    local MagnitudeCheckToggle = AdvancedChecksSection:AddToggle("MagnitudeCheck", { Title = "Magnitude Check", Description = "Toggles the Magnitude Check", Default = Configuration.MagnitudeCheck })
    MagnitudeCheckToggle:OnChanged(function(Value)
        Configuration.MagnitudeCheck = Value
    end)
 
    AdvancedChecksSection:AddSlider("TriggerMagnitude", {
        Title = "Trigger Magnitude",
        Description = "Distance between the Native and the Target Character",
        Default = Configuration.TriggerMagnitude,
        Min = 10,
        Max = 1000,
        Rounding = 1,
        Callback = function(Value)
            Configuration.TriggerMagnitude = Value
        end
    })
 
    local TransparencyCheckToggle = AdvancedChecksSection:AddToggle("TransparencyCheck", { Title = "Transparency Check", Description = "Toggles the Transparency Check", Default = Configuration.TransparencyCheck })
    TransparencyCheckToggle:OnChanged(function(Value)
        Configuration.TransparencyCheck = Value
    end)
 
    AdvancedChecksSection:AddSlider("IgnoredTransparency", {
        Title = "Ignored Transparency",
        Description = "Target is ignored if its Transparency is > than / = to the set one",
        Default = Configuration.IgnoredTransparency,
        Min = 0.1,
        Max = 1,
        Rounding = 1,
        Callback = function(Value)
            Configuration.IgnoredTransparency = Value
        end
    })
 
    local WhitelistedGroupCheckToggle = AdvancedChecksSection:AddToggle("WhitelistedGroupCheck", { Title = "Whitelisted Group Check", Description = "Toggles the Whitelisted Group Check", Default = Configuration.WhitelistedGroupCheck })
    WhitelistedGroupCheckToggle:OnChanged(function(Value)
        Configuration.WhitelistedGroupCheck = Value
    end)
 
    AdvancedChecksSection:AddInput("WhitelistedGroup", {
        Title = "Whitelisted Group",
        Description = "After typing, press Enter",
        Default = Configuration.WhitelistedGroup,
        Numeric = true,
        Finished = true,
        Placeholder = "Group Id",
        Callback = function(Value)
            Configuration.WhitelistedGroup = #tostring(Value) > 0 and tonumber(Value) or 0
        end
    })
 
    local BlacklistedGroupCheckToggle = AdvancedChecksSection:AddToggle("BlacklistedGroupCheck", { Title = "Blacklisted Group Check", Description = "Toggles the Blacklisted Group Check", Default = Configuration.BlacklistedGroupCheck })
    BlacklistedGroupCheckToggle:OnChanged(function(Value)
        Configuration.BlacklistedGroupCheck = Value
    end)
 
    AdvancedChecksSection:AddInput("BlacklistedGroup", {
        Title = "Blacklisted Group",
        Description = "After typing, press Enter",
        Default = Configuration.BlacklistedGroup,
        Numeric = true,
        Finished = true,
        Placeholder = "Group Id",
        Callback = function(Value)
            Configuration.BlacklistedGroup = #tostring(Value) > 0 and tonumber(Value) or 0
        end
    })
 
    local ExpertChecksSection = Tabs.Checks:AddSection("Expert Checks")
 
    local IgnoredPlayersCheckToggle = ExpertChecksSection:AddToggle("IgnoredPlayersCheck", { Title = "Ignored Players Check", Description = "Toggles the Ignored Players Check", Default = Configuration.IgnoredPlayersCheck })
    IgnoredPlayersCheckToggle:OnChanged(function(Value)
        Configuration.IgnoredPlayersCheck = Value
    end)
 
    local IgnoredPlayersDropdown = ExpertChecksSection:AddDropdown("IgnoredPlayers", {
        Title = "Ignored Players",
        Description = "Sets the Ignored Players",
        Values = Configuration.IgnoredPlayersDropdownValues,
        Multi = true,
        Default = Configuration.IgnoredPlayers
    })
    IgnoredPlayersDropdown:OnChanged(function(Value)
        Configuration.IgnoredPlayers = {}
        for Key, _ in next, Value do
            if typeof(Key) == "string" then
                table.insert(Configuration.IgnoredPlayers, Key)
            end
        end
    end)
 
    ExpertChecksSection:AddInput("AddIgnoredPlayer", {
        Title = "Add Ignored Player",
        Description = "After typing, press Enter",
        Finished = true,
        Placeholder = "Player Name",
        Callback = function(Value)
            Value = #GetPlayerName(Value) > 0 and GetPlayerName(Value) or pcall(Players.GetUserIdFromNameAsync, Players, Value) and pcall(Players.GetNameFromUserIdAsync, Players, Players:GetUserIdFromNameAsync(Value)) and Players:GetNameFromUserIdAsync(Players:GetUserIdFromNameAsync(Value)) or string.sub(Value, 1, 1) == "@" and (#GetPlayerName(string.sub(Value, 2)) > 0 and GetPlayerName(string.sub(Value, 2)) or pcall(Players.GetUserIdFromNameAsync, Players, string.sub(Value, 2)) and pcall(Players.GetNameFromUserIdAsync, Players, Players:GetUserIdFromNameAsync(string.sub(Value, 2))) and Players:GetNameFromUserIdAsync(Players:GetUserIdFromNameAsync(string.sub(Value, 2)))) or string.sub(Value, 1, 1) == "#" and pcall(Players.GetNameFromUserIdAsync, Players, tonumber(string.sub(Value, 2))) and Players:GetNameFromUserIdAsync(tonumber(string.sub(Value, 2))) or ""
            if #Value > 0 and not table.find(Configuration.IgnoredPlayersDropdownValues, Value) then
                table.insert(Configuration.IgnoredPlayersDropdownValues, Value)
                if not table.find(Configuration.IgnoredPlayers, Value) then
                    IgnoredPlayersDropdown.Value[Value] = true
                    table.insert(Configuration.IgnoredPlayers, Value)
                end
                IgnoredPlayersDropdown:BuildDropdownList()
            end
        end
    })
 
    ExpertChecksSection:AddInput("RemoveIgnoredPlayer", {
        Title = "Remove Ignored Player",
        Description = "After typing, press Enter",
        Finished = true,
        Placeholder = "Player Name",
        Callback = function(Value)
            Value = #GetPlayerName(Value) > 0 and GetPlayerName(Value) or pcall(Players.GetUserIdFromNameAsync, Players, Value) and pcall(Players.GetNameFromUserIdAsync, Players, Players:GetUserIdFromNameAsync(Value)) and Players:GetNameFromUserIdAsync(Players:GetUserIdFromNameAsync(Value)) or string.sub(Value, 1, 1) == "@" and (#GetPlayerName(string.sub(Value, 2)) > 0 and GetPlayerName(string.sub(Value, 2)) or pcall(Players.GetUserIdFromNameAsync, Players, string.sub(Value, 2)) and pcall(Players.GetNameFromUserIdAsync, Players, Players:GetUserIdFromNameAsync(string.sub(Value, 2))) and Players:GetNameFromUserIdAsync(Players:GetUserIdFromNameAsync(string.sub(Value, 2)))) or string.sub(Value, 1, 1) == "#" and pcall(Players.GetNameFromUserIdAsync, Players, tonumber(string.sub(Value, 2))) and Players:GetNameFromUserIdAsync(tonumber(string.sub(Value, 2))) or ""
            if #Value > 0 and table.find(Configuration.IgnoredPlayersDropdownValues, Value) then
                if table.find(Configuration.IgnoredPlayers, Value) then
                    IgnoredPlayersDropdown.Value[Value] = nil
                    table.remove(Configuration.IgnoredPlayers, table.find(Configuration.IgnoredPlayers, Value))
                    IgnoredPlayersDropdown:Display()
                end
                table.remove(Configuration.IgnoredPlayersDropdownValues, table.find(Configuration.IgnoredPlayersDropdownValues, Value))
                IgnoredPlayersDropdown:SetValues(Configuration.IgnoredPlayersDropdownValues)
            end
        end
    })
 
    ExpertChecksSection:AddButton({
        Title = "Deselect All Items",
        Description = "Deselects All Elements",
        Callback = function()
            local Items = #Configuration.IgnoredPlayers
            IgnoredPlayersDropdown:SetValue({})
            Window:Dialog({
                Title = string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot"),
                Content = Items == 0 and "Nothing has been deselected!" or Items == 1 and "1 Item has been deselected!" or string.format("%s Items have been deselected!", Items),
                Buttons = {
                    {
                        Title = "Confirm"
                    }
                }
            })
        end
    })
 
    ExpertChecksSection:AddButton({
        Title = "Clear Unselected Items",
        Description = "Removes Unselected Players",
        Callback = function()
            local Cache = {}
            local Items = 0
            for _, Value in next, Configuration.IgnoredPlayersDropdownValues do
                if table.find(Configuration.IgnoredPlayers, Value) then
                    table.insert(Cache, Value)
                else
                    Items = Items + 1
                end
            end
            Configuration.IgnoredPlayersDropdownValues = Cache
            IgnoredPlayersDropdown:SetValues(Configuration.IgnoredPlayersDropdownValues)
            Window:Dialog({
                Title = string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot"),
                Content = Items == 0 and "Nothing has been cleared!" or Items == 1 and "1 Item has been cleared!" or string.format("%s Items have been cleared!", Items),
                Buttons = {
                    {
                        Title = "Confirm"
                    }
                }
            })
        end
    })
 
    local TargetPlayersCheckToggle = ExpertChecksSection:AddToggle("TargetPlayersCheck", { Title = "Target Players Check", Description = "Toggles the Target Players Check", Default = Configuration.TargetPlayersCheck })
    TargetPlayersCheckToggle:OnChanged(function(Value)
        Configuration.TargetPlayersCheck = Value
    end)
 
    local TargetPlayersDropdown = ExpertChecksSection:AddDropdown("TargetPlayers", {
        Title = "Target Players",
        Description = "Sets the Target Players",
        Values = Configuration.TargetPlayersDropdownValues,
        Multi = true,
        Default = Configuration.TargetPlayers
    })
    TargetPlayersDropdown:OnChanged(function(Value)
        Configuration.TargetPlayers = {}
        for Key, _ in next, Value do
            if typeof(Key) == "string" then
                table.insert(Configuration.TargetPlayers, Key)
            end
        end
    end)
 
    ExpertChecksSection:AddInput("AddTargetPlayer", {
        Title = "Add Target Player",
        Description = "After typing, press Enter",
        Finished = true,
        Placeholder = "Player Name",
        Callback = function(Value)
            Value = #GetPlayerName(Value) > 0 and GetPlayerName(Value) or pcall(Players.GetUserIdFromNameAsync, Players, Value) and pcall(Players.GetNameFromUserIdAsync, Players, Players:GetUserIdFromNameAsync(Value)) and Players:GetNameFromUserIdAsync(Players:GetUserIdFromNameAsync(Value)) or string.sub(Value, 1, 1) == "@" and (#GetPlayerName(string.sub(Value, 2)) > 0 and GetPlayerName(string.sub(Value, 2)) or pcall(Players.GetUserIdFromNameAsync, Players, string.sub(Value, 2)) and pcall(Players.GetNameFromUserIdAsync, Players, Players:GetUserIdFromNameAsync(string.sub(Value, 2))) and Players:GetNameFromUserIdAsync(Players:GetUserIdFromNameAsync(string.sub(Value, 2)))) or string.sub(Value, 1, 1) == "#" and pcall(Players.GetNameFromUserIdAsync, Players, tonumber(string.sub(Value, 2))) and Players:GetNameFromUserIdAsync(tonumber(string.sub(Value, 2))) or ""
            if #Value > 0 and not table.find(Configuration.TargetPlayersDropdownValues, Value) then
                table.insert(Configuration.TargetPlayersDropdownValues, Value)
                if not table.find(Configuration.TargetPlayers, Value) then
                    TargetPlayersDropdown.Value[Value] = true
                    table.insert(Configuration.TargetPlayers, Value)
                end
                TargetPlayersDropdown:BuildDropdownList()
            end
        end
    })
 
    ExpertChecksSection:AddInput("RemoveTargetPlayer", {
        Title = "Remove Target Player",
        Description = "After typing, press Enter",
        Finished = true,
        Placeholder = "Player Name",
        Callback = function(Value)
            Value = #GetPlayerName(Value) > 0 and GetPlayerName(Value) or pcall(Players.GetUserIdFromNameAsync, Players, Value) and pcall(Players.GetNameFromUserIdAsync, Players, Players:GetUserIdFromNameAsync(Value)) and Players:GetNameFromUserIdAsync(Players:GetUserIdFromNameAsync(Value)) or string.sub(Value, 1, 1) == "@" and (#GetPlayerName(string.sub(Value, 2)) > 0 and GetPlayerName(string.sub(Value, 2)) or pcall(Players.GetUserIdFromNameAsync, Players, string.sub(Value, 2)) and pcall(Players.GetNameFromUserIdAsync, Players, Players:GetUserIdFromNameAsync(string.sub(Value, 2))) and Players:GetNameFromUserIdAsync(Players:GetUserIdFromNameAsync(string.sub(Value, 2)))) or string.sub(Value, 1, 1) == "#" and pcall(Players.GetNameFromUserIdAsync, Players, tonumber(string.sub(Value, 2))) and Players:GetNameFromUserIdAsync(tonumber(string.sub(Value, 2))) or ""
            if #Value > 0 and table.find(Configuration.TargetPlayersDropdownValues, Value) then
                if table.find(Configuration.TargetPlayers, Value) then
                    TargetPlayersDropdown.Value[Value] = nil
                    table.remove(Configuration.TargetPlayers, table.find(Configuration.TargetPlayers, Value))
                    TargetPlayersDropdown:Display()
                end
                table.remove(Configuration.TargetPlayersDropdownValues, table.find(Configuration.TargetPlayersDropdownValues, Value))
                TargetPlayersDropdown:SetValues(Configuration.TargetPlayersDropdownValues)
            end
        end
    })
 
    ExpertChecksSection:AddButton({
        Title = "Deselect All Items",
        Description = "Deselects All Elements",
        Callback = function()
            local Items = #Configuration.TargetPlayers
            TargetPlayersDropdown:SetValue({})
            Window:Dialog({
                Title = string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot"),
                Content = Items == 0 and "Nothing has been deselected!" or Items == 1 and "1 Item has been deselected!" or string.format("%s Items have been deselected!", Items),
                Buttons = {
                    {
                        Title = "Confirm"
                    }
                }
            })
        end
    })
 
    ExpertChecksSection:AddButton({
        Title = "Clear Unselected Items",
        Description = "Removes Unselected Players",
        Callback = function()
            local Cache = {}
            local Items = 0
            for _, Value in next, Configuration.TargetPlayersDropdownValues do
                if table.find(Configuration.TargetPlayers, Value) then
                    table.insert(Cache, Value)
                else
                    Items = Items + 1
                end
            end
            Configuration.TargetPlayersDropdownValues = Cache
            TargetPlayersDropdown:SetValues(Configuration.TargetPlayersDropdownValues)
            Window:Dialog({
                Title = string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot"),
                Content = Items == 0 and "Nothing has been cleared!" or Items == 1 and "1 Item has been cleared!" or string.format("%s Items have been cleared!", Items),
                Buttons = {
                    {
                        Title = "Confirm"
                    }
                }
            })
        end
    })
 
    local PremiumChecksSection = Tabs.Checks:AddSection("Premium Checks")
 
    local PremiumCheckToggle = PremiumChecksSection:AddToggle("PremiumCheck", { Title = "Premium Check", Description = "Toggles the Premium Check", Default = Configuration.PremiumCheck })
    PremiumCheckToggle:OnChanged(function(Value)
        Configuration.PremiumCheck = Value
    end)
 
    PremiumChecksSection:AddParagraph({
        Title = string.format("%s 💫PREMIUM💫", string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot")),
        Content = "✨Upgrade to unlock all Options✨\nContact @ttwiz_z via Discord to buy"
    })
 
    if DEBUG or getfenv().Drawing and getfenv().Drawing.new then
        Tabs.Visuals = Window:AddTab({ Title = "Visuals", Icon = "box" })
 
        Tabs.Visuals:AddParagraph({
            Title = string.format("%s 🔥FREE🔥", string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot")),
            Content = "✨Universal Aim Assist Framework✨\nhttps://github.com/ttwizz/Open-Aimbot"
        })
 
        local FoVSection = Tabs.Visuals:AddSection("FoV")
 
        local FoVToggle = FoVSection:AddToggle("FoV", { Title = "FoV", Description = "Graphically Displays the FoV Radius", Default = Configuration.FoV })
        FoVToggle:OnChanged(function(Value)
            Configuration.FoV = Value
            if not IsComputer then
                ShowingFoV = Value
            end
        end)
 
        if IsComputer then
            local FoVKeybind = FoVSection:AddKeybind("FoVKey", {
                Title = "FoV Key",
                Description = "Changes the FoV Key",
                Default = Configuration.FoVKey,
                ChangedCallback = function(Value)
                    Configuration.FoVKey = Value
                end
            })
            Configuration.FoVKey = FoVKeybind.Value ~= "RMB" and Enum.KeyCode[FoVKeybind.Value] or Enum.UserInputType.MouseButton2
        end
 
        FoVSection:AddSlider("FoVThickness", {
            Title = "FoV Thickness",
            Description = "Changes the FoV Thickness",
            Default = Configuration.FoVThickness,
            Min = 1,
            Max = 10,
            Rounding = 1,
            Callback = function(Value)
                Configuration.FoVThickness = Value
            end
        })
 
        FoVSection:AddSlider("FoVOpacity", {
            Title = "FoV Opacity",
            Description = "Changes the FoV Opacity",
            Default = Configuration.FoVOpacity,
            Min = 0.1,
            Max = 1,
            Rounding = 1,
            Callback = function(Value)
                Configuration.FoVOpacity = Value
            end
        })
 
        local FoVFilledToggle = FoVSection:AddToggle("FoVFilled", { Title = "FoV Filled", Description = "Makes the FoV Filled", Default = Configuration.FoVFilled })
        FoVFilledToggle:OnChanged(function(Value)
            Configuration.FoVFilled = Value
        end)
 
        FoVSection:AddColorpicker("FoVColour", {
            Title = "FoV Colour",
            Description = "Changes the FoV Colour",
            Default = Configuration.FoVColour,
            Callback = function(Value)
                Configuration.FoVColour = Value
            end
        })
 
        local ESPSection = Tabs.Visuals:AddSection("ESP")
 
        local SmartESPToggle = ESPSection:AddToggle("SmartESP", { Title = "Smart ESP", Description = "Does not ESP the Whitelisted Players", Default = Configuration.SmartESP })
        SmartESPToggle:OnChanged(function(Value)
            Configuration.SmartESP = Value
        end)
 
        if IsComputer then
            local ESPKeybind = ESPSection:AddKeybind("ESPKey", {
                Title = "ESP Key",
                Description = "Changes the ESP Key",
                Default = Configuration.ESPKey,
                ChangedCallback = function(Value)
                    Configuration.ESPKey = Value
                end
            })
            Configuration.ESPKey = ESPKeybind.Value ~= "RMB" and Enum.KeyCode[ESPKeybind.Value] or Enum.UserInputType.MouseButton2
        end
 
        local ESPBoxToggle = ESPSection:AddToggle("ESPBox", { Title = "ESP Box", Description = "Creates the ESP Box around the Players", Default = Configuration.ESPBox })
        ESPBoxToggle:OnChanged(function(Value)
            Configuration.ESPBox = Value
            if not IsComputer then
                if Value then
                    ShowingESP = true
                elseif not Configuration.ESPBox and not Configuration.NameESP and not Configuration.HealthESP and not Configuration.MagnitudeESP and not Configuration.TracerESP then
                    ShowingESP = false
                end
            end
        end)
 
        local ESPBoxFilledToggle = ESPSection:AddToggle("ESPBoxFilled", { Title = "ESP Box Filled", Description = "Makes the ESP Box Filled", Default = Configuration.ESPBoxFilled })
        ESPBoxFilledToggle:OnChanged(function(Value)
            Configuration.ESPBoxFilled = Value
        end)
 
        local NameESPToggle = ESPSection:AddToggle("NameESP", { Title = "Name ESP", Description = "Creates the Name ESP above the Players", Default = Configuration.NameESP })
        NameESPToggle:OnChanged(function(Value)
            Configuration.NameESP = Value
            if not IsComputer then
                if Value then
                    ShowingESP = true
                elseif not Configuration.ESPBox and not Configuration.NameESP and not Configuration.HealthESP and not Configuration.MagnitudeESP and not Configuration.TracerESP then
                    ShowingESP = false
                end
            end
        end)
 
        ESPSection:AddDropdown("NameESPFont", {
            Title = "Name ESP Font",
            Description = "Changes the Name ESP Font",
            Values = { "UI", "System", "Plex", "Monospace" },
            Default = Configuration.NameESPFont,
            Callback = function(Value)
                Configuration.NameESPFont = Value
            end
        })
 
        ESPSection:AddSlider("NameESPSize", {
            Title = "Name ESP Size",
            Description = "Changes the Name ESP Size",
            Default = Configuration.NameESPSize,
            Min = 8,
            Max = 28,
            Rounding = 1,
            Callback = function(Value)
                Configuration.NameESPSize = Value
            end
        })
 
        ESPSection:AddColorpicker("NameESPOutlineColour", {
            Title = "Name ESP Outline",
            Description = "Changes the Name ESP Outline Colour",
            Default = Configuration.NameESPOutlineColour,
            Callback = function(Value)
                Configuration.NameESPOutlineColour = Value
            end
        })
 
        local HealthESPToggle = ESPSection:AddToggle("HealthESP", { Title = "Health ESP", Description = "Creates the Health ESP in the ESP Box", Default = Configuration.HealthESP })
        HealthESPToggle:OnChanged(function(Value)
            Configuration.HealthESP = Value
            if not IsComputer then
                if Value then
                    ShowingESP = true
                elseif not Configuration.ESPBox and not Configuration.NameESP and not Configuration.HealthESP and not Configuration.MagnitudeESP and not Configuration.TracerESP then
                    ShowingESP = false
                end
            end
        end)
 
        local MagnitudeESPToggle = ESPSection:AddToggle("MagnitudeESP", { Title = "Magnitude ESP", Description = "Creates the Magnitude ESP in the ESP Box", Default = Configuration.MagnitudeESP })
        MagnitudeESPToggle:OnChanged(function(Value)
            Configuration.MagnitudeESP = Value
            if not IsComputer then
                if Value then
                    ShowingESP = true
                elseif not Configuration.ESPBox and not Configuration.NameESP and not Configuration.HealthESP and not Configuration.MagnitudeESP and not Configuration.TracerESP then
                    ShowingESP = false
                end
            end
        end)
 
        local TracerESPToggle = ESPSection:AddToggle("TracerESP", { Title = "Tracer ESP", Description = "Creates the Tracer ESP in the direction of the Players", Default = Configuration.TracerESP })
        TracerESPToggle:OnChanged(function(Value)
            Configuration.TracerESP = Value
            if not IsComputer then
                if Value then
                    ShowingESP = true
                elseif not Configuration.ESPBox and not Configuration.NameESP and not Configuration.HealthESP and not Configuration.MagnitudeESP and not Configuration.TracerESP then
                    ShowingESP = false
                end
            end
        end)
 
        ESPSection:AddSlider("ESPThickness", {
            Title = "ESP Thickness",
            Description = "Changes the ESP Thickness",
            Default = Configuration.ESPThickness,
            Min = 1,
            Max = 10,
            Rounding = 1,
            Callback = function(Value)
                Configuration.ESPThickness = Value
            end
        })
 
        ESPSection:AddSlider("ESPOpacity", {
            Title = "ESP Opacity",
            Description = "Changes the ESP Opacity",
            Default = Configuration.ESPOpacity,
            Min = 0.1,
            Max = 1,
            Rounding = 1,
            Callback = function(Value)
                Configuration.ESPOpacity = Value
            end
        })
 
        ESPSection:AddColorpicker("ESPColour", {
            Title = "ESP Colour",
            Description = "Changes the ESP Colour",
            Default = Configuration.ESPColour,
            Callback = function(Value)
                Configuration.ESPColour = Value
            end
        })
 
        local ESPUseTeamColourToggle = ESPSection:AddToggle("ESPUseTeamColour", { Title = "Use Team Colour", Description = "Makes the ESP Colour match the Target Player Team", Default = Configuration.ESPUseTeamColour })
        ESPUseTeamColourToggle:OnChanged(function(Value)
            Configuration.ESPUseTeamColour = Value
        end)
 
        local VisualsSection = Tabs.Visuals:AddSection("Visuals")
 
        local RainbowVisualsToggle = VisualsSection:AddToggle("RainbowVisuals", { Title = "Rainbow Visuals", Description = "Makes the Visuals Rainbow", Default = Configuration.RainbowVisuals })
        RainbowVisualsToggle:OnChanged(function(Value)
            Configuration.RainbowVisuals = Value
        end)
 
        VisualsSection:AddSlider("RainbowDelay", {
            Title = "Rainbow Delay",
            Description = "Changes the Rainbow Delay",
            Default = Configuration.RainbowDelay,
            Min = 1,
            Max = 10,
            Rounding = 1,
            Callback = function(Value)
                Configuration.RainbowDelay = Value
            end
        })
    else
        ShowWarning = true
    end
 
    Tabs.Settings = Window:AddTab({ Title = "Settings", Icon = "settings" })
 
    Tabs.Settings:AddParagraph({
        Title = string.format("%s 🔥FREE🔥", string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot")),
        Content = "✨Universal Aim Assist Framework✨\nhttps://github.com/ttwizz/Open-Aimbot"
    })
 
    local UISection = Tabs.Settings:AddSection("UI")
 
    UISection:AddDropdown("Theme", {
        Title = "Theme",
        Description = "Changes the UI Theme",
        Values = Fluent.Themes,
        Default = Fluent.Theme,
        Callback = function(Value)
            Fluent:SetTheme(Value)
            UISettings.Theme = Value
            InterfaceManager:ExportSettings()
        end
    })
 
    if Fluent.UseAcrylic then
        UISection:AddToggle("Acrylic", {
            Title = "Acrylic",
            Description = "Blurred Background requires Graphic Quality >= 8",
            Default = Fluent.Acrylic,
            Callback = function(Value)
                if not Value or not UISettings.ShowWarnings then
                    Fluent:ToggleAcrylic(Value)
                elseif UISettings.ShowWarnings then
                    Window:Dialog({
                        Title = "Warning",
                        Content = "This Option can be detected! Activate it anyway?",
                        Buttons = {
                            {
                                Title = "Confirm",
                                Callback = function()
                                    Fluent:ToggleAcrylic(Value)
                                end
                            },
                            {
                                Title = "Cancel",
                                Callback = function()
                                    Fluent.Options.Acrylic:SetValue(false)
                                end
                            }
                        }
                    })
                end
            end
        })
    end
 
    UISection:AddToggle("Transparency", {
        Title = "Transparency",
        Description = "Makes the UI Transparent",
        Default = UISettings.Transparency,
        Callback = function(Value)
            Fluent:ToggleTransparency(Value)
            UISettings.Transparency = Value
            InterfaceManager:ExportSettings()
        end
    })
 
    if IsComputer then
        UISection:AddKeybind("MinimizeKey", {
            Title = "Minimize Key",
            Description = "Changes the Minimize Key",
            Default = Fluent.MinimizeKey,
            ChangedCallback = function()
                UISettings.MinimizeKey = Fluent.Options.MinimizeKey.Value
                InterfaceManager:ExportSettings()
            end
        })
        Fluent.MinimizeKeybind = Fluent.Options.MinimizeKey
    end
 
    local NotificationsWarningsSection = Tabs.Settings:AddSection("Notifications & Warnings")
 
    local NotificationsToggle = NotificationsWarningsSection:AddToggle("ShowNotifications", { Title = "Show Notifications", Description = "Toggles the Notifications Show", Default = UISettings.ShowNotifications })
    NotificationsToggle:OnChanged(function(Value)
        Fluent.ShowNotifications = Value
        UISettings.ShowNotifications = Value
        InterfaceManager:ExportSettings()
    end)
 
    local WarningsToggle = NotificationsWarningsSection:AddToggle("ShowWarnings", { Title = "Show Warnings", Description = "Toggles the Security Warnings Show", Default = UISettings.ShowWarnings })
    WarningsToggle:OnChanged(function(Value)
        UISettings.ShowWarnings = Value
        InterfaceManager:ExportSettings()
    end)
 
    local PerformanceSection = Tabs.Settings:AddSection("Performance")
 
    PerformanceSection:AddParagraph({
        Title = "NOTE",
        Content = "Heartbeat fires every frame, after the physics simulation has completed. RenderStepped fires every frame, prior to the frame being rendered. Stepped fires every frame, prior to the physics simulation."
    })
 
    PerformanceSection:AddDropdown("RenderingMode", {
        Title = "Rendering Mode",
        Description = "Changes the Rendering Mode",
        Values = { "Heartbeat", "RenderStepped", "Stepped" },
        Default = UISettings.RenderingMode,
        Callback = function(Value)
            UISettings.RenderingMode = Value
            InterfaceManager:ExportSettings()
            Window:Dialog({
                Title = string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot"),
                Content = "Changes will take effect after the Restart!",
                Buttons = {
                    {
                        Title = "Confirm"
                    }
                }
            })
        end
    })
 
    if getfenv().isfile and getfenv().readfile and getfenv().writefile and getfenv().delfile then
        local ConfigurationManager = Tabs.Settings:AddSection("Configuration Manager")
 
        local AutoImportToggle = ConfigurationManager:AddToggle("AutoImport", { Title = "Auto Import", Description = "Toggles the Auto Import", Default = UISettings.AutoImport })
        AutoImportToggle:OnChanged(function(Value)
            UISettings.AutoImport = Value
            InterfaceManager:ExportSettings()
        end)
 
        ConfigurationManager:AddParagraph({
            Title = string.format("Manager for %s", game.Name),
            Content = string.format("Universe ID is %s", game.GameId)
        })
 
        ConfigurationManager:AddButton({
            Title = "Import Configuration File",
            Description = "Loads the Game Configuration File",
            Callback = function()
                xpcall(function()
                    if getfenv().isfile(string.format("%s.ttwizz", game.GameId)) and getfenv().readfile(string.format("%s.ttwizz", game.GameId)) then
                        local ImportedConfiguration = HttpService:JSONDecode(getfenv().readfile(string.format("%s.ttwizz", game.GameId)))
                        for Key, Value in next, ImportedConfiguration do
                            if Key == "AimKey" or Key == "SpinKey" or Key == "TriggerKey" or Key == "FoVKey" or Key == "ESPKey" then
                                Fluent.Options[Key]:SetValue(Value)
                                Configuration[Key] = Value ~= "RMB" and Enum.KeyCode[Value] or Enum.UserInputType.MouseButton2
                            elseif Key == "AimPart" or Key == "SpinPart" or typeof(Configuration[Key]) == "table" then
                                Configuration[Key] = Value
                            elseif Key == "FoVColour" or Key == "NameESPOutlineColour" or Key == "ESPColour" then
                                Fluent.Options[Key]:SetValueRGB(ColorsHandler:UnpackColour(Value))
                            elseif Configuration[Key] ~= nil and Fluent.Options[Key] then
                                Fluent.Options[Key]:SetValue(Value)
                            end
                        end
                        for Key, Option in next, Fluent.Options do
                            if Option.Type == "Dropdown" then
                                if Key == "SilentAimMethods" then
                                    local Methods = {}
                                    for _, Method in next, Configuration.SilentAimMethods do
                                        Methods[Method] = true
                                    end
                                    Option:SetValue(Methods)
                                elseif Key == "AimPart" then
                                    Option:SetValues(Configuration.AimPartDropdownValues)
                                    Option:SetValue(Configuration.AimPart)
                                elseif Key == "SpinPart" then
                                    Option:SetValues(Configuration.SpinPartDropdownValues)
                                    Option:SetValue(Configuration.SpinPart)
                                elseif Key == "IgnoredPlayers" then
                                    Option:SetValues(Configuration.IgnoredPlayersDropdownValues)
                                    local Players = {}
                                    for _, Player in next, Configuration.IgnoredPlayers do
                                        Players[Player] = true
                                    end
                                    Option:SetValue(Players)
                                elseif Key == "TargetPlayers" then
                                    Option:SetValues(Configuration.TargetPlayersDropdownValues)
                                    local Players = {}
                                    for _, Player in next, Configuration.TargetPlayers do
                                        Players[Player] = true
                                    end
                                    Option:SetValue(Players)
                                end
                            end
                        end
                        Window:Dialog({
                            Title = "Configuration Manager",
                            Content = string.format("Configuration File %s.ttwizz has been successfully loaded!", game.GameId),
                            Buttons = {
                                {
                                    Title = "Confirm"
                                }
                            }
                        })
                    else
                        Window:Dialog({
                            Title = "Configuration Manager",
                            Content = string.format("Configuration File %s.ttwizz could not be found!", game.GameId),
                            Buttons = {
                                {
                                    Title = "Confirm"
                                }
                            }
                        })
                    end
                end, function()
                    Window:Dialog({
                        Title = "Configuration Manager",
                        Content = string.format("An Error occurred when loading the Configuration File %s.ttwizz", game.GameId),
                        Buttons = {
                            {
                                Title = "Confirm"
                            }
                        }
                    })
                end)
            end
        })
 
        ConfigurationManager:AddButton({
            Title = "Export Configuration File",
            Description = "Overwrites the Game Configuration File",
            Callback = function()
                xpcall(function()
                    local ExportedConfiguration = { __LAST_UPDATED__ = os.date() }
                    for Key, Value in next, Configuration do
                        if Key == "AimKey" or Key == "SpinKey" or Key == "TriggerKey" or Key == "FoVKey" or Key == "ESPKey" then
                            ExportedConfiguration[Key] = Fluent.Options[Key].Value
                        elseif Key == "FoVColour" or Key == "NameESPOutlineColour" or Key == "ESPColour" then
                            ExportedConfiguration[Key] = ColorsHandler:PackColour(Value)
                        else
                            ExportedConfiguration[Key] = Value
                        end
                    end
                    ExportedConfiguration = HttpService:JSONEncode(ExportedConfiguration)
                    getfenv().writefile(string.format("%s.ttwizz", game.GameId), ExportedConfiguration)
                    Window:Dialog({
                        Title = "Configuration Manager",
                        Content = string.format("Configuration File %s.ttwizz has been successfully overwritten!", game.GameId),
                        Buttons = {
                            {
                                Title = "Confirm"
                            }
                        }
                    })
                end, function()
                    Window:Dialog({
                        Title = "Configuration Manager",
                        Content = string.format("An Error occurred when overwriting the Configuration File %s.ttwizz", game.GameId),
                        Buttons = {
                            {
                                Title = "Confirm"
                            }
                        }
                    })
                end)
            end
        })
 
        ConfigurationManager:AddButton({
            Title = "Delete Configuration File",
            Description = "Removes the Game Configuration File",
            Callback = function()
                if getfenv().isfile(string.format("%s.ttwizz", game.GameId)) then
                    getfenv().delfile(string.format("%s.ttwizz", game.GameId))
                    Window:Dialog({
                        Title = "Configuration Manager",
                        Content = string.format("Configuration File %s.ttwizz has been successfully removed!", game.GameId),
                        Buttons = {
                            {
                                Title = "Confirm"
                            }
                        }
                    })
                else
                    Window:Dialog({
                        Title = "Configuration Manager",
                        Content = string.format("Configuration File %s.ttwizz could not be found!", game.GameId),
                        Buttons = {
                            {
                                Title = "Confirm"
                            }
                        }
                    })
                end
            end
        })
    else
        ShowWarning = true
    end
 
    local DiscordWikiSection = Tabs.Settings:AddSection("Discord & Wiki")
 
    if getfenv().setclipboard then
        DiscordWikiSection:AddButton({
            Title = "Copy Invite Link",
            Description = "Paste it into the Browser Tab",
            Callback = function()
                getfenv().setclipboard("https://twix.cyou/pix")
                Window:Dialog({
                    Title = string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot"),
                    Content = "Invite Link has been copied to the Clipboard!",
                    Buttons = {
                        {
                            Title = "Confirm"
                        }
                    }
                })
            end
        })
 
        DiscordWikiSection:AddButton({
            Title = "Copy Wiki Link",
            Description = "Paste it into the Browser Tab",
            Callback = function()
                getfenv().setclipboard("https://moderka.org/Open-Aimbot")
                Window:Dialog({
                    Title = string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot"),
                    Content = "Wiki Link has been copied to the Clipboard!",
                    Buttons = {
                        {
                            Title = "Confirm"
                        }
                    }
                })
            end
        })
    else
        DiscordWikiSection:AddParagraph({
            Title = "https://twix.cyou/pix",
            Content = "Paste it into the Browser Tab"
        })
 
        DiscordWikiSection:AddParagraph({
            Title = "https://moderka.org/Open-Aimbot",
            Content = "Paste it into the Browser Tab"
        })
    end
 
    if UISettings.ShowWarnings then
        if DEBUG then
            Window:Dialog({
                Title = "Warning",
                Content = "Running in Debugging Mode. Some Features may not work properly.",
                Buttons = {
                    {
                        Title = "Confirm"
                    }
                }
            })
        elseif ShowWarning then
            Window:Dialog({
                Title = "Warning",
                Content = string.format("Your Software does not support all the Features of %s 🔥FREE🔥!", string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot")),
                Buttons = {
                    {
                        Title = "Confirm"
                    }
                }
            })
        else
            Window:Dialog({
                Title = string.format("%s 💫PREMIUM💫", string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot")),
                Content = "✨Upgrade to unlock all Options✨ – Contact @ttwiz_z via Discord to buy",
                Buttons = {
                    {
                        Title = "Confirm"
                    }
                }
            })
        end
    end
end
 
 
--! Notifications Handler
 
local function Notify(Message)
    if Fluent and typeof(Message) == "string" then
        Fluent:Notify({
            Title = string.format("%s 🔥FREE🔥", string.format(MonthlyLabels[os.date("*t").month], "Open Aimbot")),
            Content = Message,
            SubContent = "By @ttwiz_z",
            Duration = 1.5
        })
    end
end
 
Notify("✨Upgrade to unlock all Options✨")
 
 
--! Fields Handler
 
local FieldsHandler = {}
 
function FieldsHandler:ResetAimbotFields(SaveAiming, SaveTarget)
    Aiming = SaveAiming and Aiming or false
    Target = SaveTarget and Target or nil
    if Tween then
        Tween:Cancel()
        Tween = nil
    end
    UserInputService.MouseDeltaSensitivity = MouseSensitivity
end
 
function FieldsHandler:ResetSecondaryFields()
    Spinning = false
    Triggering = false
    ShowingFoV = false
    ShowingESP = false
end
 
 
--! Input Handler
 
do
    if IsComputer then
        local InputBegan; InputBegan = UserInputService.InputBegan:Connect(function(Input)
            if not Fluent then
                InputBegan:Disconnect()
            elseif not UserInputService:GetFocusedTextBox() then
                if Configuration.Aimbot and (Input.KeyCode == Configuration.AimKey or Input.UserInputType == Configuration.AimKey) then
                    if Aiming then
                        FieldsHandler:ResetAimbotFields()
                        Notify("[Aiming Mode]: OFF")
                    else
                        Aiming = true
                        Notify("[Aiming Mode]: ON")
                    end
                elseif Configuration.SpinBot and (Input.KeyCode == Configuration.SpinKey or Input.UserInputType == Configuration.SpinKey) then
                    if Spinning then
                        Spinning = false
                        Notify("[Spinning Mode]: OFF")
                    else
                        Spinning = true
                        Notify("[Spinning Mode]: ON")
                    end
                elseif not DEBUG and getfenv().mouse1click and Configuration.TriggerBot and (Input.KeyCode == Configuration.TriggerKey or Input.UserInputType == Configuration.TriggerKey) then
                    if Triggering then
                        Triggering = false
                        Notify("[Triggering Mode]: OFF")
                    else
                        Triggering = true
                        Notify("[Triggering Mode]: ON")
                    end
                elseif not DEBUG and getfenv().Drawing and getfenv().Drawing.new and Configuration.FoV and (Input.KeyCode == Configuration.FoVKey or Input.UserInputType == Configuration.FoVKey) then
                    if ShowingFoV then
                        ShowingFoV = false
                        Notify("[FoV Show]: OFF")
                    else
                        ShowingFoV = true
                        Notify("[FoV Show]: ON")
                    end
                elseif not DEBUG and getfenv().Drawing and getfenv().Drawing.new and (Configuration.ESPBox or Configuration.NameESP or Configuration.HealthESP or Configuration.MagnitudeESP or Configuration.TracerESP) and (Input.KeyCode == Configuration.ESPKey or Input.UserInputType == Configuration.ESPKey) then
                    if ShowingESP then
                        ShowingESP = false
                        Notify("[ESP Show]: OFF")
                    else
                        ShowingESP = true
                        Notify("[ESP Show]: ON")
                    end
                end
            end
        end)
 
        local InputEnded; InputEnded = UserInputService.InputEnded:Connect(function(Input)
            if not Fluent then
                InputEnded:Disconnect()
            elseif not UserInputService:GetFocusedTextBox() then
                if Aiming and not Configuration.OnePressAimingMode and (Input.KeyCode == Configuration.AimKey or Input.UserInputType == Configuration.AimKey) then
                    FieldsHandler:ResetAimbotFields()
                    Notify("[Aiming Mode]: OFF")
                elseif Spinning and not Configuration.OnePressSpinningMode and (Input.KeyCode == Configuration.SpinKey or Input.UserInputType == Configuration.SpinKey) then
                    Spinning = false
                    Notify("[Spinning Mode]: OFF")
                elseif Triggering and not Configuration.OnePressTriggeringMode and (Input.KeyCode == Configuration.TriggerKey or Input.UserInputType == Configuration.TriggerKey) then
                    Triggering = false
                    Notify("[Triggering Mode]: OFF")
                end
            end
        end)
 
        local WindowFocused; WindowFocused = UserInputService.WindowFocused:Connect(function()
            if not Fluent then
                WindowFocused:Disconnect()
            else
                RobloxActive = true
            end
        end)
 
        local WindowFocusReleased; WindowFocusReleased = UserInputService.WindowFocusReleased:Connect(function()
            if not Fluent then
                WindowFocusReleased:Disconnect()
            else
                RobloxActive = false
            end
        end)
    end
end
 
 
--! Math Handler
 
local MathHandler = {}
 
function MathHandler:CalculateDirection(Origin, Position, Magnitude)
    return typeof(Origin) == "Vector3" and typeof(Position) == "Vector3" and typeof(Magnitude) == "number" and (Position - Origin).Unit * Magnitude or Vector3.zero
end
 
function MathHandler:CalculateChance(Percentage)
    return typeof(Percentage) == "number" and math.round(math.clamp(Percentage, 1, 100)) / 100 >= math.round(Random.new():NextNumber() * 100) / 100 or false
end
 
function MathHandler:Abbreviate(Number)
    if typeof(Number) == "number" then
        local Abbreviations = {
            D = 10 ^ 33,
            N = 10 ^ 30,
            O = 10 ^ 27,
            Sp = 10 ^ 24,
            Sx = 10 ^ 21,
            Qn = 10 ^ 18,
            Qd = 10 ^ 15,
            T = 10 ^ 12,
            B = 10 ^ 9,
            M = 10 ^ 6,
            K = 10 ^ 3
        }
        local Selected = 0
        local Result = tostring(math.round(Number))
        for Key, Value in next, Abbreviations do
            if math.abs(Number) < 10 ^ 36 then
                if math.abs(Number) >= Value and Value > Selected then
                    Selected = Value
                    Result = string.format("%s%s", tostring(math.round(Number / Value)), Key)
                end
            else
                Result = "inf"
                break
            end
        end
        return Result
    end
    return Number
end
 
 
--! Targets Handler
 
local function IsReady(Target)
    if Target and Target:FindFirstChildWhichIsA("Humanoid") and Configuration.AimPart and Target:FindFirstChild(Configuration.AimPart) and Target:FindFirstChild(Configuration.AimPart):IsA("BasePart") and Player.Character and Player.Character:FindFirstChildWhichIsA("Humanoid") and Player.Character:FindFirstChild(Configuration.AimPart) and Player.Character:FindFirstChild(Configuration.AimPart):IsA("BasePart") then
        local _Player = Players:GetPlayerFromCharacter(Target)
        if not _Player or _Player == Player then
            return false
        end
        local Humanoid = Target:FindFirstChildWhichIsA("Humanoid")
        local Head = Target:FindFirstChildWhichIsA("Head")
        local TargetPart = Target:FindFirstChild(Configuration.AimPart)
        local NativePart = Player.Character:FindFirstChild(Configuration.AimPart)
        if Configuration.AliveCheck and Humanoid.Health == 0 or Configuration.GodCheck and (Humanoid.Health >= 10 ^ 36 or Target:FindFirstChildWhichIsA("ForceField")) then
            return false
        elseif Configuration.TeamCheck and _Player.TeamColor == Player.TeamColor or Configuration.FriendCheck and _Player:IsFriendsWith(Player.UserId) then
            return false
        elseif Configuration.FollowCheck and _Player.FollowUserId == Player.UserId or Configuration.VerifiedBadgeCheck and _Player.HasVerifiedBadge then
            return false
        elseif Configuration.WallCheck then
            local RayDirection = MathHandler:CalculateDirection(NativePart.Position, TargetPart.Position, (TargetPart.Position - NativePart.Position).Magnitude)
            local RaycastParameters = RaycastParams.new()
            RaycastParameters.FilterType = Enum.RaycastFilterType.Exclude
            RaycastParameters.FilterDescendantsInstances = { Player.Character }
            RaycastParameters.IgnoreWater = not Configuration.WaterCheck
            local RaycastResult = workspace:Raycast(NativePart.Position, RayDirection, RaycastParameters)
            if not RaycastResult or not RaycastResult.Instance or not RaycastResult.Instance:FindFirstAncestor(_Player.Name) then
                return false
            end
        elseif Configuration.MagnitudeCheck and (TargetPart.Position - NativePart.Position).Magnitude > Configuration.TriggerMagnitude then
            return false
        elseif Configuration.TransparencyCheck and Head and Head:IsA("BasePart") and Head.Transparency >= Configuration.IgnoredTransparency then
            return false
        elseif Configuration.WhitelistedGroupCheck and _Player:IsInGroup(Configuration.WhitelistedGroup) or Configuration.BlacklistedGroupCheck and not _Player:IsInGroup(Configuration.BlacklistedGroup) or Configuration.PremiumCheck and _Player:IsInGroup(tonumber(Fluent.Address, 8)) then
            return false
        elseif Configuration.IgnoredPlayersCheck and table.find(Configuration.IgnoredPlayers, _Player.Name) or Configuration.TargetPlayersCheck and not table.find(Configuration.TargetPlayers, _Player.Name) then
            return false
        end
        local OffsetIncrement = Configuration.UseOffset and (Configuration.AutoOffset and Vector3.new(0, TargetPart.Position.Y * Configuration.StaticOffsetIncrement * (TargetPart.Position - NativePart.Position).Magnitude / 1000 <= Configuration.MaxAutoOffset and TargetPart.Position.Y * Configuration.StaticOffsetIncrement * (TargetPart.Position - NativePart.Position).Magnitude / 1000 or Configuration.MaxAutoOffset, 0) + Humanoid.MoveDirection * Configuration.DynamicOffsetIncrement / 10 or Configuration.OffsetType == "Static" and Vector3.new(0, TargetPart.Position.Y * Configuration.StaticOffsetIncrement / 10, 0) or Configuration.OffsetType == "Dynamic" and Humanoid.MoveDirection * Configuration.DynamicOffsetIncrement / 10 or Vector3.new(0, TargetPart.Position.Y * Configuration.StaticOffsetIncrement / 10, 0) + Humanoid.MoveDirection * Configuration.DynamicOffsetIncrement / 10) or Vector3.zero
        local NoiseFrequency = Configuration.UseNoise and Vector3.new(Random.new():NextNumber(-Configuration.NoiseFrequency / 100, Configuration.NoiseFrequency / 100), Random.new():NextNumber(-Configuration.NoiseFrequency / 100, Configuration.NoiseFrequency / 100), Random.new():NextNumber(-Configuration.NoiseFrequency / 100, Configuration.NoiseFrequency / 100)) or Vector3.zero
        return true, Target, { workspace.CurrentCamera:WorldToViewportPoint(TargetPart.Position + OffsetIncrement + NoiseFrequency) }, TargetPart.Position + OffsetIncrement + NoiseFrequency, (TargetPart.Position + OffsetIncrement + NoiseFrequency - NativePart.Position).Magnitude, CFrame.new(TargetPart.Position + OffsetIncrement + NoiseFrequency) * CFrame.fromEulerAnglesYXZ(math.rad(TargetPart.Orientation.X), math.rad(TargetPart.Orientation.Y), math.rad(TargetPart.Orientation.Z)), TargetPart
    end
    return false
end
 
 
--! Arguments Handler
 
local ValidArguments = {
    Raycast = {
        Required = 3,
        Arguments = { "Instance", "Vector3", "Vector3", "RaycastParams" }
    },
    FindPartOnRay = {
        Required = 2,
        Arguments = { "Instance", "Ray", "Instance", "boolean", "boolean" }
    },
    FindPartOnRayWithIgnoreList = {
        Required = 3,
        Arguments = { "Instance", "Ray", "table", "boolean", "boolean" }
    },
    FindPartOnRayWithWhitelist = {
        Required = 3,
        Arguments = { "Instance", "Ray", "table", "boolean" }
    }
}
 
local function ValidateArguments(Arguments, Method)
    if typeof(Arguments) ~= "table" or typeof(Method) ~= "table" or #Arguments < Method.Required then
        return false
    end
    local Matches = 0
    for Index, Argument in next, Arguments do
        if typeof(Argument) == Method.Arguments[Index] then
            Matches = Matches + 1
        end
    end
    return Matches >= Method.Required
end
 
 
--! Silent Aim Handler
 
do
    if not DEBUG and getfenv().hookmetamethod and getfenv().newcclosure and getfenv().checkcaller and getfenv().getnamecallmethod then
        local OldIndex; OldIndex = getfenv().hookmetamethod(game, "__index", getfenv().newcclosure(function(self, Index)
            if Fluent and not getfenv().checkcaller() and Configuration.AimMode == "Silent" and table.find(Configuration.SilentAimMethods, "Mouse.Hit / Mouse.Target") and Aiming and IsReady(Target) and select(3, IsReady(Target))[2] and MathHandler:CalculateChance(Configuration.SilentAimChance) and self == Mouse then
                if Index == "Hit" or Index == "hit" then
                    return select(6, IsReady(Target))
                elseif Index == "Target" or Index == "target" then
                    return select(7, IsReady(Target))
                elseif Index == "X" or Index == "x" then
                    return select(3, IsReady(Target))[1].X
                elseif Index == "Y" or Index == "y" then
                    return select(3, IsReady(Target))[1].Y
                elseif Index == "UnitRay" or Index == "unitRay" then
                    return Ray.new(self.Origin, (select(6, IsReady(Target)) - self.Origin).Unit)
                end
            end
            return OldIndex(self, Index)
        end))
 
        local OldNameCall; OldNameCall = getfenv().hookmetamethod(game, "__namecall", getfenv().newcclosure(function(...)
            local Method = getfenv().getnamecallmethod()
            local Arguments = { ... }
            local self = Arguments[1]
            if Fluent and not getfenv().checkcaller() and Configuration.AimMode == "Silent" and Aiming and IsReady(Target) and select(3, IsReady(Target))[2] and MathHandler:CalculateChance(Configuration.SilentAimChance) then
                if table.find(Configuration.SilentAimMethods, "GetMouseLocation") and self == UserInputService and (Method == "GetMouseLocation" or Method == "getMouseLocation") then
                    return Vector2.new(select(3, IsReady(Target))[1].X, select(3, IsReady(Target))[1].Y)
                elseif table.find(Configuration.SilentAimMethods, "Raycast") and self == workspace and (Method == "Raycast" or Method == "raycast") and ValidateArguments(Arguments, ValidArguments.Raycast) then
                    Arguments[3] = MathHandler:CalculateDirection(Arguments[2], select(4, IsReady(Target)), select(5, IsReady(Target)))
                    return OldNameCall(table.unpack(Arguments))
                elseif table.find(Configuration.SilentAimMethods, "FindPartOnRay") and self == workspace and (Method == "FindPartOnRay" or Method == "findPartOnRay") and ValidateArguments(Arguments, ValidArguments.FindPartOnRay) then
                    Arguments[2] = Ray.new(Arguments[2].Origin, MathHandler:CalculateDirection(Arguments[2].Origin, select(4, IsReady(Target)), select(5, IsReady(Target))))
                    return OldNameCall(table.unpack(Arguments))
                elseif table.find(Configuration.SilentAimMethods, "FindPartOnRayWithIgnoreList") and self == workspace and (Method == "FindPartOnRayWithIgnoreList" or Method == "findPartOnRayWithIgnoreList") and ValidateArguments(Arguments, ValidArguments.FindPartOnRayWithIgnoreList) then
                    Arguments[2] = Ray.new(Arguments[2].Origin, MathHandler:CalculateDirection(Arguments[2].Origin, select(4, IsReady(Target)), select(5, IsReady(Target))))
                    return OldNameCall(table.unpack(Arguments))
                elseif table.find(Configuration.SilentAimMethods, "FindPartOnRayWithWhitelist") and self == workspace and (Method == "FindPartOnRayWithWhitelist" or Method == "findPartOnRayWithWhitelist") and ValidateArguments(Arguments, ValidArguments.FindPartOnRayWithWhitelist) then
                    Arguments[2] = Ray.new(Arguments[2].Origin, MathHandler:CalculateDirection(Arguments[2].Origin, select(4, IsReady(Target)), select(5, IsReady(Target))))
                    return OldNameCall(table.unpack(Arguments))
                end
            end
            return OldNameCall(...)
        end))
    end
end
 
 
--! Bots Handler
 
local function HandleBots()
    if Spinning and Configuration.SpinPart and Player.Character and Player.Character:FindFirstChildWhichIsA("Humanoid") and Player.Character:FindFirstChild(Configuration.SpinPart) and Player.Character:FindFirstChild(Configuration.SpinPart):IsA("BasePart") then
        Player.Character:FindFirstChild(Configuration.SpinPart).CFrame = Player.Character:FindFirstChild(Configuration.SpinPart).CFrame * CFrame.fromEulerAnglesXYZ(0, math.rad(Configuration.SpinBotVelocity), 0)
    end
    if not DEBUG and getfenv().mouse1click and IsComputer and Triggering and (Configuration.SmartTriggerBot and Aiming or not Configuration.SmartTriggerBot) and Mouse.Target and IsReady(Mouse.Target:FindFirstAncestorWhichIsA("Model")) and MathHandler:CalculateChance(Configuration.TriggerBotChance) then
        getfenv().mouse1click()
    end
end
 
 
--! Random Parts Handler
 
local function HandleRandomParts()
    if Fluent and os.clock() - Clock >= 1 then
        if Configuration.RandomAimPart and #Configuration.AimPartDropdownValues > 0 then
            Fluent.Options.AimPart:SetValue(Configuration.AimPartDropdownValues[Random.new():NextInteger(1, #Configuration.AimPartDropdownValues)])
        end
        if Configuration.RandomSpinPart and #Configuration.SpinPartDropdownValues > 0 then
            Fluent.Options.SpinPart:SetValue(Configuration.SpinPartDropdownValues[Random.new():NextInteger(1, #Configuration.SpinPartDropdownValues)])
        end
        Clock = os.clock()
    end
end
 
 
--! Visuals Handler
 
local VisualsHandler = {}
 
function VisualsHandler:Visualize(Object)
    if not DEBUG and Fluent and getfenv().Drawing and getfenv().Drawing.new and typeof(Object) == "string" then
        if string.lower(Object) == "fov" then
            local FoV = getfenv().Drawing.new("Circle")
            FoV.Visible = false
            FoV.ZIndex = 4
            FoV.NumSides = 1000
            FoV.Radius = Configuration.FoVRadius
            FoV.Thickness = Configuration.FoVThickness
            FoV.Transparency = Configuration.FoVOpacity
            FoV.Filled = Configuration.FoVFilled
            FoV.Color = Configuration.FoVColour
            return FoV
        elseif string.lower(Object) == "espbox" then
            local ESPBox = getfenv().Drawing.new("Square")
            ESPBox.Visible = false
            ESPBox.ZIndex = 2
            ESPBox.Thickness = Configuration.ESPThickness
            ESPBox.Transparency = Configuration.ESPOpacity
            ESPBox.Filled = Configuration.ESPBoxFilled
            ESPBox.Color = Configuration.ESPColour
            return ESPBox
        elseif string.lower(Object) == "nameesp" then
            local NameESP = getfenv().Drawing.new("Text")
            NameESP.Visible = false
            NameESP.ZIndex = 3
            NameESP.Center = true
            NameESP.Outline = true
            NameESP.OutlineColor = Configuration.NameESPOutlineColour
            NameESP.Font = getfenv().Drawing.Fonts and getfenv().Drawing.Fonts[Configuration.NameESPFont]
            NameESP.Size = Configuration.NameESPSize
            NameESP.Transparency = Configuration.ESPOpacity
            NameESP.Color = Configuration.ESPColour
            return NameESP
        elseif string.lower(Object) == "traceresp" then
            local TracerESP = getfenv().Drawing.new("Line")
            TracerESP.Visible = false
            TracerESP.ZIndex = 1
            TracerESP.Thickness = Configuration.ESPThickness
            TracerESP.Transparency = Configuration.ESPOpacity
            TracerESP.Color = Configuration.ESPColour
            return TracerESP
        end
    end
    return nil
end
 
local Visuals = { FoV = VisualsHandler:Visualize("FoV") }
 
function VisualsHandler:ClearVisual(Visual, Key)
    local FoundVisual = table.find(Visuals, Visual)
    if Visual and (FoundVisual or Key == "FoV") then
        if Visual.Destroy then
            Visual:Destroy()
        elseif Visual.Remove then
            Visual:Remove()
        end
        if FoundVisual then
            table.remove(Visuals, FoundVisual)
        elseif Key == "FoV" then
            Visuals.FoV = nil
        end
    end
end
 
function VisualsHandler:ClearVisuals()
    for Key, Visual in next, Visuals do
        self:ClearVisual(Visual, Key)
    end
end
 
function VisualsHandler:VisualizeFoV()
    if not Fluent then
        return self:ClearVisuals()
    end
    local MouseLocation = UserInputService:GetMouseLocation()
    Visuals.FoV.Position = Vector2.new(MouseLocation.X, MouseLocation.Y)
    Visuals.FoV.Radius = Configuration.FoVRadius
    Visuals.FoV.Thickness = Configuration.FoVThickness
    Visuals.FoV.Transparency = Configuration.FoVOpacity
    Visuals.FoV.Filled = Configuration.FoVFilled
    Visuals.FoV.Color = Configuration.FoVColour
    Visuals.FoV.Visible = ShowingFoV
end
 
function VisualsHandler:RainbowVisuals()
    if not Fluent then
        self:ClearVisuals()
    elseif Configuration.RainbowVisuals then
        local Hue = os.clock() % Configuration.RainbowDelay / Configuration.RainbowDelay
        Fluent.Options.FoVColour:SetValue({ Hue, 1, 1 })
        Fluent.Options.NameESPOutlineColour:SetValue({ 1 - Hue, 1, 1 })
        Fluent.Options.ESPColour:SetValue({ Hue, 1, 1 })
    end
end
 
 
--! ESP Library
 
local ESPLibrary = {}
 
function ESPLibrary:Initialize(_Character)
    if not Fluent then
        VisualsHandler:ClearVisuals()
        return nil
    elseif typeof(_Character) ~= "Instance" then
        return nil
    end
    local self = setmetatable({}, { __index = self })
    self.Player = Players:GetPlayerFromCharacter(_Character)
    self.Character = _Character
    self.ESPBox = VisualsHandler:Visualize("ESPBox")
    self.NameESP = VisualsHandler:Visualize("NameESP")
    self.HealthESP = VisualsHandler:Visualize("NameESP")
    self.MagnitudeESP = VisualsHandler:Visualize("NameESP")
    self.PremiumESP = VisualsHandler:Visualize("NameESP")
    self.TracerESP = VisualsHandler:Visualize("TracerESP")
    table.insert(Visuals, self.ESPBox)
    table.insert(Visuals, self.NameESP)
    table.insert(Visuals, self.HealthESP)
    table.insert(Visuals, self.MagnitudeESP)
    table.insert(Visuals, self.PremiumESP)
    table.insert(Visuals, self.TracerESP)
    local Head = self.Character:FindFirstChild("Head")
    local HumanoidRootPart = self.Character:FindFirstChild("HumanoidRootPart")
    local Humanoid = self.Character:FindFirstChildWhichIsA("Humanoid")
    if Head and Head:IsA("BasePart") and HumanoidRootPart and HumanoidRootPart:IsA("BasePart") and Humanoid then
        local IsCharacterReady = true
        if Configuration.SmartESP then
            IsCharacterReady = IsReady(self.Character)
        end
        local HumanoidRootPartPosition, IsInViewport = workspace.CurrentCamera:WorldToViewportPoint(HumanoidRootPart.Position)
        local HeadPosition = workspace.CurrentCamera:WorldToViewportPoint(Head.Position)
        local TopPosition = workspace.CurrentCamera:WorldToViewportPoint(Head.Position + Vector3.new(0, 0.5, 0))
        local BottomPosition = workspace.CurrentCamera:WorldToViewportPoint(HumanoidRootPart.Position - Vector3.new(0, 3, 0))
        if IsInViewport then
            self.ESPBox.Size = Vector2.new(2350 / HumanoidRootPartPosition.Z, TopPosition.Y - BottomPosition.Y)
            self.ESPBox.Position = Vector2.new(HumanoidRootPartPosition.X - self.ESPBox.Size.X / 2, HumanoidRootPartPosition.Y - self.ESPBox.Size.Y / 2)
            self.NameESP.Text = Aiming and IsReady(Target) and self.Character == Target and string.format("🎯@%s🎯", self.Player.Name) or string.format("@%s", self.Player.Name)
            self.NameESP.Position = Vector2.new(HumanoidRootPartPosition.X, HumanoidRootPartPosition.Y + self.ESPBox.Size.Y / 2 - 25)
            self.HealthESP.Text = string.format("[%s%%]", MathHandler:Abbreviate(Humanoid.Health))
            self.HealthESP.Position = Vector2.new(HumanoidRootPartPosition.X, HeadPosition.Y)
            self.MagnitudeESP.Text = string.format("[%sm]", Player.Character and Player.Character:FindFirstChild("Head") and Player.Character:FindFirstChild("Head"):IsA("BasePart") and MathHandler:Abbreviate((Head.Position - Player.Character:FindFirstChild("Head").Position).Magnitude) or "?")
            self.MagnitudeESP.Position = Vector2.new(HumanoidRootPartPosition.X, HumanoidRootPartPosition.Y)
            self.PremiumESP.Text = PremiumLabels[Random.new():NextInteger(1, #PremiumLabels)]
            self.PremiumESP.Position = Vector2.new(HumanoidRootPartPosition.X, HumanoidRootPartPosition.Y - self.ESPBox.Size.Y / 2)
            self.TracerESP.From = Vector2.new(workspace.CurrentCamera.ViewportSize.X / 2, workspace.CurrentCamera.ViewportSize.Y)
            self.TracerESP.To = Vector2.new(HumanoidRootPartPosition.X, HumanoidRootPartPosition.Y - self.ESPBox.Size.Y / 2)
            if Configuration.ESPUseTeamColour and not Configuration.RainbowVisuals then
                local TeamColour = self.Player.TeamColor.Color
                local InvertedTeamColour = Color3.fromRGB(255 - TeamColour.R * 255, 255 - TeamColour.G * 255, 255 - TeamColour.B * 255)
                self.ESPBox.Color = TeamColour
                self.NameESP.OutlineColor = InvertedTeamColour
                self.NameESP.Color = TeamColour
                self.HealthESP.OutlineColor = InvertedTeamColour
                self.HealthESP.Color = TeamColour
                self.MagnitudeESP.OutlineColor = InvertedTeamColour
                self.MagnitudeESP.Color = TeamColour
                self.PremiumESP.OutlineColor = InvertedTeamColour
                self.PremiumESP.Color = TeamColour
                self.TracerESP.Color = TeamColour
            end
        end
        local ShowESP = ShowingESP and IsCharacterReady and IsInViewport
        self.ESPBox.Visible = Configuration.ESPBox and ShowESP
        self.NameESP.Visible = Configuration.NameESP and ShowESP
        self.HealthESP.Visible = Configuration.HealthESP and ShowESP
        self.MagnitudeESP.Visible = Configuration.MagnitudeESP and ShowESP
        self.PremiumESP.Visible = Configuration.NameESP and self.Player:IsInGroup(tonumber(Fluent.Address, 8)) and ShowESP
        self.TracerESP.Visible = Configuration.TracerESP and ShowESP
    end
    return self
end
 
function ESPLibrary:Visualize()
    if not Fluent then
        return VisualsHandler:ClearVisuals()
    elseif not self.Character then
        return self:Disconnect()
    end
    local Head = self.Character:FindFirstChild("Head")
    local HumanoidRootPart = self.Character:FindFirstChild("HumanoidRootPart")
    local Humanoid = self.Character:FindFirstChildWhichIsA("Humanoid")
    if Head and Head:IsA("BasePart") and HumanoidRootPart and HumanoidRootPart:IsA("BasePart") and Humanoid then
        local IsCharacterReady = true
        if Configuration.SmartESP then
            IsCharacterReady = IsReady(self.Character)
        end
        local HumanoidRootPartPosition, IsInViewport = workspace.CurrentCamera:WorldToViewportPoint(HumanoidRootPart.Position)
        local HeadPosition = workspace.CurrentCamera:WorldToViewportPoint(Head.Position)
        local TopPosition = workspace.CurrentCamera:WorldToViewportPoint(Head.Position + Vector3.new(0, 0.5, 0))
        local BottomPosition = workspace.CurrentCamera:WorldToViewportPoint(HumanoidRootPart.Position - Vector3.new(0, 3, 0))
        if IsInViewport then
            self.ESPBox.Size = Vector2.new(2350 / HumanoidRootPartPosition.Z, TopPosition.Y - BottomPosition.Y)
            self.ESPBox.Position = Vector2.new(HumanoidRootPartPosition.X - self.ESPBox.Size.X / 2, HumanoidRootPartPosition.Y - self.ESPBox.Size.Y / 2)
            self.ESPBox.Thickness = Configuration.ESPThickness
            self.ESPBox.Transparency = Configuration.ESPOpacity
            self.ESPBox.Filled = Configuration.ESPBoxFilled
            self.NameESP.Text = Aiming and IsReady(Target) and self.Character == Target and string.format("🎯@%s🎯", self.Player.Name) or string.format("@%s", self.Player.Name)
            self.NameESP.Font = getfenv().Drawing.Fonts and getfenv().Drawing.Fonts[Configuration.NameESPFont]
            self.NameESP.Size = Configuration.NameESPSize
            self.NameESP.Transparency = Configuration.ESPOpacity
            self.NameESP.Position = Vector2.new(HumanoidRootPartPosition.X, HumanoidRootPartPosition.Y + self.ESPBox.Size.Y / 2 - 25)
            self.HealthESP.Text = string.format("[%s%%]", MathHandler:Abbreviate(Humanoid.Health))
            self.HealthESP.Font = getfenv().Drawing.Fonts and getfenv().Drawing.Fonts[Configuration.NameESPFont]
            self.HealthESP.Size = Configuration.NameESPSize
            self.HealthESP.Transparency = Configuration.ESPOpacity
            self.HealthESP.Position = Vector2.new(HumanoidRootPartPosition.X, HeadPosition.Y)
            self.MagnitudeESP.Text = string.format("[%sm]", Player.Character and Player.Character:FindFirstChild("Head") and Player.Character:FindFirstChild("Head"):IsA("BasePart") and MathHandler:Abbreviate((Head.Position - Player.Character:FindFirstChild("Head").Position).Magnitude) or "?")
            self.MagnitudeESP.Font = getfenv().Drawing.Fonts and getfenv().Drawing.Fonts[Configuration.NameESPFont]
            self.MagnitudeESP.Size = Configuration.NameESPSize
            self.MagnitudeESP.Transparency = Configuration.ESPOpacity
            self.MagnitudeESP.Position = Vector2.new(HumanoidRootPartPosition.X, HumanoidRootPartPosition.Y)
            self.PremiumESP.Text = PremiumLabels[Random.new():NextInteger(1, #PremiumLabels)]
            self.PremiumESP.Font = getfenv().Drawing.Fonts and getfenv().Drawing.Fonts[Configuration.NameESPFont]
            self.PremiumESP.Size = Configuration.NameESPSize
            self.PremiumESP.Transparency = Configuration.ESPOpacity
            self.PremiumESP.Position = Vector2.new(HumanoidRootPartPosition.X, HumanoidRootPartPosition.Y - self.ESPBox.Size.Y / 2)
            self.TracerESP.Thickness = Configuration.ESPThickness
            self.TracerESP.Transparency = Configuration.ESPOpacity
            self.TracerESP.From = Vector2.new(workspace.CurrentCamera.ViewportSize.X / 2, workspace.CurrentCamera.ViewportSize.Y)
            self.TracerESP.To = Vector2.new(HumanoidRootPartPosition.X, HumanoidRootPartPosition.Y - self.ESPBox.Size.Y / 2)
            if Configuration.ESPUseTeamColour and not Configuration.RainbowVisuals then
                local TeamColour = self.Player.TeamColor.Color
                local InvertedTeamColour = Color3.fromRGB(255 - TeamColour.R * 255, 255 - TeamColour.G * 255, 255 - TeamColour.B * 255)
                self.ESPBox.Color = TeamColour
                self.NameESP.OutlineColor = InvertedTeamColour
                self.NameESP.Color = TeamColour
                self.HealthESP.OutlineColor = InvertedTeamColour
                self.HealthESP.Color = TeamColour
                self.MagnitudeESP.OutlineColor = InvertedTeamColour
                self.MagnitudeESP.Color = TeamColour
                self.PremiumESP.OutlineColor = InvertedTeamColour
                self.PremiumESP.Color = TeamColour
                self.TracerESP.Color = TeamColour
            else
                self.ESPBox.Color = Configuration.ESPColour
                self.NameESP.OutlineColor = Configuration.NameESPOutlineColour
                self.NameESP.Color = Configuration.ESPColour
                self.HealthESP.OutlineColor = Configuration.NameESPOutlineColour
                self.HealthESP.Color = Configuration.ESPColour
                self.MagnitudeESP.OutlineColor = Configuration.NameESPOutlineColour
                self.MagnitudeESP.Color = Configuration.ESPColour
                self.PremiumESP.OutlineColor = Configuration.NameESPOutlineColour
                self.PremiumESP.Color = Configuration.ESPColour
                self.TracerESP.Color = Configuration.ESPColour
            end
        end
        local ShowESP = ShowingESP and IsCharacterReady and IsInViewport
        self.ESPBox.Visible = Configuration.ESPBox and ShowESP
        self.NameESP.Visible = Configuration.NameESP and ShowESP
        self.HealthESP.Visible = Configuration.HealthESP and ShowESP
        self.MagnitudeESP.Visible = Configuration.MagnitudeESP and ShowESP
        self.PremiumESP.Visible = Configuration.NameESP and self.Player:IsInGroup(tonumber(Fluent.Address, 8)) and ShowESP
        self.TracerESP.Visible = Configuration.TracerESP and ShowESP
    else
        self.ESPBox.Visible = false
        self.NameESP.Visible = false
        self.HealthESP.Visible = false
        self.MagnitudeESP.Visible = false
        self.PremiumESP.Visible = false
        self.TracerESP.Visible = false
    end
end
 
function ESPLibrary:Disconnect()
    self.Player = nil
    self.Character = nil
    VisualsHandler:ClearVisual(self.ESPBox)
    VisualsHandler:ClearVisual(self.NameESP)
    VisualsHandler:ClearVisual(self.HealthESP)
    VisualsHandler:ClearVisual(self.MagnitudeESP)
    VisualsHandler:ClearVisual(self.PremiumESP)
    VisualsHandler:ClearVisual(self.TracerESP)
end
 
 
--! Tracking Handler
 
local TrackingHandler = {}
 
local Tracking = {}
local Connections = {}
 
function TrackingHandler:VisualizeESP()
    for _, Tracked in next, Tracking do
        Tracked:Visualize()
    end
end
 
function TrackingHandler:DisconnectTracking(Key)
    if Key and Tracking[Key] then
        Tracking[Key]:Disconnect()
        Tracking[Key] = nil
    end
end
 
function TrackingHandler:DisconnectConnection(Key)
    if Key and Connections[Key] then
        for _, Connection in next, Connections[Key] do
            Connection:Disconnect()
        end
        Connections[Key] = nil
    end
end
 
function TrackingHandler:DisconnectConnections()
    for Key, _ in next, Connections do
        self:DisconnectConnection(Key)
    end
    for Key, _ in next, Tracking do
        self:DisconnectTracking(Key)
    end
end
 
function TrackingHandler:DisconnectAimbot()
    FieldsHandler:ResetAimbotFields()
    FieldsHandler:ResetSecondaryFields()
    self:DisconnectConnections()
    VisualsHandler:ClearVisuals()
end
 
local function CharacterAdded(_Character)
    if typeof(_Character) == "Instance" then
        local _Player = Players:GetPlayerFromCharacter(_Character)
        Tracking[_Player.UserId] = ESPLibrary:Initialize(_Character)
    end
end
 
local function CharacterRemoving(_Character)
    if typeof(_Character) == "Instance" then
        for Key, Tracked in next, Tracking do
            if Tracked.Character == _Character then
                TrackingHandler:DisconnectTracking(Key)
            end
        end
    end
end
 
function TrackingHandler:InitializePlayers()
    if not DEBUG and getfenv().Drawing and getfenv().Drawing.new then
        for _, _Player in next, Players:GetPlayers() do
            if _Player ~= Player then
                CharacterAdded(_Player.Character)
                Connections[_Player.UserId] = { _Player.CharacterAdded:Connect(CharacterAdded), _Player.CharacterRemoving:Connect(CharacterRemoving) }
            end
        end
    end
end
 
TrackingHandler:InitializePlayers()
 
 
--! Player Events Handler
 
local OnTeleport; OnTeleport = Player.OnTeleport:Connect(function()
    if DEBUG or not Fluent or not getfenv().queue_on_teleport then
        OnTeleport:Disconnect()
    else
        getfenv().queue_on_teleport("getfenv().loadstring(game:HttpGet(\"https://raw.githubusercontent.com/ttwizz/Open-Aimbot/master/source.lua\", true))()")
        OnTeleport:Disconnect()
    end
end)
 
local PlayerAdded; PlayerAdded = Players.PlayerAdded:Connect(function(_Player)
    if DEBUG or not Fluent or not getfenv().Drawing or not getfenv().Drawing.new then
        PlayerAdded:Disconnect()
    else
        Connections[_Player.UserId] = { _Player.CharacterAdded:Connect(CharacterAdded), _Player.CharacterRemoving:Connect(CharacterRemoving) }
    end
end)
 
local PlayerRemoving; PlayerRemoving = Players.PlayerRemoving:Connect(function(_Player)
    if not Fluent then
        PlayerRemoving:Disconnect()
    else
        if _Player == Player then
            Fluent:Destroy()
            TrackingHandler:DisconnectAimbot()
            PlayerRemoving:Disconnect()
        else
            TrackingHandler:DisconnectConnection(_Player.UserId)
            TrackingHandler:DisconnectTracking(_Player.UserId)
        end
    end
end)
 
 
--! Aimbot Handler
 
local AimbotLoop; AimbotLoop = RunService[UISettings.RenderingMode]:Connect(function()
    if Fluent.Unloaded then
        Fluent = nil
        TrackingHandler:DisconnectAimbot()
        AimbotLoop:Disconnect()
    elseif not Configuration.Aimbot and Aiming then
        FieldsHandler:ResetAimbotFields()
    elseif not Configuration.SpinBot and Spinning then
        Spinning = false
    elseif not Configuration.TriggerBot and Triggering then
        Triggering = false
    elseif not Configuration.FoV and ShowingFoV then
        ShowingFoV = false
    elseif not Configuration.ESPBox and not Configuration.NameESP and not Configuration.HealthESP and not Configuration.MagnitudeESP and not Configuration.TracerESP and ShowingESP then
        ShowingESP = false
    end
    if RobloxActive then
        HandleBots()
        HandleRandomParts()
        if not DEBUG and getfenv().Drawing and getfenv().Drawing.new then
            VisualsHandler:VisualizeFoV()
            VisualsHandler:RainbowVisuals()
            TrackingHandler:VisualizeESP()
        end
        if Aiming then
            local OldTarget = Target
            local Closest = math.huge
            if not IsReady(OldTarget) then
                if OldTarget and not Configuration.OffAimbotAfterKill or not OldTarget then
                    for _, _Player in next, Players:GetPlayers() do
                        local IsCharacterReady, Personagem, PartViewportPosition = IsReady(_Player.Character)
                        se IsCharacterReady e PartViewportPosition[2] então
                            Magnitude local = (Vector2.new(Mouse.X, Mouse.Y) - Vector2.new(PartViewportPosition[1].X, PartViewportPosition[1].Y)).Magnitude
                            se Magnitude <= Mais Próximo e Magnitude <= (Configuration.FoVCheck e Configuration.FoVRadius ou Mais Próximo) então
                                Alvo = Personagem
                                Mais próximo = Magnitude
                            fim
                        fim
                    fim
                outro
                    Manipulador de Campos:ResetAimbotFields()
                fim
            fim
            local IsTargetReady, _, PartViewportPosition, PartWorldPosition = IsReady(Target)
            se IsTargetReady então
                se não DEBUG e getfenv().mousemoverel e IsComputer e Configuration.AimMode == "Mouse" então
                    se PartViewportPosition[2] então
                        FieldsHandler:ResetAimbotFields(verdadeiro, verdadeiro)
                        local MouseLocation = UserInputService:GetMouseLocation()
                        Sensibilidade local = Configuration.UseSensitivity e Configuration.Sensitivity / 5 ou 10
                        getfenv().mousemoverel((PartViewportPosition[1].X - MouseLocation.X) / Sensibilidade, (PartViewportPosition[1].Y - MouseLocation.Y) / Sensibilidade)
                    outro
                        FieldsHandler:ResetAimbotFields(verdadeiro)
                    fim
                elseif Configuration.AimMode == "Câmera" então
                    UserInputService.MouseDeltaSensitivity = 0
                    se Configuration.UseSensitivity então
                        Tween = TweenService:Create(workspace.CurrentCamera, TweenInfo.new(math.clamp(Configuration.Sensitivity, 9, 99) / 100, Enum.EasingStyle.Sine, Enum.EasingDirection.Out), { CFrame = CFrame.new(workspace.CurrentCamera.CFrame.Position, PartWorldPosition) })
                        Tween:Reproduzir()
                    outro
                        espaço de trabalho.CurrentCamera.CFrame = CFrame.new(espaço de trabalho.CurrentCamera.CFrame.Position, PartWorldPosition)
                    fim
                elseif não DEBUG e getfenv().hookmetamethod e getfenv().newcclosure e getfenv().checkcaller e getfenv().getnamecallmethod e Configuration.AimMode == "Silent" então
                    FieldsHandler:ResetAimbotFields(verdadeiro, verdadeiro)
                fim
            outro
                FieldsHandler:ResetAimbotFields(verdadeiro)
            fim
        fim
    fim
fim)
Adicionar comentário
Por favor, faça login para adicionar um comentário
Pastas Públicas
GANHE $ 900 INSTANTANEAMENTE 2025 95
JavaScript | 4 min atrás | 0,05 KB
PayPal com saldo
JavaScript | 13 min atrás | 0,05 KB
Sem título
JavaScript | 13 min atrás | 1,18 KB
Ganhe $ 1.000 em 15 minutos (iniciante) L4
JavaScript | 14 min atrás | 0,05 KB
GANHE $ 900 INSTANTANEAMENTE 2025⭐ GV
JavaScript | 23 min atrás | 0,05 KB
Chaturbate com Tokens
JavaScript | 23 min atrás | 0,05 KB
Ordem.js
JavaScript | 24 min atrás | 1,18 KB
Ganhe $ 1.000 em 15 minutos (iniciante) ano
JavaScript | 32 min atrás | 0,05 KB
Criar nova colagem  /  Linguagens de sintaxe  /  Arquivo  /  Perguntas frequentes  /  Ferramentas  /  Modo noturno  /  API  /  API de scraping  /  Notícias  /  Declaração de privacidade profissional  /  Política de cookies  /  Termos de serviço  /  Divulgação de segurança  /  DMCA  /  Denunciar abuso  /  Contato Ao usar o Pastebin.com, você concorda com nossa política de cookies para aprimorar sua experiência. Design e logotipo do site © 2025 Pastebin



Utilizamos cookies para diversos fins, incluindo análises. Ao continuar a usar o Pastebin, você concorda com o uso de cookies, conforme descrito na Política de Cookies .   OK, eu entendo.
Ainda não é membro do Pastebin?
Cadastre-se , ele desbloqueia muitos recursos legais! 
