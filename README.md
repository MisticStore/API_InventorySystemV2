# API_InventorySystemV2
API do nosso Inventário na Versão 2.0

## Sumário

- [Player API](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#player-api)
    - [Funções : server - side](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#fun%C3%A7%C3%B5es-do-lado-server---side)
        - [getPlayerItem](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#getplayeritem)
        - [givePlayerItem](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#giveplayeritem)
        - [takePlayerItem](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#takeplayeritem)
        - [getAllPlayerItens](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#getallplayeritens)
        - [isPlayerReciveItem](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#isplayerreciveitem)
        - [setPlayerMaxWeight](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#setplayermaxweight)
        - [updatePlayerInventory](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#updateplayerinventory)
        - [getPlayerActualWeight](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#getplayeractualweight)
        - [getPlayerInventoryData](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#getplayerinventorydata)

- [Aditional API](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#aditional-api)
    - [Funções : server - side](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#fun%C3%A7%C3%B5es-do-lado-server---side-1)
        - [getAditionalElementFromData](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#getaditionalelementfromdata)
        - [getAditionalItem](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#getaditionalitem)


# Player API

## Funções do lado `server - side`

## **getPlayerItem**
- **Argumentos Obrigatórios:**
    - [element](https://wiki.multitheftauto.com/wiki/Element) `playerElement`: Elemento do Jogador.
    - [string](https://wiki.multitheftauto.com/wiki/String) `itemCheck`: Item desejado a Checar.

- **Retorno da Função:**
    - [bool](https://wiki.multitheftauto.com/wiki/Boolean) `haveItem`: Retorna *true* caso o Jogador possua o Item, *falso* a ação contrária.
    - [int](https://wiki.multitheftauto.com/wiki/Int) `amountItem`: Retorna a *quantidade* do Item que o Jogador possui.
    - [int](https://wiki.multitheftauto.com/wiki/Int) `indexItem`: Retorna a *posição / index* do Item na tabela de Itens do Jogador.

Syntax

```Lua
bool, int, int getPlayerItem (playerElement, itemCheck)
```

Exemplo

```Lua
local inventory = exports["mistic_inventory_v2"]

addCommandHandler ("getitem", function (playerElement, commandExecute, itemCheck)
    local haveItem, amountItem, indexItem = inventory:getPlayerItem (playerElement, itemCheck)
    print (haveItem, amountItem, indexItem)
end)
```

## **givePlayerItem**
- **Argumentos Obrigatórios:**
    - [element](https://wiki.multitheftauto.com/wiki/Element) `playerElement`: Elemento do Jogador.
    - [string](https://wiki.multitheftauto.com/wiki/String) `itemGive`: Item desejado a Givar.
    - [int](https://wiki.multitheftauto.com/wiki/Int) `itemAmount`: Quantidade que deseja Givar.

- **Retorno da Função:**
    - [bool](https://wiki.multitheftauto.com/wiki/Boolean): Retorna *true* caso o Jogador recebeu o Item, *falso* a ação contrária.

Syntax

```Lua
bool givePlayerItem (playerElement, itemGive, itemAmount)
```

Exemplo

```Lua
local inventory = exports["mistic_inventory_v2"]

addCommandHandler ("giveitem", function (playerElement, commandExecute, itemGive, itemAmount)
    local giveItem = inventory:givePlayerItem (playerElement, itemGive, itemAmount)
    print (giveItem)
end)
```

# **takePlayerItem**
- **Argumentos Obrigatórios:**
    - [element](https://wiki.multitheftauto.com/wiki/Element) `playerElement`: Elemento do Jogador.
    - [string](https://wiki.multitheftauto.com/wiki/String) `itemTake`: Item desejado a Retirar.
    - [int](https://wiki.multitheftauto.com/wiki/Int) `itemAmount`: Quantidade que deseja Retirar.

- **Retorno da Função:**
    - [bool](https://wiki.multitheftauto.com/wiki/Boolean): Retorna *true* caso o Item foi removido do Jogador, *falso* a ação contrária.

Syntax

```Lua
bool takePlayerItem (playerElement, itemTake, itemAmount)
```

Exemplo

```Lua
local inventory = exports["mistic_inventory_v2"]

addCommandHandler ("takeitem", function (playerElement, commandExecute, itemTake, itemAmount)
    local takeItem = inventory:takePlayerItem (playerElement, itemTake, itemAmount)
    print (takeItem)
end)
```

# **getAllPlayerItens**
- **Argumentos Obrigatórios:**
    - [element](https://wiki.multitheftauto.com/wiki/Element) `playerElement`: Elemento do Jogador.

- **Retorno da Função:**
    - [table](https://wiki.multitheftauto.com/wiki/Table): Retorna a *tabela* de Itens do Jogador.

Syntax

```Lua
table getAllPlayerItens (playerElement)
```

Exemplo

```Lua
local inventory = exports["mistic_inventory_v2"]

addCommandHandler ("getitens", function (playerElement, commandExecute)
    local playerItens = inventory:getAllPlayerItens (playerElement)
    iprint (playerItens, #playerItens)
end)
```

# **isPlayerReciveItem**
- **Argumentos Obrigatórios:**
    - [element](https://wiki.multitheftauto.com/wiki/Element) `playerElement`: Elemento do Jogador.
    - [string](https://wiki.multitheftauto.com/wiki/String) `itemRecive`: Item desejado a Verificar.
    - [int](https://wiki.multitheftauto.com/wiki/Int) `itemAmount`: Quantidade que deseja Verificar.

- **Retorno da Função:**
    - [bool](https://wiki.multitheftauto.com/wiki/Boolean): Retorna *true* caso o Jogador possa receber aquela quantidade do Item, *falso* a ação contrária.

Syntax

```Lua
bool isPlayerReciveItem (playerElement, itemRecive, itemAmount)
```

Exemplo

```Lua
local inventory = exports["mistic_inventory_v2"]

addCommandHandler ("isitem", function (playerElement, commandExecute, itemRecive, itemAmount)
    local reciveItem = inventory:isPlayerReciveItem (playerElement, itemRecive, itemAmount)
    print (reciveItem)
end)
```

# **setPlayerMaxWeight**
- **Argumentos Obrigatórios:**
    - [element](https://wiki.multitheftauto.com/wiki/Element) `playerElement`: Elemento do Jogador.
    - [int](https://wiki.multitheftauto.com/wiki/Int) `newWeight`: Peso desejado a Adicionar.
    - [bool](https://wiki.multitheftauto.com/wiki/Boolean) `withOld`: Se vai somar com o peso antigo ou não.

- **Retorno da Função:**
    - [bool](https://wiki.multitheftauto.com/wiki/Boolean): Retorna *true* caso o Jogador tenha o Peso Máximo do inventário alterado, *falso* a ação contrária.

Syntax

```Lua
bool setPlayerMaxWeight (playerElement, newWeight, withOld)
```

Exemplo

```Lua
local inventory = exports["mistic_inventory_v2"]

addCommandHandler ("setweight", function (playerElement, commandExecute, newWeight, withOld)
    local setWeight = inventory:setPlayerMaxWeight (playerElement, newWeight, withOld)
    print (setWeight)
end)
```

# **updatePlayerInventory**
- **Argumentos Obrigatórios:**
    - [element](https://wiki.multitheftauto.com/wiki/Element) `playerElement`: Elemento do Jogador.

- **Retorno da Função:**
    - [bool](https://wiki.multitheftauto.com/wiki/Boolean): Retorna *true* caso o Inventário do Jogador tenha sido atualizado para o `client - side`, *falso* a ação contrária.

Syntax

```Lua
bool updatePlayerInventory (playerElement)
```

Exemplo 1

```Lua
local inventory = exports["mistic_inventory_v2"]

addCommandHandler ("updateinv", function (playerElement, commandExecute)
    local updateInv = inventory:updatePlayerInventory (playerElement)
    print (updateInv)
end)
```

Exemplo 2

```Lua
-- server - side

addEventHandler ("mistic_inventory:forceUpdatePlayerInventory", getRootElement (), function (playerElement)
    print ("Update Enviado.")
end)

-- client - side

addEventHandler ("mistic_inventory:updatePlayerInventory", getRootElement (), function (typeUpdate, elementInventory, tableInventory)
    --[[
        typeUpdate: Tipo do Update ("player" ou "adicional");
        elementInventory: Elemento para Atualizar (tem que ser o mesmo do inventário, ex : Inventário aberto pelo Jogador `Thigas`, elementInventory = `Thigas`);
        tableInventory: Tabela do Inventário do Jogador (tem que conter todas as informações do Inventário);
    ]]
    print ("Inventário Atualizado.")
end)
```

# **getPlayerActualWeight**
- **Argumentos Obrigatórios:**
    - [element](https://wiki.multitheftauto.com/wiki/Element) `playerElement`: Elemento do Jogador.

- **Retorno da Função:**
    - [int](https://wiki.multitheftauto.com/wiki/Int): Retorna o *peso* do Inventário do Jogador.

Syntax

```Lua
int getPlayerActualWeight (playerElement)
```

Exemplo

```Lua
local inventory = exports["mistic_inventory_v2"]

addCommandHandler ("getweight", function (playerElement, commandExecute)
    local myWeight = inventory:getPlayerActualWeight (playerElement)
    print (myWeight)
end)
```

# **getPlayerInventoryData**
- **Argumentos Obrigatórios:**
    - [element](https://wiki.multitheftauto.com/wiki/Element) `playerElement`: Elemento do Jogador.

- **Retorno da Função:**
    - [table](https://wiki.multitheftauto.com/wiki/Table): Retorna a *tabela* do Inventário do Jogador.

Syntax

```Lua
table getPlayerInventoryData (playerElement)
```

Exemplo

```Lua
local inventory = exports["mistic_inventory_v2"]

addCommandHandler ("getinv", function (playerElement, commandExecute)
    local playerItens = inventory:getPlayerInventoryData (playerElement)
    iprint (playerItens, playerItens.itensData, playerItens.informationsData)
end)
```

# Aditional API

## Funções do lado `server - side`

## **getAditionalElementFromData**

```Lua
function getAditionalElementFromData (nameAditional)
    local tableAditional = getElementsByType ("objects")
    if tableAditional and #tableAditional ~= 0 then
        local aditionalElement = tableAditional[i]
        if aditionalElement and isElement (aditionalElement) and getElementData (aditionalElement, "mistic_inventory:thisInventoryObject") and getElementData (aditionalElement, "mistic_inventory:thisInventoryObject").identify == nameAditional then
            return aditionalElement
        end
    end
    return false
end
```

## **getAditionalItem**
- **Argumentos Obrigatórios:**
    - [element](https://wiki.multitheftauto.com/wiki/Element) `aditionalElement`: Elemento do Adicional.
    - [string](https://wiki.multitheftauto.com/wiki/String) `aditionalData`: Data do Adicional.
    - [string](https://wiki.multitheftauto.com/wiki/String) `itemCheck`: Item desejado a Checar.

- **Retorno da Função:**
    - [bool](https://wiki.multitheftauto.com/wiki/Boolean) `haveItem`: Retorna *true* caso o Adicional possua o Item, *falso* a ação contrária.
    - [int](https://wiki.multitheftauto.com/wiki/Int) `amountItem`: Retorna a *quantidade* do Item que o Adicional possui.
    - [int](https://wiki.multitheftauto.com/wiki/Int) `indexItem`: Retorna a *posição / index* do Item na tabela de Itens do Adicional.

Syntax

```Lua
bool, int, int getAditionalItem (aditionalElement, aditionalData, itemCheck)
```

Exemplo

```Lua
local inventory = exports["mistic_inventory_v2"]

addCommandHandler ("getaitem", function (playerElement, commandExecute, aditionalData, itemCheck)
    local aditionalElement = getAditionalElementFromData (aditionalData)
    if aditionalElement then
        local haveItem, amountItem, indexItem = inventory:getAditionalItem (aditionalElement, aditionalData, itemCheck)
        print (haveItem, amountItem, indexItem)
    end
end)
```
