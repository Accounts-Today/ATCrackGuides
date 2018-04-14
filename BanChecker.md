# ATCrack Ban Checker
The atcrack ban checker is a unique addon for ATCrack that allows you to check bans for any server, but it can be a bit difficult to configure, so here is a guide on how to do so.
## How It Works
The Ban Checker is configured using a `bans.json` in the same directory as `Cracker.jar` file. Both servers and their associated details are placed in this file, and it is the file atcrack will use when checking for bans on servers
## The bans.json file
```es6
{
  "request_change":false, //Indicates whether your proxies change every request (I.E storm proxes). RSocks for instance are backconnect, but do not change IP every request, therefore for RSocks this would be disabled.
  "servers": [
    {
      "ip": "us.mineplex.com:25565",
      "name": "Mineplex",
      "banKeys": [
        "ban"
      ]
    },
    {
      "ip": "mc.hypixel.net:25565",
      "name": "Hypixel",
      "banKeys": [
        "ban"
      ],
      "match": true
    }
  ],
  "proxies": [
    "163.172.48.109:15003",
    "163.172.48.117:15003",
    "163.172.48.119:15003",
    "163.172.48.121:15003",
    "163.172.48.109:15004",
    "163.172.48.117:15004",
    "163.172.48.119:15004",
    "163.172.48.121:15004"
  ]
}
```
This is an example bans.json file. In here, we configure what servers to use and some additional proxies. The servers we are checking are `Mineplex` and `Hypixel`. The `Proxies` segment is for special proxies used during checking. Note, you **only need to do specify additional proxies** if `reqChange` is true..

### Server parts
`IP` - The IP and Port of the server you wish to check

`Name` - The simple name for this server, if one isnt provided then the IP will be used

`Ban Keys` - A list of strings indicating a ban. We use this so accounts that are blocked for proxies aren't miss matched.

`Match` - An optional parameter instructing ATCrack how to connect to some specific servers. In general, you won't have to touch this. Basically, match indicates that the authentication and connecting IP need to match for the server to work (Like how Hypixel blocks MCLeaks). Match tells ATCrack to re authenticate using one of the special proxies, and connect with that to bypass the block.

# And that's it! If you need any help, DM jp.
