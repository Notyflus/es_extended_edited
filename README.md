<h1 align='center'>ES_EXTENDED_EDITED</h1>


### This edited version of es_extended (1.5.0) adds:
- The possibility to choosing the identification of players when connecting to the server. (license, steamid, discord, xlb, liveid, ip)
- The possibility of having a second job
- "nf_" scripting support

### Manually
- Download https://github.com/Notyflus/es_extended_edited/archive/master.zip
- Rename `es_extended_edited` to `es_extended`
- Put it in the `[esx]` directory

### Installation
- Import `es_extended_edited.sql` in your database
- Configure your `server.cfg` to look like this:

```
endpoint_add_tcp "0.0.0.0:30120"
endpoint_add_udp "0.0.0.0:30120"

set gamename gta5
sv_scriptHookAllowed 0
sv_enforceGameBuild 2545
sv_endpointPrivacy true
#sv_master1 ""   # To hide server from fivem server list

sv_hostname "FXServer, but unconfigured"
set steam_webApiKey ""   # -> replace "" with the key
sv_licenseKey changeme
sv_maxclients 10

sets sv_projectName "My FXServer Project"
sets sv_projectDesc "Default FXServer requiring configuration"
#load_server_icon icon.png
#sets banner_detail "https://url.to/image.png"
#sets banner_connecting "https://url.to/image.png"
sets locale "root-AQ"
sets tags "default"

set onesync legacy   # Infinity is not recommended for ESX
set mysql_connection_string "mysql://user:password@localhost/database?waitForConnections=true&charset=utf8mb4"   # Or `user@localhost` without password

## These resources will start by default.
ensure chat
ensure spawnmanager
ensure sessionmanager
ensure hardcap

## Add system admins
add_ace group.admin command allow # allow all commands
add_ace group.admin command.quit deny # but don't allow quit
add_ace resource.es_extended command.add_ace allow
add_ace resource.es_extended command.add_principal allow
add_ace resource.es_extended command.remove_principal allow
add_ace resource.es_extended command.stop allow

## Default & Standalone resources
ensure chat-theme-gtao # Cool Chat theme
ensure oxmysql

## ESX Legacy
ensure es_extended
ensure [esx]

## ESX Addons
ensure [esx_addons]
stop basic-gamemode #remove this if you dont want to use multicharacter
```
<hr>
