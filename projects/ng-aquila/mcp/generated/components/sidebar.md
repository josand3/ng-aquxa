--- 
title: Side Navigation
category: components
alias: sidenav, side navigation

module: NxSidebarModule
components:
  - name: NxSidebarComponent
    selector: nx-sidebar
    inputs:
      - name: resizeable
        desc: "If set to `true` this will enable dynamic resizing of the sidebar."
        type: "BooleanInput"
      - name: minWidth
        desc: "Sets the minimal width (in pixel) of the sidebar."
        type: "NumberInput"
      - name: maxWidth
        desc: "Sets the maximal width (in pixel) of the sidebar."
        type: "NumberInput"
      - name: resizeHandleAriaLabel
        desc: "This sets the accessibility label for the resize handle of the sidebar."
        type: "string"
    outputs:
      - name: widthChange
        desc: "Emits the new width of the sidebar on resize or on close/open event."
        type: "EventEmitter<number>"
    methods:
      - name: expand
        params:
          - name: expandedWidth
            type: number | undefined
        desc: "This will expand the sidebar to its full width."
        returnType: void
      - name: close
        params: 
        desc: "This will close the sidebar to its minimal width."
        returnType: void
      - name: toggle
        params: 
        desc: "This will close or expand the sidebar depending if it is expanded or closed."
        returnType: void
  - name: NxSidebarFooterComponent
    selector: nx-sidebar-footer
  - name: NxSidebarToggleComponent
    selector: button[nxSidebarToggle]
    methods:
      - name: toggle
        params: 
        returnType: void

---
# Overview
The `<nx-sidebar>` provides a collapsible container for side content (often navigation, though it can be any content) alongside some primary content.

Please note that all the following examples use the [NxActionComponent](./documentation/action) for the side navigation items. The `NxActionModule` **is not automatically imported** when you import the `NxSidebarModule`. Therefore you have to import the `NxActionModule` yourself, if you want the same sidebar look:

```ts
import { NxActionModule } from '@allianz/ng-aquila/action';
```
