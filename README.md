Minhas configuração do meu terminal no Windows 10 / 11

### settings.json
```bash
{
    "$help": "https://aka.ms/terminal-documentation",
    "$schema": "https://aka.ms/terminal-profiles-schema",
    "actions": 
    [
        {
            "command": 
            {
                "action": "copy",
                "singleLine": false
            },
            "id": "User.copy.644BA8F2",
            "keys": "ctrl+c"
        },
        {
            "command": "paste",
            "id": "User.paste",
            "keys": "ctrl+v"
        },
        {
            "command": 
            {
                "action": "splitPane",
                "split": "auto",
                "splitMode": "duplicate"
            },
            "id": "User.splitPane.A6751878",
            "keys": "alt+shift+d"
        },
        {
            "command": "find",
            "id": "User.find",
            "keys": "ctrl+shift+f"
        }
    ],
    "alwaysShowNotificationIcon": false,
    "centerOnLaunch": true,
    "copyFormatting": "none",
    "copyOnSelect": false,
    "defaultProfile": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
    "firstWindowPreference": "defaultProfile",
    "launchMode": "maximized",
    "newTabMenu": 
    [
        {
            "type": "remainingProfiles"
        }
    ],
    "profiles": 
    {
        "defaults": 
        {
            "backgroundImage": null,
            "colorScheme": "coolnight",
            "cursorShape": "vintage",
            "experimental.retroTerminalEffect": false,
            "font": 
            {
                "face": "JetBrainsMono Nerd Font"
            },
            "icon": "none",
            "opacity": 80,
            "padding": "8",
            "scrollbarState": "hidden",
            "useAcrylic": false
        },
        "list": 
        [
            {
                "commandline": "%SystemRoot%\\System32\\WindowsPowerShell\\v1.0\\powershell.exe",
                "guid": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
                "hidden": false,
                "name": "Windows PowerShell"
            },
            {
                "commandline": "%SystemRoot%\\System32\\cmd.exe",
                "guid": "{0caa0dad-35be-5f56-a8ff-afceeeaa6101}",
                "hidden": false,
                "name": "Prompt de comando"
            },
            {
                "guid": "{b453ae62-4e3d-5e58-b989-0a998ec441b8}",
                "hidden": false,
                "name": "Azure Cloud Shell",
                "source": "Windows.Terminal.Azure"
            }
        ]
    },
    "schemes": 
    [
        {
            "background": "#282A36",
            "black": "#21222C",
            "blue": "#BD93F9",
            "brightBlack": "#6272A4",
            "brightBlue": "#D6ACFF",
            "brightCyan": "#A4FFFF",
            "brightGreen": "#69FF94",
            "brightPurple": "#FF92DF",
            "brightRed": "#FF6E6E",
            "brightWhite": "#FFFFFF",
            "brightYellow": "#FFFFA5",
            "cursorColor": "#F8F8F2",
            "cyan": "#8BE9FD",
            "foreground": "#F8F8F2",
            "green": "#50FA7B",
            "name": "Dracula",
            "purple": "#FF79C6",
            "red": "#FF5555",
            "selectionBackground": "#44475A",
            "white": "#F8F8F2",
            "yellow": "#F1FA8C"
        },
        {
            "background": "#010C18",
            "black": "#0B3B61",
            "blue": "#1376F9",
            "brightBlack": "#63686D",
            "brightBlue": "#388EFF",
            "brightCyan": "#FF6AD7",
            "brightGreen": "#74FFD8",
            "brightPurple": "#AE81FF",
            "brightRed": "#FF54B0",
            "brightWhite": "#60FBBF",
            "brightYellow": "#FCF5AE",
            "cursorColor": "#38FF9D",
            "cyan": "#FF5ED4",
            "foreground": "#ECDEF4",
            "green": "#52FFD0",
            "name": "coolnight",
            "purple": "#C792EA",
            "red": "#FF3A3A",
            "selectionBackground": "#38FF9C",
            "white": "#16FDA2",
            "yellow": "#FFF383"
        },
        {
            "background": "#1A1A1A",
            "black": "#121212",
            "blue": "#2B4FFF",
            "brightBlack": "#666666",
            "brightBlue": "#5C78FF",
            "brightCyan": "#5AC8FF",
            "brightGreen": "#905AFF",
            "brightPurple": "#5EA2FF",
            "brightRed": "#BA5AFF",
            "brightWhite": "#FFFFFF",
            "brightYellow": "#685AFF",
            "cursorColor": "#FFFFFF",
            "cyan": "#28B9FF",
            "foreground": "#F1F1F1",
            "green": "#7129FF",
            "name": "xcad",
            "purple": "#2883FF",
            "red": "#A52AFF",
            "selectionBackground": "#FFFFFF",
            "white": "#F1F1F1",
            "yellow": "#3D2AFF"
        }
    ],
    "showTabsInTitlebar": true,
    "tabWidthMode": "equal",
    "theme": "legacyDark",
    "themes": [],
    "useAcrylicInTabRow": true
}
```
### Nerd font
No momento estou utilizando a **JetBrainsMono**, o link para o download dela está aqui [DOWNLOAD](https://www.nerdfonts.com/font-downloads)
### Starship
Antes de tudo, tenha certeza que instalou o [chocolatey](https://chocolatey.org/install#individual) na sua máquina.
Instale o starship com os seguintes comandos:
```bash
choco install starship
```
2) execute o comando `code $PROFILE` e cole o comando `Invoke-Expression (&starship init powershell)`, agora toda vez que iniciar o seu powershell, starship será executado automaticamente.
3) Execute o comando `mkdir -p ~/.config`, logo em seguida crie o arquivo com o nome **starship.toml**, e dentro dele cole a seguinte configuração:
```bash
[character]
success_symbol = "[>](bold green)"
error_symbol = "[x](bold red)"
vimcmd_symbol = "[<](bold green)"

[git_commit]
tag_symbol = " tag "

[git_status]
ahead = ">"
behind = "<"
diverged = "<>"
renamed = "r"
deleted = "x"

[aws]
symbol = "aws "

[azure]
symbol = "az "

[buf]
symbol = "buf "

[bun]
symbol = "bun "

[c]
symbol = "C "

[cobol]
symbol = "cobol "

[conda]
symbol = "conda "

[crystal]
symbol = "cr "

[cmake]
symbol = "cmake "

[daml]
symbol = "daml "

[dart]
symbol = "dart "

[deno]
symbol = "deno "

[dotnet]
symbol = ".NET "

[directory]
read_only = " ro"

[docker_context]
symbol = "docker "

[elixir]
symbol = "exs "

[elm]
symbol = "elm "

[fennel]
symbol = "fnl "

[fossil_branch]
symbol = "fossil "

[gcloud]
symbol = "gcp "

[git_branch]
symbol = "git "

[gleam]
symbol = "gleam "

[golang]
symbol = "go "

[gradle]
symbol = "gradle "

[guix_shell]
symbol = "guix "

[hg_branch]
symbol = "hg "

[java]
symbol = "java "

[julia]
symbol = "jl "

[kotlin]
symbol = "kt "

[lua]
symbol = "lua "

[nodejs]
symbol = "nodejs "

[memory_usage]
symbol = "memory "

[meson]
symbol = "meson "

[nats]
symbol = "nats "

[nim]
symbol = "nim "

[nix_shell]
symbol = "nix "

[ocaml]
symbol = "ml "

[opa]
symbol = "opa "

[os.symbols]
AIX = "aix "
Alpaquita = "alq "
AlmaLinux = "alma "
Alpine = "alp "
Amazon = "amz "
Android = "andr "
Arch = "rch "
Artix = "atx "
CachyOS = "cach "
CentOS = "cent "
Debian = "deb "
DragonFly = "dfbsd "
Emscripten = "emsc "
EndeavourOS = "ndev "
Fedora = "fed "
FreeBSD = "fbsd "
Garuda = "garu "
Gentoo = "gent "
HardenedBSD = "hbsd "
Illumos = "lum "
Kali = "kali "
Linux = "lnx "
Mabox = "mbox "
Macos = "mac "
Manjaro = "mjo "
Mariner = "mrn "
MidnightBSD = "mid "
Mint = "mint "
NetBSD = "nbsd "
NixOS = "nix "
Nobara = "nbra "
OpenBSD = "obsd "
OpenCloudOS = "ocos "
openEuler = "oeul "
openSUSE = "osuse "
OracleLinux = "orac "
Pop = "pop "
Raspbian = "rasp "
Redhat = "rhl "
RedHatEnterprise = "rhel "
RockyLinux = "rky "
Redox = "redox "
Solus = "sol "
SUSE = "suse "
Ubuntu = "ubnt "
Ultramarine = "ultm "
Unknown = "unk "
Uos = "uos "
Void = "void "
Windows = "win "

[package]
symbol = "pkg "

[perl]
symbol = "pl "

[php]
symbol = "php "

[pijul_channel]
symbol = "pijul "

[pulumi]
symbol = "pulumi "

[purescript]
symbol = "purs "

[python]
symbol = "py "

[quarto]
symbol = "quarto "

[raku]
symbol = "raku "

[ruby]
symbol = "rb "

[rust]
symbol = "rs "

[scala]
symbol = "scala "

[spack]
symbol = "spack "

[solidity]
symbol = "solidity "

[status]
symbol = "[x](bold red) "

[sudo]
symbol = "sudo "

[swift]
symbol = "swift "

[typst]
symbol = "typst "

[terraform]
symbol = "terraform "

[zig]
symbol = "zig "
```
Vídeo que utilizei de base:
[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/AK2JE2YsKto/0.jpg)](https://www.youtube.com/watch?v=AK2JE2YsKto)

### Extras

Autocomplete no powershell 
```bash
Install-Module -Name PSReadLine -AllowClobber -Force
```
