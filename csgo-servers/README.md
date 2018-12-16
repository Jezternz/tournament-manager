# Setting Up CSGO Dedicated Servers

## Forwarding Ports

Forward the ports mentioned on the [Dedicated Server](https://developer.valvesoftware.com/wiki/Source_Dedicated_Server) page.

## Creating Game Server Login Tokens (GSLTs)

1. Go go [Manage Game Servers](https://steamcommunity.com/dev/managegameservers) and create tokens for your dedicated servers.

## Installing Dedicated Servers

1. Install [Steam-CMD](https://developer.valvesoftware.com/wiki/SteamCMD#Downloading_SteamCMD) to `C:\SteamCMD`, or similar.

2. Run this command to install CSGO dedicated server

    `steamcmd +login anonymous +force_install_dir ../csgo_ds +app_update 740 validate +quit`

    Or if you need a login: `+login <username> <password>`

    The game will be installed in a folder like `C:\csgo_ds\steamapps\common\Counter-Strike Global Offensive Beta - Dedicated Server`.

4. Change the server name in the `autoexec.cfg` and any other settings in that file or `server.cfg`.

5. Copy the `server.cfg` and `autoexec.cfg` to the `csgo\cfg` folder.

6. Start servers:

    Competitive: `srcds -game csgo -console -usercon +sv_setsteamaccount <gsltoken> -net_port_try 1 +game_type 0 +game_mode 1 +mapgroup mg_active +map de_dust2`

    Wingman: `srcds -game csgo -console -usercon +sv_setsteamaccount <gsltoken> -net_port_try 1 +game_type 0 +game_mode 2 +map de_shortdust`

## Updating Existing Servers

1. Run the same command that installed it:

    `steamcmd +login anonymous +force_install_dir ../csgo_ds +app_update 740 validate +quit`

# Using RCon In Game

1. Type `rcon_password <password>` to enable RCON to the server. The password is defined in the `autoexec.cfg`.

2. Issue commands with `rcon <command>`.

# Official Docs

* https://developer.valvesoftware.com/wiki/Counter-Strike:_Global_Offensive_Dedicated_Servers
* https://developer.valvesoftware.com/wiki/Source_Dedicated_Server
* https://developer.valvesoftware.com/wiki/SteamCMD
* https://steamcommunity.com/dev/managegameservers
