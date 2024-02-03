# i3blocks.conf
i3blocks configuration file

# i3blocks configuration file
#
# The i3blocks man page describes the usage of the binary,
# and its website describes the configuration:
#
#     https://vivien.github.io/i3blocks

# Global properties
separator=true
separator_block_width=15


[greetings]
color=#f5af19
command=echo "Hello, ArNahid!"
interval=once

[time]
command=date '+%d-%m-%y %H:%M:%S'
interval=1
color=#09ff00

[volume]
label=Volume:
command=amixer get Master | grep -E -o '[0-9]{1,3}?%' | head -1
interval=once
signal=1
# use 'pkill -RTMIN+1 i3blocks' after changing the volume



[block1]
baz=qux

# This is a comment
[block2]
quux= quuz


# Block with a fixed width
[aligned]
min_width=100
align=center


# Fetch the public IP address only on startup
[public-ip]
command=wget -qO - icanhazip.com
interval=once

[ip]
command=hostname -i | awk '{ print "IP:" $1 }'
interval=once
color=#91E78B

[caps-lock]
command=xset -q | grep Caps | awk '{ print $2, $3, $4 }'
interval=once
signal=10

# Restart i3 on click
[restart]
full_text=Restart
command=i3-msg -q restart
#interval=0







