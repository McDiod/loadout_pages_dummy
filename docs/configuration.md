# Configuration
You can configure GRAD Loadout by adding the `Loadouts` class to your `description.ext`. This is entirely optional, as all parameters have default values.

## Parameters

Parameter | Default Value | Description
----------|---------------|------------
asd       | asd           | asd

## Example

```sqf
class Loadouts {
    baseDelay = 10;
    perPlayerDelay = 1;
    handleRadios = 0;
    resetLoadout = 1;
    customGear = 300;
};
```
