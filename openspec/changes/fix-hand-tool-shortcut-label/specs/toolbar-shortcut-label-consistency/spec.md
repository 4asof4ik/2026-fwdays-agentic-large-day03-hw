## ADDED Requirements

### Requirement: Hand tool displays keyboard shortcut label

The hand (pan) tool in the desktop toolbar SHALL display its keyboard shortcut "H" as a superscript label on its icon, consistent with all other toolbar tools.

#### Scenario: Hand tool shows "H" label on desktop toolbar

- **WHEN** the user views the Excalidraw toolbar on a desktop (non-mobile) viewport
- **THEN** the hand tool icon SHALL display "H" in the bottom-right corner as a keybinding label, using the same `.ToolIcon__keybinding` styling as all other tool icons

#### Scenario: Hand tool tooltip includes shortcut

- **WHEN** the user hovers over the hand tool icon on desktop
- **THEN** the tooltip SHALL display the tool name and shortcut (e.g., "Hand (panning tool) — H")

### Requirement: Mobile toolbar hides hand tool shortcut label

The hand tool on mobile viewports SHALL NOT display a keybinding label, consistent with the existing mobile toolbar behavior.

#### Scenario: Hand tool has no label on mobile

- **WHEN** the user views the Excalidraw toolbar on a mobile viewport
- **THEN** the hand tool icon SHALL NOT display a keybinding label overlay

### Requirement: All toolbar tools follow consistent label pattern

Every tool in the desktop toolbar that has a keyboard shortcut defined in `SHAPES` SHALL display its shortcut as a keybinding label. No tool-specific exclusions SHALL exist in the label computation logic.

#### Scenario: No tool-specific exclusions in keybinding label logic

- **WHEN** the `ShapesSwitcher` component computes `keybindingLabel` for any tool
- **THEN** the computation SHALL use the generic formula (`numericKey || letter`) without special-casing any tool by name or value
