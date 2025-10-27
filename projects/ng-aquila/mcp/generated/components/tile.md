--- 
title: Tile
category: components

components: 
- name: NxTileGroupComponent
  selector: nx-tile-group
  inputs:
    - name: autoGrid
      desc: "Whether to enable automatic grid layout for the tiles. Default is true."
      default: input(true)
      type: "InputSignal<boolean>"
    - name: maxColumns
      desc: "Maximum number of columns when auto grid is enabled. Default is 4."
      default: input(4)
      type: "InputSignal<number>"
    - name: selectionMode
      desc: "Selection mode for the tile group. Can be 'single' or 'multi'. Default is 'single'."
      default: input<NxTileSelectionMode>('single')
      type: "InputSignal<'single' | 'multi'>"
    - name: disabledInput
      desc: "Whether the tile group is disabled. Default is false."
      default: input(false, { alias: 'disabled' })
      type: "InputSignal<boolean>"
    - name: readonly
      desc: "Whether the tile group is readonly. Default is false."
      default: input(false)
      type: "InputSignal<boolean>"
    - name: tileLayout
      desc: "The layout of the tiles in the group. Can be 'horizontal' or 'vertical'. Default is 'vertical'."
      default: input<NxTileLayout>('vertical')
      type: "InputSignal<'horizontal' | 'vertical'>"
  methods:
    - name: setDisabledState
      params:
        - name: isDisabled
          type: boolean
      returnType: void
    - name: touch
      params: 
      returnType: void
- name: NxTileComponent
  selector: nx-tile
  desc: |
    Represents a tile component with selectable, readonly, and disabled states.
  inputs:
    - name: icon
      desc: "Icon to display in the tile."
      default: input<string>('')
      type: "InputSignal<string>"
    - name: label
      desc: "Label text for the tile."
      default: input<string | null>(null)
      type: "InputSignal<string | null>"
    - name: hint
      desc: "Hint text for the tile."
      default: input<string | null>(null)
      type: "InputSignal<string | null>"
    - name: disabledInput
      desc: "Disabled input, can be overridden by group."
      default: input(false, { alias: 'disabled' })
      type: "InputSignal<boolean>"
    - name: readonlyInput
      desc: "Readonly input, can be overridden by group."
      default: input(false, { alias: 'readonly' })
      type: "InputSignal<boolean>"
    - name: value
      desc: "Value of the tile (used for selection in a group)."
      default: input<any>(null)
      type: "InputSignal<any>"
  methods:
    - name: toggleSelection
      params:
        - name: event
          type: Event
      desc: "Toggles the selection state of the tile."
      returnType: void
    - name: touch
      params: 
      returnType: void



---
# Overview
The Tile component is a new component from the One Allianz Design System with a backwards compatible theme for NDBX projects. It is an alternative to the circle toggle component. We suggest not to mix both of them on the same page.
The Tile component is a versatile UI element that can display an icon, label, and hint text. It supports selectable, readonly, and disabled states, and can be used in both single-select and multi-select groups.
