<img src="https://vitalpoint.ai/wp-content/uploads/2020/06/near_logo-1.png"  width="128" height="33">

---
# How to set up a telegram bot for Monitoring Alerts

Telegram is one of the most popular messengers and it may be very useful to check your server and node health.

# What this bot can do?

###  Monitoring

 1. CPU load 
 2. RAM load
 3. Network

### Historical data
 1. CPU Utilization
 2. RAM Load
 3. Disk I/O
 4. Network perfomance 
 5. Ping test 

### Alert
 1. High CPU Utilization
 2. High RAM load
 3. Network degradation

### Server
 1. Check CPU load
 2. Check RAM load
 3. Check disk usage
 4. Check disk i/o
 5. Check server ping
 6. Alalyze server traceroute
 7. Get top processes
 8. Check uptime
 9. Check network load
 10. Make a speedtest

### Near validator tools and alerts
 1. Alert if node is down
 2. Alert if node is out of sync
 3. Validator info:
    - Pool name
    - Pubkey
    - Stake
    - Blocks produced and
 4. Near logs (last 10 lines).
 

### Installation
 1. Create telegram bot and get Api Token
 2. Send to your new bot command /start
 3. Clone bot to server
```sh
cd $HOME && git clone -v https://github.com/ama31337/serverbot.git && cd ./serverbot && chmod +x ./installsbot.sh
```
 4. Open ./config.py and insert your bot API and your telegram id.
 5. Run installation script
```sh
./installsbot.sh
```
### Update
 1. Backup your old config and pull changes from git
```sh
cd $HOME/serverbot && mv config.py config.py.bak && git pull
source /home/$USER/.bash_aliases
```
 2. Compare the configs and adjust if necessary
 3. Restart bot
```sh
botstop
botstart
```

### Start, stop or check bot status
If you make any changes in config you need to restart your bot. To start, stop or check status you can use commands in bash:
```sh
botstart
botstop
botstatus
```

### What to do if something not working?
If you get History load error, remove bot files from /tmp
```sh
sudo rm -rf /tmp/*.log
sudo rm -rf /tmp/*.png
```
Find in bot.py telebot.logger.setLevel(logging.ERROR) and change ERROR to DEBUG, restart serverbot service and execute
```sh
$ journalctl -e -u serverbot > ~/serverbot/servicelog.log
```

New features added!
Check your validator node health and alert in emergency cases.
Check your pool info, current and proposals validators.
All networks are supported: betanet, testnet, guidnet, mainnet.

<img src="https://github.com/ama31337/neartips/blob/master/manuals/near_node_alert.png">

<img src="https://github.com/ama31337/neartips/blob/master/manuals/serverbot.gif">

If bot was helpful to you, feel free to donate a tip --> [@31337.near](https://explorer.near.org/accounts/31337.near)
Or stake with us --> [@lux.poolv1.near](https://explorer.near.org/accounts/lux.poolv1.near)
