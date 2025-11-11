# dwm
Suckless Dynamic Window Manager

git clone https://git.suckless.org/dwm

cd ../dwm

## Patches
curl -O https://dwm.suckless.org/patches/actualfullscreen/dwm-actualfullscreen-20211013-cb3f58a.diff

curl -O https://dwm.suckless.org/patches/backlight/dwm-backlight-20241021-351084d.diff

curl -O https://dwm.suckless.org/patches/fibonacci/dwm-fibonacci-20200418-c82db69.diff

curl -O https://dwm.suckless.org/patches/alpha/dwm-alpha-20230401-348f655.diff

## Build
patch -p1 < patches/dwm-actualfullscreen-20211013-cb3f58a.diff

patch -p1 < patches/dwm-backlight-20241021-351084d.diff

patch -p1 < patches/dwm-fibonacci-20200418-c82db69.diff

patch -p1 < patches/dwm-alpha-20230401-348f655.diff

nvim config.def.h

	copy modkey togglebar and replace it with togglefullscr
  
	up/down brightness > replace xbacklight with brightnessctl set 5+/- (xev to get keyboard inputs)
