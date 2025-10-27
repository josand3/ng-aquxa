--- 
title: Page Search
category: components
alias: search field

module: NxPageSearchModule
components:
  - name: NxPageSearchComponent
    selector: nx-page-search
    inputs:
      - name: buttonLabel
        desc: "Sets the text label of the button."
        type: "string"
      - name: hideSearchButton
        desc: "Whether the search button should be hidden."
        type: "BooleanInput"
      - name: buttonLayout
        desc: "Layout of the search button inside of a NxGrid. Default: 12,12,12,2."
        type: "string"
      - name: contentLayout
        desc: "Layout of the content area inside of a NxGrid. Default: 12,12,12,10 | 12 (if search button is hidden)."
        type: "string"
    outputs:
      - name: buttonClick
        desc: "An event emitted when the user clicks the search button."
        type: "EventEmitter<any>"
    methods:
      - name: onButtonClick
        params: 
        returnType: void

---
# Overview
The page search component implements a simple container with a button on the right side and custom content on the left. It is optimized for the usage of [NxInput](./documentation/input/overview) or [NxAutocomplete](./documentation/autocomplete/overview) as content.

The layout of the component uses a single row for both content and button. As default, the page search uses **nxCol="12,12,12,2"** for the button and **nxCol="12,12,12,10"** for the content; it is, however, possible to implement custom column constraints. In the following examples the values "12,12,12,4" for `buttonLayout` and "12,12,12,8" for `contentLayout` are used.

If you use more than one page-search or elements with `role="search"` per page, each one should have a unique aria-label.
