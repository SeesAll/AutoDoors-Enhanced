# Changelog

## v3.3.14

### Fixed
- Corrected compile error from an intermediate modernization pass caused by an extra closing brace.
- Confirmed compile-successful version for testing and distribution.

### Notes
- This is the corrected release build intended for use.

---

## v3.3.13

### Changed
- Performed a second modernization pass to further clean up the codebase.
- Reduced repetition in command handling.
- Added helper methods to simplify door-specific and door-type-specific settings logic.
- Improved internal structure for maintainability.
- Improved controller-linked door tracking to a more efficient lookup approach.

### Notes
- This build was part of the modernization process but was superseded by v3.3.14 due to a compile issue.

---

## v3.3.12

### Added
- Added fallback support for newly introduced Armored Ladder Hatches:
  - `floor.ladder.hatch.toptier`
  - `floor.triangle.ladder.hatch.toptier`

### Changed
- Improved internal handling for supported door discovery.
- Added safer parsing and guard handling.
- Improved door-controller exclusion logic for better runtime efficiency.
- Cleaned up internal caching behavior.

### Notes
- This was the first modernization and compatibility update pass.

---

## Summary of differences from the original

Compared to the original Auto Doors release, the modernized version:
- supports the new Armored Ladder Hatch content
- improves door-controller related lookup efficiency
- cleans up and modernizes portions of the codebase
- keeps the original feature set and usage style intact wherever practical
- is easier to maintain going forward
