<p align="center">
  <img width="200" height="200" src="https://github.com/Mark2Mark/mark-zones-plugin/blob/main/.images/Mark-Zones-Icon.png?raw=true">
</p>

# Mark Zones

[![made with heart by Mark Frömberg](https://img.shields.io/badge/made%20with%20%E2%99%A5%20by-mark%20frömberg-F9DE64.svg?style=flat)](https://github.com/Mark2Mark)

A reporter plugin for **Glyphs 3** that displays custom reference zones per master in the Edit View. Define zones by position, thickness, color, overshoot, and name — filtered per script, category, or any combination of glyph properties.

Minimum Glyphs version: build `3062`.

> Do not download directly from here. Please install via GlyphsApp's Plugin Manager.

&nbsp;

<p align="center">
  <img width="" height="" src="https://github.com/Mark2Mark/mark-zones-plugin/blob/main/.images/MarkZones-Hero-Light-Pad.png?raw=true">
  <p align="center">In use with Latin script</p>
</p>

<p align="center">
  <img src="https://github.com/Mark2Mark/mark-zones-plugin/blob/main/.images/MarkZones-Thai.png?raw=true">
  <p align="center">In use with Thai script</p>
</p>


## Features

### Zone Types

- **Thick zones** (pair) — a filled band between a position and a thickness. Bordered by solid lines with a curly brace and label on the left.
- **Line zones** — a dashed horizontal line at a single y-position (thickness = 0).

Both types support overshoots:

- **Thick zone** overshoots extend outward in both directions (above and below the zone).
- **Line zone** overshoots extend upward for positions above 0, downward otherwise.

<p align="center">
  <img width="" height="400" src="https://github.com/Mark2Mark/mark-zones-plugin/blob/main/.images/MarkZones-ThickThin.png?raw=true">
</p>

### Glyph Filtering

Zones are only displayed for glyphs that match the filter. The filter uses a Predicate Editor (like you know from other locations in Glyphs, like Global Guidelines) that lets you combine conditions on:

- **Script** (e.g. Latin, Hangul, Thai)
- **Category** (e.g. Letter, Number, Mark)
- **Subcategory** (e.g. Uppercase, Lowercase, Smallcaps)
- **Name** (contains, begins with, ends with)
- **Case** (uppercase, lowercase, smallCaps, etc.)
- **Tags** (contains)

Combine multiple conditions with **All** (AND) or **Any** (OR) logic.

Note: Legacy zone definitions using the old `Script + Script` syntax are automatically converted to predicate filters when opened in the UI.

### Node and Anchor Highlighting

- **Nodes** in an overshoot region are highlighted with a filled circle. Nodes exactly on the zone border are shown as a filled diamond.
- **Selected nodes** get a larger highlight.
- **Anchors** in an overshoot region are highlighted similarly.
- If a zone is named **"Anchors"**, any anchor that is *not* on one of those zone positions is highlighted in orange as a warning.

--IMAGE HERE

### Zone Dragging

Hold **Cmd** and hover over a zone border to see a grab cursor. Then **Cmd-drag** to reposition the zone edge directly in the Edit View:

- Dragging the **bottom** edge of a thick zone moves the entire zone (position changes, thickness stays).
- Dragging the **top** edge of a thick zone resizes it (position stays, thickness changes).
- Dragging a **line zone** moves it to a new y-position.

While dragging, a dashed preview shows the new position along with live position/thickness labels.

### Zone Editing

**Cmd-double-click** a zone edge in the Edit View to open the Custom Parameter UI as a sheet — pre-filled with the clicked zone's properties. Edit name, color, filter, overshoot, zone positions, or linked glyphs without navigating to Font Info. Cancel discards all changes; OK applies them immediately.

### Linked Glyphs

Each zone can have **linked glyphs** — other glyphs whose outlines are transformed when you drag the zone. Each linked glyph has a **stretch** setting:

- **Stretch** (1): scales the linked glyph proportionally to the zone resize.
- **Raise** (0): moves the linked glyph without stretching, keeping its relative position within the zone.

This is useful for adjusting diacritics or other dependent shapes when changing vertical metrics. This also respects the italic angle and stretches or raises the glyphs along the italic angle.

### Italic Angle Support

All zone rendering respects the master's italic angle. Zones, overshoots, labels, braces, and drag previews are all sheared correctly.

### Mark Zone Center Line

For glyphs in the **Mark** category, a dotted center line is drawn inside thick zones to help with vertical alignment of combining marks.

<p align="center">
  <img width="" height="400" src="https://github.com/Mark2Mark/mark-zones-plugin/blob/main/.images/MarkZones-Center.png?raw=true">
</p>

### Context Menu: "New Mark Zone from Selection"

Right-click in the Edit View to create a new `MarkZones` custom parameter from the current selection's vertical bounds. Instead of silently adding a zone with defaults, the **Custom Parameter UI opens as a sheet** — letting you edit the name, color, overshoot, filter, and zone positions before committing.

- **Cancel** discards the zone entirely — nothing is saved.
- **Apply to all masters** — when the font has multiple masters and the current glyph is compatible across all of them, a checkbox lets you duplicate the zone to every master. Each master gets its own overshoot (from its baseline metric) and zone positions (mapped from the corresponding nodes in that master's layer).

### Per-Master, Per-Parameter Control

- Zones are defined as `MarkZones` custom parameters on font masters in **Font Info > Masters**.
- You can have **multiple zones** within a single parameter (grouped under the same name and color).
- You can have **multiple MarkZones parameters** per master for different groups.
- **Toggle visibility** of any zone group via the custom parameter checkbox — disable it to hide the zones without deleting the definition.
- Zones are hidden when the **Space key** is held or the **Text tool** is active.

&nbsp;

## Custom Parameter UI

Click a `MarkZones` custom parameter to open its editor:

<p align="center">
  <img width="450" src="https://github.com/Mark2Mark/mark-zones-plugin/blob/main/.images/MarkZones-UI-1.png?raw=true">
  <br>
  <em>Custom Parameter editor with simple filter and 2 zones</em>
</p>
<p align="center">
  <img width="450" src="https://github.com/Mark2Mark/mark-zones-plugin/blob/main/.images/MarkZones-UI-2.png?raw=true">
  <br>
  <em>Custom Parameter editor with more complex filter, zones, and linked glyphs</em>
</p>

The dialog has these sections:

| Section | Description |
|---|---|
| **Filter** | Predicate editor for script/category/name conditions |
| **Name** | Display name shown next to the zone in the Edit View |
| **Overshoot** | Overshoot distance in units |
| **Color** | Zone color (with alpha support) |
| **Zones** | Table of zone positions and thicknesses |
| **Linked Glyphs** | Table of glyph names and stretch/raise behavior |

&nbsp;

## Tips

- It is best to hide GlyphsApp's built-in metrics (`Cmd + Shift + M`), because this plugin draws its own metric lines.
- Name a zone **"Anchors"** to get warnings for anchors that aren't on a defined zone position.
- Group related zones (e.g. all x-height zones) into one parameter to share a name and color.
- Use separate parameters for unrelated zone groups (e.g. uppercase vs lowercase).
- You can also add a Mark Zones CP from Scratch by clicking the + Button in the Custom Parameters List in Font Info, typing `MarkZones` and hitting enter. 

&nbsp;

## Custom Parameter Format

The raw value stored in the `MarkZones` parameter follows this format:

**Predicate format** (current):
```
?predicateString_Name: r,g,b,a; overshoot; (pos, thick); (pos); ...
```

**Legacy format** (still supported):
```
Script + Script_Name: r,g,b,a; overshoot; (pos, thick); (pos); ...
```

Zones with linked glyphs append `&{glyphName*stretch, ...}` after the position/thickness tuple.
