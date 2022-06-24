# API_InventorySystemV2
API do nosso Inventário na Versão 2.0

## Sumário

- [Player API](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#player-api)
    - [Funções : server - side](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#fun%C3%A7%C3%B5es-do-lado-server---side)
        - [getPlayerItem](https://github.com/MisticStore/API_InventorySystemV2/edit/main/README.md#getplayeritem)

## Player API

# Funções do lado `server - side`

# **getPlayerItem**
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

# **givePlayerItem**
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
    local giveItem = inventory:getPlayerItem (playerElement, itemGive, itemAmount)
    print (giveItem)
end)
```

# **takePlayerItem**
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
    local giveItem = inventory:getPlayerItem (playerElement, itemGive, itemAmount)
    print (giveItem)
end)
```
