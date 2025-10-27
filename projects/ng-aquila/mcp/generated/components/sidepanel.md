--- 
title: Sidepanel
category: components
alias: sidebar, drawer

module: NxSidepanelModule
components:
  - name: NxSidepanelComponent
    selector: nx-sidepanel
    inputs:
      - name: opened
        desc: "Whether the sidepanel should be opened and visible."
        type: "BooleanInput"
      - name: position
        desc: "Sets the position of the sidepanel."
        type: "'floating' | 'static'"
      - name: appearance
        desc: "Sets the appearance of the sidepanel. Default: dark."
        type: "'light' | 'dark'"
    outputs:
      - name: openedChange
        desc: "An event emitted when the opened value has changed.  Emits the boolean value."
        type: "EventEmitter<boolean>"
    methods:
      - name: toggle
        params: 
        desc: "Toggles the opened state of the sidepanel."
        returnType: void
      - name: open
        params: 
        desc: "Sets the opened state of the sidepanel to true."
        returnType: void
      - name: close
        params: 
        desc: "Sets the opened state of the sidepanel to false."
        returnType: void
      - name: onAnimationDone
        params:
          - name: event
            type: AnimationEvent
        returnType: void
      - name: focusTrigger
        params:
          - name: opened
            type: boolean
        returnType: void
  - name: NxSidepanelHeaderComponent
    selector: nx-sidepanel-header
  - name: NxSidepanelContentComponent
    selector: nx-sidepanel-content
  - name: NxSidepanelCloseButtonComponent
    selector: button[nxSidepanelCloseButton]
  - name: NxSidepanelOuterContainerComponent
    selector: nx-sidepanel-outer-container

---
# Overview
Please note that the sidepanel is currently **not recommended for mobile usage**.

The `nx-sidepanel` is a container that is fixed to the right edge of the viewport to provide content that supports the main content area. The `nx-sidepanel` needs to be wrapped into `nx-sidepanel-outer-container`, which also holds the main content besides the sidepanel:

```html
<nx-sidepanel-outer-container>
    <!-- Main content of the page -->

    <nx-sidepanel>
        <!-- Content besides the main area of the page -->
    </nx-sidepanel>
</nx-sidepanel-outer-container>
```

`<nx-sidepanel-header>` provides a place that will stay fixed on top, when the bottom part of `<nx-sidepanel-content>` is scrolled down.
