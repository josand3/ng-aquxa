--- 
title: Tooltip
category: components

module: NxTooltipModule
components:
  - name: NxTooltipDirective
    selector: [nxTooltip]
    desc: |
      Directive that attaches a tooltip to the host element.
    inputs:
      - name: nxTooltipShowDelay
        desc: "The default delay in ms before showing the tooltip after show is called"
        default: this._defaultOptions!.showDelay
        type: "number"
      - name: nxTooltipHideDelay
        desc: "The default delay in ms before hiding the tooltip after hide is called"
        default: this._defaultOptions!.hideDelay
        type: "number"
      - name: manualTrigger
        desc: "Whether the tooltip should only be shown or hidden manually. If true, tooltip will not respond to mouse or focus events."
        default: input(false)
        type: "InputSignal<boolean>"
      - name: nxTooltipPosition
        desc: "Allows the user to define the position of the tooltip relative to the parent element"
        type: "TooltipVerticalPosition | TooltipHorizontalPosition"
      - name: nxTooltipDisabled
        desc: "Disables the display of the tooltip."
        type: "BooleanInput"
      - name: nxTooltipSelectable
        desc: "Allow selection of text within tooltip trigger.  NOTE: inputs and textareas always remain selectable, ignoring this input."
        type: "BooleanInput"
      - name: nxTooltip
        desc: "The message to be displayed in the tooltip"
        type: "string"
    methods:
      - name: show
        params:
          - name: delay
            type: number
        desc: "Shows the tooltip after the delay in ms, defaults to tooltip-delay-show or 0ms if no input"
        returnType: void
      - name: hide
        params:
          - name: delay
            type: number
        desc: "Hides the tooltip after the delay in ms, defaults to tooltip-delay-hide or 0ms if no input"
        returnType: void
      - name: toggle
        params: 
        desc: "Shows/hides the tooltip"
        returnType: void
  - name: NxTooltipComponent
    selector: nx-tooltip-component
    desc: |
      Internal component that wraps the tooltip's content.
    methods:
      - name: show
        params:
          - name: delay
            type: number
        desc: "Shows the tooltip with an aninxion originating from the provided origin"
        returnType: void
      - name: hide
        params:
          - name: delay
            type: number
        desc: "Begins the animation to hide the tooltip after the provided delay in ms."
        returnType: void
      - name: afterHidden
        params: 
        desc: "Returns an observable that notifies when the tooltip has been hidden from view."
        returnType: Observable<void>
      - name: isVisible
        params: 
        desc: "Whether the tooltip is being displayed."
        returnType: boolean
      - name: isDelayed
        params: 
        desc: "Whether the tooltip started a delay to be shown/hidden"
        returnType: boolean

---
# Overview
The Tooltip component requires additional CSS files from the Angular CDK to work. Please add the following files to your global styles or into the styles option in the angular.json if not already present (learn [how to enable Angular CDK styles](./documentation/overlay/overview#angular-cdk)):

```
  node_modules/@angular/cdk/overlay-prebuilt.css
  node_modules/@angular/cdk/a11y-prebuilt.css
```
