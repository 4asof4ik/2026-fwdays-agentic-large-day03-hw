## Why

The hand (pan) tool in the Excalidraw toolbar is the only tool missing its keyboard shortcut label ("H") as a superscript on the icon. Every other tool displays its shortcut key, creating a visual inconsistency that hurts discoverability. This is a regression in toolbar UX consistency reported in [GitHub issue #11020](https://github.com/excalidraw/excalidraw/issues/11020).

## What Changes

- Remove the explicit exclusion of the hand tool from shortcut label rendering in the desktop toolbar's `ShapesSwitcher` component
- The hand tool icon will display "H" as a superscript label, matching the pattern used by all other toolbar tools (selection shows "1", rectangle shows "R", etc.)

## Capabilities

### New Capabilities

- `toolbar-shortcut-label-consistency`: Ensure all toolbar tools consistently display their keyboard shortcut labels as superscripts on their icons, including the hand/pan tool

### Modified Capabilities

## Impact

- **Code**: `packages/excalidraw/components/Actions.tsx` — the `ShapesSwitcher` component's keybinding label computation (line ~1104) where `value === "hand"` causes the label to be `undefined`
- **Visual**: The hand tool icon in the navigation bar will now show "H" in its bottom-right corner
- **No breaking changes**: This is a purely additive UI fix with no API or behavioral changes
