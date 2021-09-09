# Oh-my-posh

You need have installed newly versions of [powershell](https://docs.microsoft.com/pt-br/powershell/scripting/install/installing-powershell-core-on-windows) and the official termianl app from windows: [terminal](https://www.microsoft.com/pt-br/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab).

1. First thing to do is install `CaskaydiaCove NF` font [link](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/CascadiaCode.zip?WT.mc_id=-blog-scottha).
2. Select `CaskaydiaCove NF` on powershell sction settings.json of Windows Terminal:
```json
{
    "fontFace": "CaskaydiaCove NF", // just copy this line
    "guid": "{574e775e-4f2a-5b96-ac1e-a2962a402336}",
    "hidden": false,
    "name": "PowerShell",
    "source": "Windows.Terminal.PowershellCore"
}
```
4. Install Oh my posh on powershell and choose theme file decribed at end of this file:

```powershell
Install-Module oh-my-posh -Scope CurrentUser

Set-PoshPrompt -Theme .\ohmyposh.json
```
5. Install terminal Icons:

```powershell
Install-Module -Name Terminal-Icons -Repository PSGallery

Import-Module -Name Terminal-Icons
```
6. Save configs on `$PROFILE` file:

type: `code $PROFILE`

```
Set-PoshPrompt -Theme .\ohmyposh.json
Import-Module -Name Terminal-Icons
```

now save the file

Oh my posh Config file
```json
{
    "final_space": true,
    "console_title": true,
    "console_title_style": "folder",
    "blocks": [
        {
            "type": "prompt",
            "alignment": "left",
            "horizontal_offset": 0,
            "vertical_offset": 0,
            "segments": [
                {
                    "type": "path",
                    "style": "diamond",
                    "powerline_symbol": "",
                    "invert_powerline": false,
                    "foreground": "#ffffff",
                    "background": "#ff479c",
                    "leading_diamond": "",
                    "trailing_diamond": "",
                    "properties": {
                        "prefix": "  ",
                        "style": "folder"
                    }
                },
                {
                    "type": "git",
                    "style": "powerline",
                    "powerline_symbol": "",
                    "invert_powerline": false,
                    "foreground": "#193549",
                    "background": "#fffb38",
                    "leading_diamond": "",
                    "trailing_diamond": "",
                    "properties": {
                        "display_status": true,
                        "display_stash_count": true,
                        "display_upstream_icon": true
                    }
                },
                {
                    "type": "dotnet",
                    "style": "powerline",
                    "powerline_symbol": "",
                    "invert_powerline": false,
                    "foreground": "#ffffff",
                    "background": "#6CA35E",
                    "leading_diamond": "",
                    "trailing_diamond": "",
                    "properties": {
                        "display_version": true,
                        "prefix": "  "
                    }
                },
                {
                    "type": "root",
                    "style": "powerline",
                    "powerline_symbol": "",
                    "invert_powerline": false,
                    "foreground": "#ffffff",
                    "background": "#ffff66",
                    "leading_diamond": "",
                    "trailing_diamond": "",
                    "properties": null
                },
                {
                    "type": "exit",
                    "style": "powerline",
                    "powerline_symbol": "",
                    "invert_powerline": false,
                    "foreground": "#ffffff",
                    "background": "#2e9599",
                    "leading_diamond": "",
                    "trailing_diamond": "",
                    "properties": {
                        "always_enabled": true,
                        "color_background": true,
                        "display_exit_code": false,
                        "error_color": "#f1184c",
                        "prefix": " "
                    }
                }
            ]
        }
    ]
}
```
