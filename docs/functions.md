# Functions

## GRAD_Loadout_fnc_factionSetLoadout

You can dynamically alias a faction name and optionally broadcast it over network (parameter 2, bool):

`["BLU_F", "USMC", true] call GRAD_Loadout_fnc_factionSetLoadout;` – thus, you can change loadout presets for your factions. In this example, this would work now:

```
class Loadouts {
    class Faction {
        class USMC {
            class AllUnits {
                backpack = "";
            };
        };
    };
};
```

## GRAD_Loadout_fnc_doLoadoutForUnit

Call this with unit as first parameter to dynamically assign loadout during scenario.

**Example:**

```sqf
[player] call GRAD_Loadout_fnc_doLoadoutForUnit;
```

## GRAD_Loadout_fnc_addReviver

Use to dynamically adjust loadout values. This example adds a bit of randomization to Russian helmets and broadcasts the reviver over network (parameter 2, bool):

**Example:**

```sqf
[
    {
        params ["_value"];
        if (_value == "rhs_6b27m_digi") then {
            _value = selectRandom ["rhs_6b27m_digi", "rhs_6b27m_digi_bala"];
        };
        _value
    },
    "headgear",
    true
] call GRAD_Loadout_fnc_addReviver;
```
