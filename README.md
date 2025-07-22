local brainhort_na_mao = false
local brainhort_roubado = false
local cooldown = 1 -- em segundos

function teleportar_para_base()
    print("Teleportando você para a base...")
    -- Simulação do teleporte (aqui seria o código real de teleporte em um jogo)
    print("Você está na base!")
end

function iniciar_roubo_na_mao()
    print("Botão 'Roube' AZUL pressionado com brainhort na mão...")
    print("Aguarde " .. cooldown .. " segundo(s) para roubar e teleportar para a base.")
    local start = os.time()
    while os.difftime(os.time(), start) < cooldown do
        -- Espera o cooldown terminar
    end
    brainhort_roubado = true
    print("Brainhort roubado da sua mão!")
    teleportar_para_base()
end

function iniciar_roubo_comum()
    print("Botão 'Roube' comum pressionado...")
    print("Aguarde " .. cooldown .. " segundo(s) para roubar normalmente.")
    local start = os.time()
    while os.difftime(os.time(), start) < cooldown do
        -- Espera o cooldown terminar
    end
    brainhort_roubado = true
    print("Brainhort roubado! Retorne para a base manualmente.")
end

while true do
    print("\n=== Alto Setal ===")
    print("Você está com o brainhort na mão? (s/n)")
    local resp = io.read()
    brainhort_na_mao = (resp == "s")

    print("Escolha opção:")
    print("1 - Clique no botão 'Roube' comum")
    print("2 - Clique no botão 'Roube' azul")
    local escolha = io.read()

    if brainhort_na_mao and escolha == "2" then
        iniciar_roubo_na_mao()
    else
        iniciar_roubo_comum()
    end

    print("\nDeseja tentar de novo? (s/n)")
    if io.read() ~= "s" then break end
    brainhort_roubado = false
end
