
# CS2 Config Formatting

## CS2Fixes Entwatch

```json
[
    {
        "name": "Item Name",            // Name of item that appears in chat
        "shortname": "Short Name",      // Name of item that appears on the HUD
        "hammerid": "",                 // Hammerid of the weapon entity
        "message": true,                // Whether to show pickup/drop messages in chat
        "ui": true,                     // Whether to show this item on the HUD
        "transfer": true,               // Whether to allow this item to be transferred (this auto detects false for knife items)
        "color": "",                    // Color of the item for chat messages (see list of colors)
        "triggers": [""],               // Array of hammerids of any triggers that this item is associated with
        "templated": true,              // Whether the entity of this handler is templated with the item weapon, (auto detected if not specified)
        "handlers": [
            {
                "name": "Handler",          // extra name to show in chat when used e.g. XXX has used Item Name (Handler)
                "type": "button",           // "button", 
                                            // "counterdown" - counter stops OnHitMin
                                            // "counterup" - counter stops OnHitMax
                                            // (anything else is ignored)
                "hammerid": "",             // hammerid of the entity
                "event": "OnPressed",       // Name of the output, counterup/down types always force "OutValue"
                "mode": 2,                  // Mode of the handler
                                            //  0/1 = None
                                            //  2 = Cooldown,           3 = MaxUses (cooldown between each)
                                            //  4 = CooldownAfterUses,  5 = CounterValue
                "offset": [5,-9],           // ADDS the specified offset to counter values, 
                                            // First number is counter value, Second is counter max
                "cooldown": 60,             // Cooldown duration if mode = 2,3,4
                "maxuses": 0,               // Maxuses if mode = 3,4
                "message": true,            // Whether to show when this is used in chat
                "ui": true,                 // Whether to track this handler on the HUD
                "templated": true           // Whether the entity of this handler is templated with the item weapon, 
            }                               //  (this will attempt to auto detect if not specified)
        ]
    }
]```

### Clean Template

```json
[
    // Full Config
    {
        "name": "",
        "shortname": "",
        "hammerid": "",
        "message": true,
        "ui": true,
        "transfer": true,
        "color": "",
        "triggers": [""],
        "templated": true,
        "handlers": [
            {
                "name": "Handler",
                "type": "button",
                "hammerid": "",
                "event": "OnPressed",
                "mode": 0,
                "cooldown": 0,
                "maxuses": 0,
                "offset": [0,0],
                "message": true,
                "ui": true,
                "templated": true
            }
        ]
    },
    // Regular button
    {
        "name": "",
        "shortname": "",
        "hammerid": "",
        "message": true,
        "ui": true,
        "transfer": true,
        "color": "",
        "triggers": [""],
        "handlers": [
            {
                "type": "button",
                "hammerid": "",
                "event": "OnPressed",
                "mode": 0,
                "cooldown": 0,
                "maxuses": 0,
                "message": true,
                "ui": true
            }
        ]
    },
    // Button and filter separate (most reliable)
    {
        "name": "",
        "shortname": "",
        "hammerid": "",
        "message": true,
        "ui": true,
        "transfer": true,
        "color": "",
        "triggers": [""],
        "handlers": [
            {
                "type": "button",
                "hammerid": ""
            },
            {
                "hammerid": "",
                "event": "OnPass",
                "mode": 0,
                "cooldown": 0,
                "maxuses": 0,
                "message": true,
                "ui": true
            }
        ]
    },
]
```

### Available Colors

- white, default
- darkred
- team
- green
- lightgreen
- olive
- red
- gray, grey
- yellow
- silver
- blue
- darkblue
- purple, pink
- red2
- orange, gold