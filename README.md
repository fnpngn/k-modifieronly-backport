# What
This is a navigation repository as the project requires patching multiple KDE modules.        
This is a private attempt to backport the patches made in KDE that allow to use modifier only key chords as shortcuts.   
The target packages are applied/ubuntu/noble kwin, kglobalaccel, kguiaddons, kwindowsystem

# Why
This is a basic usability feature that was completely inaccessible through integrated tools or any keymapping software.   
It is still inaccessible on Ubuntu LTS due to it using Plasma 5.27 with no backports in sight.  
The default presets for modifier shortcuts in keyboard layout options are not only rigid but also completely break all the other hotkeys that use any of the involved modifiers.  

# Where
## Backports
[kglobalaccel](https://github.com/fnpngn/kglobalaccel-modifieronly-backport)   
[kwin](https://github.com/fnpngn/kwin-modifieronly-backport)   
[kguiaddons](https://github.com/fnpngn/kguiaddons-modifieronly-backport)   
[kwindowsystem](https://github.com/fnpngn/kwindowsystem-modifieronly-backport)   
- - -
## Original changes
[kglobalaccel main PR](https://invent.kde.org/plasma/kglobalacceld/-/merge_requests/44#014186ddf2dd1aa75709115400e25e06ba6e2d47)   
[KGUiAddons allow recording shortcuts](https://invent.kde.org/frameworks/kguiaddons/-/merge_requests/115)   
[kwin forward mouse events](https://invent.kde.org/plasma/kwin/-/merge_requests/5251)   
[kkeyserver add modifiers to keymap](https://invent.kde.org/frameworks/kwindowsystem/-/merge_requests/148)   
- - -
[kglobalaccel Trigger modifier only shortcuts when any modifier is released](https://invent.kde.org/plasma/kglobalacceld/-/merge_requests/53)   
[causes bug](https://invent.kde.org/plasma/kglobalacceld/-/issues/1)    
[reverted here](https://invent.kde.org/plasma/kglobalacceld/-/merge_requests/61)   
- - -
### Other fixes
[explicitly process invalid keycodes ](https://invent.kde.org/plasma/kglobalacceld/-/merge_requests/54)   
[plugins/xcb: correctly handle multiple modifiers in xrecord ](https://invent.kde.org/plasma/kglobalacceld/-/merge_requests/58)   
[plugins/xcb: skip xrecord events when keyboard is grabbed ](https://invent.kde.org/plasma/kglobalacceld/-/merge_requests/60)   
[trigger shortcuts on first key release](https://invent.kde.org/plasma/kglobalacceld/-/merge_requests/62) (cycle through by pressing one key in the chord)


# When
This project is unfinished. Some modules are done, others can not yet be compiled, some only compile without autotests.  
The goal is to port all the initial functionality, resolve tests, then port the further [updates](https://invent.kde.org/plasma/plasma-desktop/-/merge_requests/2342) and [bugfixes](https://bugs.kde.org/show_bug.cgi?id=489187)   
Currently facing issues resolving phantom Qt dependencies that simultaneously do not yet exist and are [deprecated](https://github.com/Zren/material-decoration/issues/60)
