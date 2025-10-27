--- 
title: Signal Button
category: components

module: NxSignalButtonModule
components:
  - name: NxSignalButtonComponent
    selector: nx-signal-button
    inputs:
      - name: disabled
        type: "BooleanInput"
      - name: context
        desc: "Sets the context of the signal button."
        type: "'success' | 'warning' | 'error'"
      - name: aria-label
        desc: "Which aria-label will be reading from screen reader."
        type: "string"
      - name: aria-labelledby
        desc: "Which aria-labelledby will be reading from screen reader."
        type: "string"
      - name: popoverDirection
        desc: "The direction of the popover. The options are `left` | `top` | `right` | `bottom`."
        type: "PopoverHorizontalDirection | PopoverVerticalDirection"
      - name: scrollStrategy
        desc: "Sets the scroll strategy. 'close' closes the popover on scroll while 'reposition' scrolls the popover with the origin."
        type: "'close' | 'reposition'"
    outputs:
      - name: opened
        desc: "The event emitter for open."
        type: "EventEmitter<boolean>"
      - name: closed
        desc: "The event emitter for close."
        type: "EventEmitter<boolean>"

---
# Overview
The signal button can be used to open a popover with a message. With use of `popoverDirection` the popover can be opened in the direction `top`, `bottom`, `left` and `right`. The popover `scrollStrategy` can be set to `close` or `reposition`.
