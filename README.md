# Renode with platformio
1. Install Renode
2. Create a project with platformio (this case hifive1 with zephyr)
3. Add this to ini file
```
[env:hifive1]
platform = sifive
framework = zephyr
board = hifive1
monitor_speed = 115200
upload_command = renode -e "include @scripts/single-node/sifive_fe310.resc" -e "machine StartGdbServer 3333 True" -e "sysbus LoadELF @$SOURCE" -e "start"
debug_tool = custom
debug_port = localhost:3333
debug_server = renode
   -e
   include @scripts/single-node/sifive_fe310.resc
   -e
   machine StartGdbServer 3333 True
debug_extra_cmds = monitor start
```
