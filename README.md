# conky_rc

Install conky:
```
ArchLInux:
sudo pacman -S conky
Debian:
sudo apt install conky-all
```
The conky rc file to show the system info
You need to setup the network interface section `conky.text`

- clone the repo to `$HOME`
`git clone https://github.com/ihexon/conky_rc ~/conky_rc`

- modify conky.conf

```
${if_existing /proc/net/route wls8}\
${image $HOME/.config/conky/up.png -p 368,183 -s 20x20}${offset 400}${voffset 8}${color1}${upspeed wls8}${goto 470}${color6}/ ${color6}${totalup enp2s0}
${image $HOME/.config/conky/dwn.png -p 368,212 -s 20x20}${offset 400}${voffset 8}${color1}${downspeed wls8}${goto 470}${color6}/ ${color6}${offset 3}${totaldown enp2s0}\
${else}\
${image $HOME/.config/conky/up.png -p 368,212 -s 20x20}${offset 400}${voffset 8}${color1}${upspeed lo}${goto 470}${color6}/ ${color6}${totalup wlan0}
${image $HOME/.config/conky/dwn.png -p 368,212 -s 20x20}${offset 400}${voffset 8}${color1}${downspeed lo}${goto 470}${color6}/ ${color6}${offset 3}${totaldown wlan0}${endif}
```

- copy the "\*.png" to ~/.config/conky:

`cp ~/conky_rc/asster/*.png  ~/.config/conky`

- Start test
`conky -c ~/conky_rc/conky.conf`

