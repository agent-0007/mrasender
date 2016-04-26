# mrasender - [Tarantool][] module for sending messages to Mail.Ru Agent

## Prerequisites

 * Tarantool 1.6.5+ with header files (tarantool && tarantool-dev packages)
 * Msgpuk ( git clone https://github.com/rtsisyk/msgpuck && cd msgpuck && cmake . && make install)

## HOWTO
```lua

#!/usr/bin/env tarantool

box.cfg{
        log_level = 5
}

local agent = require('mrasender')
local log   = require('log')

local username  = 'USERNAME@mail.ru'
local password  = 'PASSWORD'
local recipient = 'RECIPIENT@mail.ru'
local msg       = 'Test message from tarantool'

-- send message to recipient from username
local res = agent.send_message_to_mra(username, password, recipient, msg)

log.info("Send message to:"..recipient..", result:"..res);

```
Enjoy!

## See Also

 * [Tarantool][]
 * [Tarantool Rocks][TarantoolRocks]
 * [Tarantool/Lua API Reference][TarantoolLuaReference]
 * [Tarantool/C API Reference][TarantoolCReference]
 * [Lua/C API Reference][LuaCReference]

[Tarantool]: http://github.com/tarantool/tarantool
[Download]: http://tarantool.org/download.html
[RockSpec]: https://github.com/keplerproject/luarocks/wiki/Rockspec-format
[LuaCReference]: http://pgl.yoyo.org/luai/i/_
[TarantoolLuaReference]: http://tarantool.org/doc/reference/index.html
[TarantoolCReference]: http://tarantool.org/doc/reference/capi.html
[TarantoolRocks]: https://github.com/tarantool/rocks
