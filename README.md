# dwm
Suckless Dynamic Window Manager

git clone https://git.suckless.org/dwm

cd ../dwm

## Patches
curl -O https://dwm.suckless.org/patches/actualfullscreen/dwm-actualfullscreen-20211013-cb3f58a.diff

curl -O https://dwm.suckless.org/patches/backlight/dwm-backlight-20241021-351084d.diff

curl -O https://dwm.suckless.org/patches/fibonacci/dwm-fibonacci-20200418-c82db69.diff

## Build
patch -p1 < dwm-actualfullscreen-20211013-cb3f58a.diff

patch -p1 < dwm-backlight-20241021-351084d.diff

patch -p1 < dwm-fibonacci-20200418-c82db69.diff

nvim config.def.h

	copy modkey togglebar and replace it with togglefullscr
  
	up/down brightness > replace xbacklight with brightnessctl set 5+/- (xev to get keyboard inputs)
