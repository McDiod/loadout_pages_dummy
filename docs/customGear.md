# customGear
`customGear` is a functionality included in GRAD Loadout that allows players to customize their loadout based on a set of options. By default a player can `ACE-Selfinteract >> Equipment >> Customize loadout`, for a certain time after his loadout was applied.

## Configuration
There are a set of config parameters that can be used to define how `customGear` will behave (see [Configuration](configuration.md)).

### customGear
This parameter sets when exactly a player can access the `customGear` interface via his selfinteraction menu.

* -1 to disable entirely
* number to allow for this value in seconds after last loadout application
* statement to allow while this returns `true`, parameters are `[unit]`

**Example 1:**
```sqf
class Loadouts {
    // players can access the customGear interface for 5 minutes after last loadout application
    customGear = 300;
};
```

**Example 2:**
```sqf
class Loadouts {
    // players can access the customGear interface while closer than 100 to the BLUFOR respawn marker
    customGear = "(_this select 0) distance2D (getMarkerPos "respawn_west") < 100";
};
```

### customGearAllowedCategories
This parameter sets what categories players can customize (e.g. only vest and uniform). By default these are all supported categories.

**Example:**
```sqf
class Loadouts {
    // players can only customize uniform, vest, primary weapon and optic
    customGearAllowedCategories[] = {
        "uniform",
        "vest",
        "primaryWeapon",
        "primaryWeaponOptics"
    };
};
```

## Pictures

The `customGear` interface is reminiscent of BI's virtual arsenal:
![](https://i.imgur.com/FNN54BO.jpg)
