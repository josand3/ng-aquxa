--- 
title: Menu
category: components

module: NxMenuModule
components:
  - name: NxMenuComponent
    selector: nx-menu
    desc: |
      This components is a collapsible menu for usage on smaller devices.
      
      Can contain any content, but usually [nxMenuLink], [nxMenuGroup] and [nxAction].
    inputs:
      - name: open
        desc: "Whether the menu is open or closed."
        type: "BooleanInput"
    methods:
      - name: toggle
        params: 
        returnType: void
  - name: NxMenuLinkDirective
    selector: a[nxMenuLink]
    desc: |
      This is a menu link.
      It adds styling to a link and is usually used within a [nxMenuItem].
  - name: NxMenuItemDirective
    selector: [nxMenuItem]
    desc: |
      This is a menu item is used to structure content whithin a menu.
    inputs:
      - name: nxMenuItem
        type: "string"
  - name: NxMenuButtonComponent
    selector: [nxMenuButton]
    inputs:
      - name: expandable
        desc: "Whether this menu button is expandable or not. Will add a caret icon."
        type: "BooleanInput"
      - name: expanded
        desc: "Whether this menu button is expanded or not. Only works in combination with the `expandable` option set to `true`."
        type: "BooleanInput"
      - name: menuButtonType
        desc: "The type of this menu button. Can be `primary` or `secondary`, defaults to `primary`."
        type: "'root' | 'nested'"
  - name: NxMenuButtonIconDirective
    selector: [nxMenuButtonIcon]
    desc: |
      Icon that can be added to a [nxButton].

---
# Overview
This is a collapsible menu. It is designed to be a replacement for the top level navigation in the header and the sidebar on small screens (mobile and tablet if necessary). The menu consists of a wrapper `<nx-menu>` component that handles the collapsing and positioning of the menu content. A common `<nx-menu>` contains a set of `[nxMenuItem]`,`[nxMenuButton]` and `[nxMenuLink]`. The content of the menu is not restricted to those elements.
