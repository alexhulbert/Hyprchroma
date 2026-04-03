# Hyprchroma

> [!IMPORTANT]  
> This project has been merged into [upstream](https://github.com/micha4w/Hypr-DarkWindow).
> Use it with:
> ```conf
> windowrule = darkwindow:shade chromakey bkg=[0.066 0.066 0.105],match:class firefox
> bind = $mainMod, O, darkwindow:shadeactive, chromakey bkg=[0.175, 0.175, 0.175] targetOpacity=0.5
> ```


![2024-10-18-000536_hyprshot](https://github.com/user-attachments/assets/d47d78e7-5ddd-4637-83d4-6a8a7be2e0ce)

Hyprchroma is a Hyprland plugin that applies a chromakey effect for global window background transparency without affecting readability

## Configuration
```conf
# hyprland.conf
windowrulev2 = plugin:chromakey,fullscreen:0
chromakey_background = 7,8,17
```

Also adds 2 Dispatches `togglewindowchromakey WINDOW` and `togglechromakey` (for the active window)

## Installation

### Hyprland >= v0.36.0
We now support Nix, wooo!

### Hyprpm

outputs = {
  home-manager,
  hypr-darkwindow,
  ...
}: {
  ... = {
    home-manager.users.micha4w = {
      wayland.windowManager.hyprland.plugins = [
        hypr-darkwindow.packages.${pkgs.system}.Hypr-DarkWindow
      ];
    };
  };
}
```

> [!NOTE]
> In this example `inputs.hypr-darkwindow.url` sets the tag, Make sure that tag matches your Hyprland version.


### Hyprland >= v0.34.0
Install using `hyprpm`
```sh
hyprpm add https://github.com/alexhulbert/Hyprchroma
hyprpm enable hyprchroma
hyprpm reload
```

### Nix

For nix instructions, refer to the parent repository.
