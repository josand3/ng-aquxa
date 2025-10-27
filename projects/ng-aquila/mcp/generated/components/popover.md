--- 
title: Popover
category: components

module: NxPopoverModule
components:
  - name: NxPopoverTriggerDirective
    selector: [nxPopoverTriggerFor]
    inputs:
      - name: nxPopoverTriggerFor
        desc: "Links the trigger with the popover to open."
        type: "NxPopoverComponent"
      - name: nxPopoverDirection
        desc: "Sets the desired direction to open the popover. E.g., right, left, bottom, top"
        default: 'right'
        type: "PopoverHorizontalDirection | PopoverVerticalDirection"
      - name: nxPopoverInitialVisible
        desc: "Whether the popover will be opened automatically."
        default: false
        type: "boolean"
      - name: nxPopoverVisibleChange
        desc: "An event is emitted when the visibility of the popopver changes."
        default: new EventEmitter<boolean>()
        type: "EventEmitter<boolean>"
      - name: nxPopoverTrigger
        desc: "Sets the way to trigger the popover. Options are hover, click, manual"
        default: 'click'
        type: "'click' | 'hover' | 'manual'"
      - name: nxPopoverShow
        desc: "Whether to show or hide the popover."
        type: "BooleanInput"
      - name: nxPopoverCloseable
        desc: "Whether to show a close button. By default a close icon is only shown for trigger type click. Can't be used for trigger type hover."
        type: "BooleanInput"
      - name: closeOnClickOutside
        desc: "Whether the popover should be closed on click outside of the popover in the trigger modes 'manual' and 'click'."
        type: "BooleanInput"
      - name: hidePopoverArrow
        desc: "Whether to show the popover arrow. By default set to true"
        type: "BooleanInput"
      - name: nxPopoverWidth
        desc: "Popover width"
        type: "string | undefined"
      - name: nxPopoverMaxWidth
        desc: "Popover max-width"
        type: "string | undefined"
      - name: nxPopoverModal
        desc: "Whether the popover opens in modal state."
        type: "BooleanInput"
      - name: nxPopoverScrollStrategy
        desc: "Sets the scroll strategy. 'close' closes the popover on scroll while 'reposition' scrolls the popover with the origin."
        type: "'close' | 'reposition' | null | undefined"
    outputs:
      - name: changeShow
        desc: "An event is emitted if the visibility status of the popover changes."
        type: "EventEmitter<boolean>"
    methods:
      - name: isCloseable
        params: 
        returnType: boolean
      - name: updatePosition
        params: 
        desc: "Update the popover with the given position strategy."
        returnType: void
      - name: handleClick
        params: 
        returnType: void
      - name: open
        params: 
        desc: "Open the popover instance."
        returnType: void
      - name: close
        params: 
        desc: "Close the popover instance."
        returnType: void
      - name: toggle
        params: 
        desc: "Toggle the popover instance."
        returnType: void
  - name: NxPopoverComponent
    selector: nx-popover
    outputs:
      - name: closed
        desc: "Event emitted when the popover is closed."
        type: "EventEmitter<void>"
    methods:
      - name: emitCloseButtonClick
        params: 
        desc: "Emits event to notify the popover trigger directive that the close button was clicked."
        returnType: void
      - name: emitClosedEvent
        params: 
        returnType: void
  - name: NxPopoverContentDirective
    selector: ng-template[nxPopoverContent]
    desc: |
      Popover content that will be rendered lazily
      after the popover is opened for the first time.

---
# Overview
Popover requires Angular CDK (incl. CSS). Learn [how to enable Angular CDK styles](./documentation/overlay/overview#angular-cdk).
