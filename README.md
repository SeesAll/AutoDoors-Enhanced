# Auto Doors

A maintained and modernized version of the original **Auto Doors** Rust plugin for uMod/Oxide.

This plugin automatically closes supported doors behind players after a configurable delay. It preserves the original feature set and behavior wherever practical, while improving code quality, maintainability, and support for newer Rust content.

## Credits

Original plugin authors:
- Wulf
- lukespragg
- Arainrr
- James
- Bushhy

Modernization and compatibility update:
- SeesAll

## What this version does

Auto Doors automatically closes supported doors after a delay when a player opens them.

It supports:
- global per-player enable/disable
- global per-player delay
- per-door-type overrides
- per-single-door overrides
- optional permission-based access
- optional exclusion of doors connected to door controllers
- persistent player preferences across restarts
- optional wipe-based data reset behavior

## What is different from the original

This updated version keeps the plugin's intended functionality intact, but improves several areas:

### 1. Support for new Rust door content
Added support for the newly introduced **Armored Ladder Hatches**, including fallback handling for:
- `floor.ladder.hatch.toptier`
- `floor.triangle.ladder.hatch.toptier`

This ensures Auto Doors works with the new armored ladder hatch variants even if automatic door discovery does not pick them up correctly on a given server build.

### 2. Performance improvements
The original plugin checked door controllers by scanning tracked manipulators whenever a door opened.

This version improves that logic by using more efficient tracking for controller-linked doors, reducing unnecessary repeated work during door-open events.

### 3. Cleaner and safer code
This version includes low-risk internal cleanup and modernization, including:
- cleaner command handling
- reduced repetition in door setting logic
- safer null handling
- cleaner support-door cache rebuilding
- safer internal parsing and validation paths
- corrected compile issues from intermediate modernization work

### 4. Maintenance-friendly structure
The code is now easier to read, maintain, and extend without changing how players use the plugin.

## Commands

By default:
- `/ad`
- `/autodoor`

### Usage
- `/ad`
  - Enables or disables automatic door closing for the player
- `/ad 5`
  - Sets the player's default auto-close delay
- `/ad single`
  - Enables or disables auto-close for the specific door the player is looking at
- `/ad single 5`
  - Sets the auto-close delay for the specific door the player is looking at
- `/ad type`
  - Enables or disables auto-close for the type of door the player is looking at
- `/ad type 5`
  - Sets the auto-close delay for that type of door
- `/ad all 5`
  - Sets the default delay for all doors and clears per-door/per-type overrides
- `/ad help`
  - Shows help information

## Permission

Optional permission:
- `autodoors.use`

If `Use permissions` is set to `true` in the config, players must have this permission to use Auto Doors.

## Configuration

Key options include:
- `Use permissions`
- `Clear data on map wipe`
- `Allows automatic closing of unowned doors`
- `Exclude door controller`
- `Cancel on player dead`
- `Default enabled`
- `Default delay`
- `Maximum delay`
- `Minimum delay`
- custom chat commands and prefix

## Data storage

The plugin stores player preferences in its data file so settings persist across restarts.

Stored data includes:
- player-wide enable/disable state
- player-wide delay
- per-door overrides
- per-door-type overrides

If configured, data can be cleared on map wipe.

## Compatibility notes

This version is intended as a conservative modernization of the original plugin.

Goals of this update:
- preserve original behavior where possible
- avoid feature removal
- improve maintainability
- improve compatibility with newer Rust content
- avoid risky rewrites that could introduce regressions

## Suggested GitHub repository contents

Recommended files to upload:
- `AutoDoors.cs` or `AutoDoors_3.3.14.cs`
- `README.md`
- `CHANGELOG.md`
- `LICENSE` (if you are publishing under the same terms you are allowed to use)

## Suggested repository short description

Modernized Auto Doors plugin for Rust/uMod with cleaner internals, performance improvements, and Armored Ladder Hatch support.

## Suggested release title

`Auto Doors v3.3.14 - modernization, performance cleanup, and Armored Ladder Hatch support`

## Suggested release notes

This update preserves the original Auto Doors feature set while improving internal structure, maintainability, and compatibility with newer Rust content. It includes support for the new Armored Ladder Hatch variants, internal performance improvements around door controller handling, and general cleanup to make the plugin easier to maintain going forward.
