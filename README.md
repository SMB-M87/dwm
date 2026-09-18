# Dynamic Window Manager
See the original dwm [README](./README).

# Setup
	# Clone
	git clone https://git.suckless.org/dwm
	cd ../dwm

	# Patches
	# Toggle fullscreen for a window
	curl -O https://dwm.suckless.org/patches/actualfullscreen/dwm-actualfullscreen-20211013-cb3f58a.diff
	
	# Allows control of brightness by using the dedicated keys
	curl -O https://dwm.suckless.org/patches/backlight/dwm-backlight-20241021-351084d.diff

	# Adds spiral and dwindle window-tiling
	curl -O https://dwm.suckless.org/patches/fibonacci/dwm-fibonacci-20200418-c82db69.diff

	# Allows translucent bars
	curl -O https://dwm.suckless.org/patches/alpha/dwm-alpha-20230401-348f655.diff

	# Apply patches
	patch -p1 < patches/dwm-actualfullscreen-20211013-cb3f58a.diff
	patch -p1 < patches/dwm-backlight-20241021-351084d.diff
	patch -p1 < patches/dwm-fibonacci-20200418-c82db69.diff
	patch -p1 < patches/dwm-alpha-20230401-348f655.diff

	# Change patched config definitions
	nvim config.def.h

	# Copy row
	{ MODKEY,                       XK_b,      togglebar,      		  {0} },	
	# Replace togglebar function with new fullscreen function in copied row
	{ MODKEY,                       XK_b,      togglebarfullscr,      {0} },
	
	# Replace up/downbrightness xbacklight by brightnessctl
	static const char *upbrightness[]   = { "brightnessctl", "set", "5+", NULL };
	static const char *downbrightness[] = { "brightnessctl", "set", "5-", NULL };

	# Update changes
	make clean install
