# Remote Stats
The purpose of this task is to send live stats to a server in order to be able to monitor them remotelly from our mobile phone or any other device. Now it is able to show you all your botting sessions, for that you only need to open server once, and activate the task in all DarkBot instances. Note that in order to manage all sessions, the webpage served must to reestablish the connection every time you change from one account to another. So it is not a bug when you go to the details of one account and connection is closed, it is working as intended.

## Dependencies
`RemoteStatsServer.exe`<br>
Needed to serve your web page locally.

`Ngrok.exe`<br>
Needed to be able to access your local server remotelly.
Do not worry about this, as it is included in the server executable file, but it is important for you to know that this software is gonna be downloaded first time you
execute the server.

In order to serve web content and have the same URL for your server indefinetly (for each session), you will need to register at
[Ngrok](https://dashboard.ngrok.com/signup) and obtain your [Ngrok Auth Token](https://dashboard.ngrok.com/get-started/your-authtoken) to configure the plugin.

## Use
1. Configure the task by clicking _Setup_ button in settings
2. Steps: download the server file, select it and register in Ngrok in order to obtain your Auth Token (remember to verify your ngrok account)
3. Paste the Ngrok Auth Token in the setting. I recommend you to let the rest of fields untouched (localhost and port)
4. Go to the top-left DarkBot menu and click _Remote Stats Server_ under _DksPlugin_ separator
5. If the setup is correct, you should be able to click in _Start Server_
6. Once the server is running, it will show a QRCode (contains the URL to the web page)
7. Scan the code and enjoy

## Advanced
In case you want to program your own server. This is the data sended by the plugin to the server defined in settings.

### JSON 
```json
{
    "hero": {
        "x": 8021.437406290944,
        "y": 2104.7512544734773,
        "configuration": "FIRST",
        "hp": 520201,
        "maxHp": 520201,
        "shield": 0,
        "maxShield": 0,
        "hull": 260708,
        "maxHull": 375000,
        "hpPercent": 1,
        "shieldPercent": 1,
        "hullPercent": 0.6952213333333334,
        "username": "ExampleUserName",
        "target": {
            "isValid": true,
            "isEnemy": false,
            "x": 7590.351409407955,
            "y": 1704.147527209273,
            "name": "-=[ Melter ]=- ζ22",
            "hp": 110702,
            "maxHp": 300000,
            "shield": 372711,
            "maxShield": 400001,
            "hpPercent": 0.36900666666666665,
            "shieldPercent": 0.9317751705620736
        }
    },
    "stats": {
        "runningTime": "27:16:06",
        "totalUridium": 822387,
        "earnedUridium": 197984,
        "totalCredits": 502704110,
        "earnedCredits": 115831625,
        "totalHonor": 8753677,
        "earnedHonor": 1763704,
        "totalExperience": 553915750,
        "earnedExperience": 72039260,
        "cargo": 812,
        "maxCargo": 4000,
        "level": 17,
        "ping": 89,
        "runningTimeSeconds": 98166
    },
    "module": {
        "status": "Kekka 1.6.6 beta 21 | attacking | Killing npc S | Npc: 4 2 | Wave 21/46"
    },
    "map": {
        "boundX": 21000,
        "boundY": 13500,
        "name": "GG ζ 3",
        "mapID": "73",
        "portals": [],
        "npcs": [
            {
                "x": 7473.028566655505,
                "y": 1741.1354375972724,
                "name": "-=[ Melter ]=- ζ22"
            },
            {
                "x": 0,
                "y": 0,
                "name": "-=[ Melter ]=- ζ22"
            },
            {
                "x": 0,
                "y": 0,
                "name": "-=[ Melter ]=- ζ22"
            },
            {
                "x": 7590.351409407955,
                "y": 1704.147527209273,
                "name": "-=[ Melter ]=- ζ22"
            }
        ],
        "players": []
    }
}
```
