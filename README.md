# API_InventorySystemV2
API do nosso Inventário na Versão 2.0

## Utils API

* Verificar se o jogador possui um determinado item.

```Lua
bool, int, int getPlayerItem (player, item)
```

* Verificar se o adicional (baú / porta malas) possui um determinado item.

```Lua
bool, int, int getAditionalItem (objeto, data, item)
```

* Código útil para indentificar um adicional do inventário.

```Lua
function getAditionalElement ()
    local tableObjects = getElementsByType ("object")
    if tableObjects and #tableObjects ~= 0 then
        for i = 1, #tableObjects do
            local objectElement = tableObjects[i]
            if objectElement and isElement (objectElement) and getElementData (objectElement, "mistic_inventory:thisInventoryObject") then
                return 
            end
        end
    end
    return false
end
```

* Data dos adicionais do inventário (baú / lixeira)

```Lua
table getElementData (objeto, "mistic_inventory:thisInventoryObject")
```
