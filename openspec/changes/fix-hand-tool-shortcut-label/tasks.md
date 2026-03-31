## 1. Fix Hand Tool Shortcut Label

- [x] 1.1 In `packages/excalidraw/components/Actions.tsx`, remove the `value === "hand"` exclusion from the `keybindingLabel` computation in `ShapesSwitcher` (~line 1104). Change `const keybindingLabel = value === "hand" ? undefined : numericKey || letter;` to `const keybindingLabel = numericKey || letter;`

## 2. Verification

- [x] 2.1 Run `yarn test:typecheck` to ensure no TypeScript errors are introduced
- [x] 2.2 Run `yarn test:update` to update any affected snapshots and confirm all tests pass
- [x] 2.3 Visually verify in the browser that the hand tool now displays "H" as a superscript label in the desktop toolbar, matching other tools
- [x] 2.4 Verify on mobile viewport that the hand tool still does not show a shortcut label (mobile uses `HandButton` with `isMobile=true`, unaffected by this change)
