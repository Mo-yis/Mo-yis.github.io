---
layout: posts
title: GNOME 个人配置
---


# 在 Firefox 中安装扩展 GNOME Shell integration

[GNOME Shell integration](https://addons.mozilla.org/en-US/firefox/addon/gnome-shell-integration/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search)




# 打开 GNOME Shell extensions 网站, 安装并启用以下扩展

- AppIndicator and KStatusNotifierItem Support (by 3v1n0)
- Bing Wallpaper (by neffo)
- Clipboard Indicator (by Tudmotu)
- Dash to Panel (by charlesg99):

```bash
[/]
animate-appicon-hover=true
animate-appicon-hover-animation-extent={'RIPPLE': 4, 'PLANK': 4, 'SIMPLE': 1}
appicon-margin=4
appicon-padding=2
available-monitors=[1, 0]
dot-position='TOP'
dot-style-focused='DOTS'
focus-highlight=true
focus-highlight-dominant=false
hide-overview-on-startup=false
hotkeys-overlay-combo='TEMPORARILY'
intellihide=false
intellihide-animation-time=200
intellihide-behaviour='FOCUSED_WINDOWS'
intellihide-close-delay=400
intellihide-enable-start-delay=2000
intellihide-hide-from-windows=false
intellihide-key-toggle=['<Super>i']
intellihide-key-toggle-text='<Super>i'
intellihide-only-secondary=false
intellihide-pressure-threshold=100
intellihide-pressure-time=1000
intellihide-show-in-fullscreen=false
intellihide-use-pressure=false
isolate-workspaces=false
leftbox-padding=-1
multi-monitors=false
panel-anchors='{"0":"MIDDLE","1":"MIDDLE"}'
panel-element-positions='{"0":[{"element":"showAppsButton","visible":true,"position":"stackedTL"},{"element":"activitiesButton","visible":false,"position":"stackedTL"},{"element":"leftBox","visible":true,"position":"stackedTL"},{"element":"taskbar","visible":true,"position":"stackedTL"},{"element":"centerBox","visible":true,"position":"stackedBR"},{"element":"rightBox","visible":true,"position":"stackedBR"},{"element":"dateMenu","visible":true,"position":"stackedBR"},{"element":"systemMenu","visible":true,"position":"stackedBR"},{"element":"desktopButton","visible":true,"position":"stackedBR"}],"1":[{"element":"showAppsButton","visible":true,"position":"stackedTL"},{"element":"activitiesButton","visible":false,"position":"stackedTL"},{"element":"leftBox","visible":true,"position":"stackedTL"},{"element":"taskbar","visible":true,"position":"stackedTL"},{"element":"centerBox","visible":true,"position":"stackedBR"},{"element":"rightBox","visible":true,"position":"stackedBR"},{"element":"dateMenu","visible":true,"position":"stackedBR"},{"element":"systemMenu","visible":true,"position":"stackedBR"},{"element":"desktopButton","visible":true,"position":"stackedBR"}]}'
panel-lengths='{"0":100,"1":100}'
panel-positions='{"0":"TOP","1":"TOP"}'
panel-sizes='{"0":24,"1":24}'
primary-monitor=1
show-appmenu=true
show-apps-icon-file=''
show-favorites-all-monitors=true
status-icon-padding=-1
stockgs-keep-top-panel=false
trans-bg-color='#33d17a'
trans-panel-opacity=0.20000000000000001
trans-use-custom-bg=false
trans-use-custom-gradient=false
trans-use-custom-opacity=true
trans-use-dynamic-opacity=true
tray-padding=-1
window-preview-title-position='TOP'
```

- Light/Dark Theme Switcher (by fthx)
- Notes (by Maestroschan)
- Sound Input & Output Device Chooser (by kgshank)
- system-monitor-next (by mgalgs)
- VirtualBox applet (by eugene-rom)




# 安装字体

- 复制字体到 `~/.local/share/fonts` 文件夹下
- 多个字体可能会影响使用
- 常用字体:
    - `simkai.ttf`: KaiTi, 楷体
    - `simsun.ttc`: SimSun, 宋体

