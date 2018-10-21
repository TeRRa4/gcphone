### [Downloads page](https://github.com/N3MTV/gcphone/releases)

<h2 align="center">Phone for FiveM</h2>

![Image of gcphone1](https://i.imgur.com/naTiBgI.png)
![Image of gcphone2](https://i.imgur.com/LAicovK.png)
![Image of gcphone3](https://i.imgur.com/imWPohA.png)
![Image of gcphone4](https://i.imgur.com/rzWdDMy.png)
![Image of gcphone5](https://i.imgur.com/9h7eiI8.png)


## Features
  - Contact list
  - Send
  - Voice calls
  - Anonymous calls
  - Bank Application
  - Anonymous chat applications
  - Stock exchange applications
  - Phone and background options


## Configuration


### Edit file /html/static/config/config.json
```json
{
  "//": "Phone network name",
  "reseau": "Gannon",
  
  "//": "Main color of the phone",
  "themeColor": "#303f9f",

  "//": "List of colours for the contacts",
  "colors": [
    "#EF5350",
    "#EC407A",
    "#AB47BC",
    "#7E57C2",
    "#5C6BC0",
    "#42A5F5",
    "#29B6F6",
    "#26C6DA",
    "#26A69A",
    "#66BB6A",
    "#9CCC65",
    "#D4E157",
    "#FFCA28",
    "#FFA726",
    "#FF7043",
    "#8D6E63",
    "#78909C"
  ],

  "//": "If false, add a dash '-' in the number (###-####)",
  "useFormatNumberFrance": false,

  "//": "useWebRTCVocal: false => Calls with GTA channels",
  "//": "useWebRTCVocal: true  => Calls using WebRTC",
  "useWebRTCVocal": true,

  "//": "TURN server config",
  "RTCConfig": {
    "iceServers": [{
      "urls": ["turn:gannon.ovh"],
      "username": "jojo",
      "credential": "pass"
    }]
  },


  "//": "List of wallpapers available, location => /html/static/img/background",
  "background" : {
    "Calvin & Hobbes": "back001.jpg",
    "Destiny": "back002.jpg",
    "Stormtrooper": "back003.jpg",
    "Custom URL": "URL"
  },
  "//": "Default Wallpaper",
  "background_default": {
    "label": "Calvin & Hobbes",
    "value": "back001.jpg"
  },

  "//": "List of available phones, location => /html/static/img/coque",
  "coque": {
    "Sansumg S8": "s8.png",
    "Iphone X": "iphonex.png",
    "Brick Base": "base.png",
    "Transparent": "transparent.png"
  },
  "//": "Default phone",
  "coque_default": {
    "label": "Sansumg S8",
    "value": "s8.png"
  },

  "//": "Service call config",
  "serviceCall": [
    {

      "//": "Item name",
      "display": "Police",

      "//": "Optional: colour to use",
      "backgroundColor": "red",

      "//": "Optional: image to use",
      "icon": "/html/static/img/icons_app/bank.png",

      "//": "List of possible actions",
      "subMenu": [
        {
          "//": "Title of the action",
          "title": "Send a message",

          "//": "Name of the event trigger when in use",
          "eventName": "esx_addons_gcphone:call",

          "//": "Optional: Parameter 'data' sent with the event",
          "type": {
            "number": "police"
          }
        },
        {
          "title": "Call the standard",
          "eventName": "gcphone:autoCallNumber",
          "type": {
            "number": "911"
          }
        }
      ]
    },
    {
      "display": "Ambulance",
      "backgroundColor": "red",
      "subMenu": [
        {
          "title": "Send a message",
          "eventName": "esx_addons_gcphone:call",
          "type": {
            "number": "ambulance"
          }
        }
      ]
    }
  ],

  "//": "Application configs",
  "apps": [
    {
      "//": "Name of app",
      "name": "Phone",

      "//": "App icon",
      "icons": "/html/static/img/icons_app/call.png",

      "//": "Route of the application, DO NOT MODIFY",
      "routeName": "appels",

      "//": "If true, the application will be available on the home page",
      "inHomePage": true,

      "//": "If false, app is not visible",
      "enabled": true
    },
    {
      "name": "Messages",
      "icons": "/html/static/img/icons_app/sms.png",
      "routeName": "messages",
      "inHomePage": true,

      "//": "Reference to the store, to display a chip under the icon of the app",
      "puceRef": "nbMessagesUnread",
    },
    {
      "name": "Contacts",
      "icons": "/html/static/img/icons_app/contacts.png",
      "routeName": "contacts",
      "inHomePage": true
    },
    {
      "name": "Settings",
      "icons": "/html/static/img/icons_app/settings.png",
      "routeName": "parametre",
      "inHomePage": true
    },
    {
      "name": "Bank",
      "icons": "/html/static/img/icons_app/bank.png",
      "routeName": "bank",
      "inHomePage": false
    },
    {
      "name": "Stocks",
      "icons": "/html/static/img/icons_app/bourse.png",
      "routeName": "bourse",
      "enabled": true
    },
    {
      "name": "Photo",
      "icons": "/html/static/img/icons_app/photo.png",
      "routeName": "photo"
    },
    {
      "name": "Dark Chat",
      "icons": "/html/static/img/icons_app/tchat.png",
      "routeName": "tchat"
    }
  ]
}

```
*Do not forget to add the new files in __ressource.lua*


* You can edit the sounds in \ html \ static \ sound
* The shells must be 1000x500 px, The screen area is center size 800 * 400
* Bank & Exchange applications are configured according to your script

### Fixed extensions are configurable in gcphone / config.lua
```LUA
--[[
  Be careful not to use a number that conflicts with a player
--]]
FixePhone = {
  -- Police station
  ['911'] = { name =  "Central Police", coords = { x = 441.2, y = -979.7, z = 30.58 } },
  
  -- Cabin near the police station
  ['008-0001'] = { name = "Phone Box", coords = { x = 372.25, y = -965.75, z = 28.58 } },
}
```




## License
[GNU v3](https://opensource.org/licenses/gpl-3.0.html)

Jonathan (Gannon) D
