--- 
title: Action
category: components
alias: menu

module: NxActionModule
components:
  - name: NxActionComponent
    selector: [nxAction]
    inputs:
      - name: selected
        desc: "Whether this action is selected or not."
        type: "BooleanInput"
      - name: expandable
        desc: "Whether this action is expandable or not. Will add a caret icon."
        type: "BooleanInput"
      - name: expanded
        desc: "Whether this action is expanded or not.  Only works in combination with the `expandable` option set to `true`."
        type: "BooleanInput"
  - name: NxActionIconDirective
    selector: [nxActionIcon]

---
# Overview
An `[nxAction]` enhances `<a>` or `<button>` elements with styling to be used as a list inside a [sidebar](./documentation/sidebar/overview) or in a [nx-tree](./documentation/tree/overview).

<!-- example(action) -->
