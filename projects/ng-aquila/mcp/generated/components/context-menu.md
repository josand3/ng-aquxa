--- 
title: Context Menu
category: components
alias: menu

module: NxContextMenuModule
components:
  - name: NxContextMenuComponent
    selector: nx-context-menu
    outputs:
      - name: closed
        desc: "Event emitted when the menu is closed."
        type: "EventEmitter<void | 'click' | 'keydown' | 'tab'>"
    methods:
      - name: focusFirstItem
        params:
          - name: origin
            type: FocusOrigin | undefined
        desc: "Focus the first item in the menu."
        returnType: void
      - name: resetActiveItem
        params: 
        desc: "Resets the active item in the menu. This is used when the menu is opened, allowing the user to start from the first option when pressing the down arrow."
        returnType: void
  - name: NxContextMenuContentDirective
    selector: ng-template[nxContextMenuContent]
    desc: |
      Context menu content that will be rendered lazily once the menu is opened.
    methods:
      - name: attach
        params:
          - name: context
            type: any
        desc: "Attaches the content with a particular context."
        returnType: void
      - name: detach
        params: 
        desc: "Detaches the content."
        returnType: void
  - name: NxContextMenuItemComponent
    selector: [nxContextMenuItem]
    desc: |
      This directive is intended to be used inside an nx-context-menu tag.
      It exists mostly to set the role attribute, disabled state and styling.
    inputs:
      - name: selectable
        desc: "Whether the context menu item is selectable"
        type: "boolean"
      - name: disabled
        desc: "Whether the context menu item is disabled."
        type: "BooleanInput"
      - name: disableCloseOnSelect
        desc: "Whether the context menu close on select."
        type: "BooleanInput"
    methods:
      - name: focus
        params:
          - name: origin
            type: FocusOrigin | undefined
        desc: "Focuses this context menu item."
        returnType: void
      - name: getLabel
        params: 
        desc: "Gets the label to be used when determining whether the option should be focused."
        returnType: string
  - name: NxContextMenuItemWrapComponent
    selector: nx-context-menu-item-wrap
    desc: |
      This directive is need when [nx-context-menu-item] is not directly under [nx-context-menu].
  - name: NxContextMenuTriggerDirective
    selector: [nxContextMenuTriggerFor]
    desc: |
      This directive is intended to be used in conjunction with an nx-context-menu tag.
      It is responsible for toggling the display of the provided context menu instance.
    inputs:
      - name: nxContextMenuTriggerData
        desc: "Data to be passed along to any lazily-rendered content."
        type: "object"
      - name: nxContextMenuTriggerMode
        desc: "Sets the mode of this context menu trigger. 'button' (default): Opens by clicking the trigger 'cursor': Opens at the cursor position by right clicking anywhere on the trigger."
        default: 'button'
        type: "'button' | 'cursor'"
      - name: nxContextMenuTriggerFor
        desc: "References the context menu instance that the trigger is associated with."
        type: "NxContextMenuComponent"
      - name: scrollStrategy
        type: "'close' | 'reposition' | null | undefined"
    outputs:
      - name: contextMenuOpened
        desc: "Event emitted when the associated context menu is opened."
        type: "EventEmitter<void>"
      - name: contextMenuClosed
        desc: "Event emitted when the associated context menu is closed."
        type: "EventEmitter<void>"
    methods:
      - name: triggersSubmenu
        params: 
        desc: "Whether the context menu triggers a sub-menu or a top-level one."
        returnType: boolean
      - name: toggleContextMenu
        params:
          - name: origin
            type: FocusOrigin | undefined
        desc: "Toggles the context menu between the open and closed states."
        returnType: void
      - name: openContextMenu
        params:
          - name: origin
            type: FocusOrigin | undefined
          - name: position
            type: Point | undefined
        desc: "Opens the context menu."
        returnType: void
      - name: closeContextMenu
        params: 
        desc: "Closes the context menu."
        returnType: void
      - name: focus
        params: 
        desc: "Focuses the context menu trigger."
        returnType: void
  - name: NxContextMenuHeaderComponent
    selector: nx-context-menu-header
  - name: NxContextMenuItemCheckboxDirective
    selector: [nxContextMenuItemCheckbox]
    methods:
      - name: onKeyDown
        params:
          - name: event
            type: KeyboardEvent
        returnType: void
  - name: NxContextMenuGroupComponent
    selector: nx-context-menu-group
    inputs:
      - name: label
        default: input<string>()
        type: "InputSignal<string | undefined>"

---
# Overview
The `<nx-context-menu>` is a floating panel containing a list of options. You can visually separate options using the `<nx-divider>` element.

<!-- example(context-menu-basic) -->

By itself, the `<nx-context-menu>` element does not render anything. The menu is attached to and opened via application of the `nxContextTriggerFor` directive:
