local brainhort_roubado = false
local cooldown = 1 -- em segundos
local pode_roubar = true

function roubar_brainhort()
    if pode_roubar then
        print("Iniciando roubo... Aguarde " .. cooldown .. " segundo(s).")
        pode_roubar = false
        local start = os.time()
        while os.difftime(os.time(), start) < cooldown do
            -- Espera o cooldown terminar
        end
        brainhort_roubado = true
        pode_roubar = true
        print("Brainhort roubado pelo Alto Setal! Você está seguro na base.")
    else
        print("Aguarde o cooldown antes de roubar novamente!")
    end
end

while true do
    print("\n=== Alto Setal ===")
    if not brainhort_roubado then
        print("Pressione ENTER para 'Roubar' o brainhort.")
        io.read()
        roubar_brainhort()
    else
        print("Você já roubou o brainhort! Reiniciando para tentar de novo.\n")
        brainhort_roubado = false
    end
end
