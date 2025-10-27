--- 
title: Table
category: components

module: NxTableModule
components:
  - name: NxHeaderCellDirective
    selector: [nxHeaderCell]
    desc: |
      This is a table header cell.
  - name: NxTableComponent
    selector: table[nxTable]
    desc: |
      This is a table.
      The table supports a `zebra` and a `condensed` mode.
    inputs:
      - name: condensed
        desc: "Change the table mode to condensed"
        type: "BooleanInput"
      - name: zebra
        desc: "Change the table mode to zebra"
        type: "BooleanInput"
      - name: sticky
        desc: "Makes first or last column 'sticky'.  Values: `'first' | 'last' | 'both'`."
        type: "string"
  - name: NxTableCellComponent
    selector: td[nxTableCell], td[nxCell]
    desc: |
      This is a table cell.
  - name: NxTableComponent
    selector: table[nxTable]
    desc: |
      This is a table.
      The table supports a `zebra` and a `condensed` mode.
    inputs:
      - name: condensed
        desc: "Change the table mode to condensed"
        type: "BooleanInput"
      - name: zebra
        desc: "Change the table mode to zebra"
        type: "BooleanInput"
      - name: sticky
        desc: "Makes first or last column 'sticky'.  Values: `'first' | 'last' | 'both'`."
        type: "string"
  - name: NxTableRowComponent
    selector: tr[nxTableRow]
    desc: |
      This is a table row.
    inputs:
      - name: selectable
        desc: "Whether this table row is selectable"
        type: "BooleanInput"
      - name: selected
        desc: "Whether this table row is selected"
        type: "BooleanInput"
      - name: mayStick
        desc: "Whether this row is rendered 'sticky'. Only works for `nxHeaderCell` cells."
        type: "BooleanInput"
    outputs:
      - name: select
        type: "EventEmitter<void>"
  - name: NxToggleButtonComponent
    selector: nx-toggle-button
    desc: |
      This toggle button can be clicked and toggles expandable elements.
      
      E.g. it can toggle a expandable table row or anything else that implements the `NxExpandable` interface.
    inputs:
      - name: target
        desc: "This is the expandable target that will be toggled when the user clicks the button."
        type: "NxExpandable"
      - name: ariaLabel
        type: "string"
  - name: NxExpandableTableDirective
    selector: table[nxExpandableTable], ng-container[nxExpandableContainer]
    desc: |
      The nxExpandableTable adds row expansion functionality to the nxTable.
      It provides the logic to expand/collapse all expandable rows simultanously.
    methods:
      - name: toggle
        params: 
        desc: "Toggles the expandable rows. If all rows are open it will close them, otherwise it will open them."
        returnType: void
      - name: expand
        params: 
        desc: "Expands all expandable rows."
        returnType: void
      - name: close
        params: 
        desc: "Closes all expandable rows."
        returnType: void
  - name: NxExpandableTableRowComponent
    selector: tr[nxExpandableTableRow]
    desc: |
      This is an expandable table row.
      It can collapse its height to hide the content.
      Requires the table cells to have the `[nxExpandableTableCell]` component.
    inputs:
      - name: isExpanded
        type: "BooleanInput"
    methods:
      - name: toggle
        params: 
        desc: "Toggles the expansion of this row."
        returnType: void
      - name: expand
        params: 
        desc: "Expands this row."
        returnType: void
      - name: close
        params: 
        desc: "Closes this row."
        returnType: void
  - name: NxExpandableTableCellComponent
    selector: td[nxExpandableTableCell]
    desc: |
      This is an expandable table cell.
      Only works in conjunction with the `[nxExpandableTableRow]` component.
    inputs:
      - name: indented
        default: input(false, { transform: booleanAttribute })
        type: "InputSignalWithTransform<boolean, unknown>"
  - name: NxSortHeaderComponent
    selector: th[nxSortHeaderCell]
    inputs:
      - name: nxSortHeaderCell
        desc: "Sets the key of this sort header."
        type: "string"
  - name: NxSortDirective
    selector: table[nxSort]
    inputs:
      - name: active
        desc: "Sets the key of the most recently sorted column."
        type: "string"
      - name: direction
        desc: "Sets the direction of the currently active sorted column. Default: 'asc'."
        type: "'asc' | 'desc'"
    outputs:
      - name: activeChange
        desc: "An event emitted when the active value has changed."
        type: "EventEmitter<string>"
      - name: directionChange
        desc: "An event emitted when the direction value has changed."
        type: "EventEmitter<'asc' | 'desc'>"
      - name: sortChange
        desc: "An event emitted when either the active sort or sort direction changes."
        type: "EventEmitter<SortEvent>"
    methods:
      - name: sort
        params:
          - name: sortable
            type: string
        desc: "Sets the active sort key and determines the new sort direction. Afterwards the output event `sortChange` is called.  If `sortable` is not the key of the active sort header, the initial direction to sort is 'asc'. Otherwise the direction of the sorted column changes."
        returnType: void
  - name: NxHeaderResizeDirective
    selector: [nxHeaderResize]
  - name: NxTableCellClipDirective
    selector: table[nxTableCellClip]

---
# Overview
This component is implemented on top of the native HTML table `<table></table>` and adds the needed styling. In addition, there is an expandable table option for advanced use cases.

We provide the following directives: `nxTableCell`, `nxTableRow` and `nxHeaderCell` to apply our style respectively on the top of `td`, `tr` and `th`. This setup maintains the capabilities of the native table such as accessibility and native HTML markups within cells.

According to our UX guidelines we recommend wrapping your tables in a horizontal scrolling container (if they are not 100% responsive). Please note how our examples do that.

<!-- example(table) -->
