[[DevOps]]

ssh to running app
```
fly -a leetcode-bot-2 ssh console -s
```

schedule cron tasks using yacron

## Errors
#fix Getting Error tunnel unavailable for organization

flyctl wireguard list
flyctl wireguard reset
flyctl wireguard remove  # did this for all the listed connections
then flyctl stopped responding to any commands so i:

flyctl auth logout
flyctl auth login