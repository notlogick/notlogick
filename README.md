local targeting = false 
function main()
    if not isSampfuncsLoaded() or not isSampLoaded() then
        return
    end
    while not isSampAvailable() do
        wait(0)
    end
    sampAddChatMessage("Hello World!", 0xFFFFFFFF)
    while true do
        wait(0)
        local result, ped = getCharPlayerIsTargeting(playerPed)
        if result and not targeting then 
            local result2, id = sampGetPlayerIdByCharHandle(ped)
            if result2 then
                local nickname = sampGetPlayerNickname(id)
                local score = sampGetPlayerScore(id)
                sampAddChatMessage(string.format("%s[%d] has an account %d", nickname, id, score), -1)
                targeting = true 
            end
        elseif not result and targeting then 
            targeting = false
        end
    end
end


function main()
    if not isSampfuncsLoaded() or not isSampLoaded() then
        return
    end
    while not isSampAvailable() do
        wait(0)
    end

    sampRegisterChatCommand("toster", tosterCallBack) 

    wait(-1) 
end

function tosterCallBack(params)
    sampAddChatMessage("Call!", -1)
end

sampAddChatMessage(params, -1)

(error) test.lua: opcode '0AF8' call caused an unhandled exception


https://lua.org.ru/manual_ru.html




















