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
    "copyFormatting": "none",
    "copyOnSelect": false,
    "defaultProfile": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
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
            "colorScheme": "xcad",
            "cursorShape": "vintage",
            "experimental.retroTerminalEffect": true,
            "font": 
            {
                "face": "JetBrainsMono Nerd Font"
            },
            "icon": "C:\\Users\\Fam\u00edlia\\Downloads\\Walter White Costume -  Breaking Bad.jpeg",
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

1) choco install starship
2) execute o comando code $PROFILE e cole o comando Invoke-Expression (&starship init powershell), agora toda vez que iniciar o seu powershell, ele será executado automaticamente.
3) Execute o comando mkdir -p ~/.config, logo em seguida crie o arquivo com o nome starship.toml, e dentro dele cole a seguinte configuração:

```bash
format = """\
[╭╴](fg:arrow)\
$username\
$os\
$git_branch\
(\
    at \
    $directory\
)\
$cmd_duration\
(\
    via \
    $python\
    $conda\
    $nodejs\
    $c\
    $rust\
    $java\
)
[╰─](fg:arrow)$character\
"""
# Add the modules you need

# Disable the blank line at the start of the prompt
add_newline = true


palette = "normal"


[palettes.normal]
arrow = "#333533"
os = "#16f4d0"
os_admin = "#e4ff1a"
directory = "#9ffff5"
time = "#bdfffd"
node = "#a5e6ba"
git = "#f17f29"
git_status = "#DFEBED"
python = "#edf67d"
conda = "#70e000"
java = "#F86279"
rust = "#ffdac6"
clang = "#caf0f8"
duration = "#ce4257"
text_color = "#EDF2F4"
text_light = "#26272A"

# I disabled some modules (Rust, Java...) since some things aren't installed in my machine, enable them if you need.

[username]
style_user = 'bold os'
style_root = 'bold os_admin'
format = '[  $user](fg:$style) '
disabled = false
show_always = true

[os]
format = "on [($name)]($style) "
style = "bold blue"
disabled = true

[os.symbols]
Alpine = " "
Arch = " "
Debian = " "
EndeavourOS = " "
Fedora = " "
Linux = " "
Macos = " "
Manjaro = " "
Mint = " "
NixOS = " "
openSUSE = " "
Pop = " "
SUSE = " "
Ubuntu = " "
Windows = " "

[character]
success_symbol = "[󰍟](fg:arrow)"
error_symbol = "[󰍟](fg:red)"

[directory]
format = "[$path](bold $style)[$read_only]($read_only_style) "
truncation_length = 2
style = "fg:directory"
read_only_style = "fg:directory"
before_repo_root_style = "fg:directory"
truncation_symbol = "…/"
truncate_to_repo = true
read_only ="  "

[time]
disabled = true
format = "at [󱑈 $time]($style)"
time_format = "%H:%M"
style = "bold fg:time"

[cmd_duration]
format = "took [ $duration]($style) "
style = "bold fg:duration"
min_time = 500

[git_branch]
format = "via [$symbol$branch]($style) "
style = "bold fg:git"
symbol = " "

[git_status]
format = '[ $all_status$ahead_behind ]($style)'
style = "fg:text_color bg:git"
disabled = true

[docker_context]
disabled=true
symbol = " "

[package]
disabled=true

[fill]
symbol = " "

[nodejs]
format = "[ $symbol$version ]($style)"
style = "bg:node fg:text_light"
symbol = " "
version_format = "${raw}"
disabled=false

[python]
disabled=false
format = '[ ${symbol}${pyenv_prefix}(${version})( \($virtualenv\)) ]($style)'
symbol = " "
version_format = "${raw}"
style = "bg:python fg:text_light"

[conda]
format = "[ $symbol$environment ]($style)"
style = "bg:conda fg:text_light"
ignore_base = false
disabled = false
symbol = " "

[java]
format = "[ $symbol$version ]($style)"
style = "bg:java fg:text_light"
version_format = "${raw}"
symbol = " "
disabled = true

[c]
format = "[ $symbol($version(-$name)) ]($style)"
style = "bg:clang fg:text_light"
symbol = " "
version_format = "${raw}"
disabled=true

[rust]
format ="[ $symbol$version ]($style)"
style = "bg:rust fg:text_light"
symbol = " "
version_format = "${raw}"
disabled=true
```

Vídeo quee utilizei de base:

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/AK2JE2YsKto/0.jpg)](https://www.youtube.com/watch?v=AK2JE2YsKto)
