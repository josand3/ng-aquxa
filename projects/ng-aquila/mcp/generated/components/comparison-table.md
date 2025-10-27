--- 
title: Comparison Table
category: components

module: NxComparisonTableModule
components:
  - name: NxComparisonTableComponent
    selector: nx-comparison-table
    inputs:
      - name: isError
        type: "boolean"
      - name: selectedIndex
        desc: "Sets which info column is selected."
        type: "NumberInput"
      - name: hiddenIndexes
        desc: "Sets which column is hidden."
        type: "number[]"
      - name: view
        desc: "Sets the layout explicitely. If not specified, a layout will be set based on the viewport."
        type: "'mobile' | 'tablet' | 'desktop' | null | undefined"
    outputs:
      - name: selectedIndexChange
        desc: "An event that is is dispatched each time selected index of the table has changed."
        type: "EventEmitter<number>"
  - name: NxComparisonTableCell
    selector: nx-comparison-table-cell
    inputs:
      - name: index
        type: "number"
      - name: disabledColumn
        desc: "Sets all cells below a header cell to be disabled (disabled column).  **Important**: this property can be set only on header cells."
        type: "BooleanInput"
      - name: type
        desc: "Sets the type of the cell. Default: 'content'."
        type: "'header' | 'content' | 'footer'"
    outputs:
      - name: indexChange
        type: "EventEmitter<number>"
  - name: NxComparisonTableDescriptionCell
    selector: nx-comparison-table-description-cell
  - name: NxComparisonTableIntersectionCell
    selector: nx-comparison-table-intersection-cell
  - name: NxToggleSectionDirective
    selector: [nxComparisonTableToggleSection]
    inputs:
      - name: isExpanded
        desc: "Whether the toggle section is expanded. Default: true."
        type: "boolean"
  - name: NxToggleSectionHeaderComponent
    selector: nx-comparison-table-toggle-section-header
    methods:
      - name: toggle
        params: 
        desc: "Toggles the toggle section."
        returnType: void
  - name: NxComparisonTableRowDirective
    selector: [nxComparisonTableRow]
    inputs:
      - name: type
        desc: "Sets the type of the row. Default: 'content'."
        type: "'header' | 'content' | 'footer'"
      - name: mayStick
        type: "BooleanInput"
  - name: NxComparisonTableSelectButton
    selector: button[nxComparisonTableSelectButton]
    inputs:
      - name: selectedLabel
        desc: "Sets the label that is displayed when the column is selected. Default: 'Selected'."
        type: "string"
      - name: unselectedLabel
        desc: "Sets the label that is displayed when the column is not selected. Default: 'Select'."
        type: "string"
      - name: unselectedClassNames
        desc: "Sets the classNames (style, size and negative) of the unselected button. Default: 'secondary small'."
        type: "string"
      - name: selectedClassNames
        desc: "Sets the classNames (style, size and negative) of the selected button. Default: 'primary small'."
        type: "string"
  - name: NxComparisonTableFlexRow
    selector: nx-comparison-table-flex-row
    desc: |
      Component that is only used internally for displaying a `nxComparisonTableRow`
      (header, content and footer rows) in desktop and tablet view.
    inputs:
      - name: row
        type: "NxComparisonTableRowDirective"
  - name: NxComparisonTableRowGroupDirective
    selector: [nxComparisonTableRowGroup]
    inputs:
      - name: labelCollapsed
        desc: "Sets the label of the expandable area that is shown when the row group is collapsed."
        type: "string"
      - name: labelExpanded
        desc: "Sets the label of the expandable area that is shown when the row group is expanded."
        type: "string"
      - name: visibleRows
        desc: "Sets the number of rows that are visible when loading the component. Default: 5."
        type: "NumberInput"
      - name: isExpanded
        desc: "Sets the expanded state of the row group"
        type: "BooleanInput"
      - name: useFullRowForExpandableArea
        desc: "**Expert Option**.  Sets if the expandable area uses the full width of the row or leaves out the first column.  Default: `false`."
        type: "BooleanInput"
    outputs:
      - name: isExpandedChange
        desc: "An event emitted every time the expanded state of the group changes"
        type: "EventEmitter<boolean>"
  - name: NxComparisonTableDesktopGroup
    selector: nx-comparison-table-desktop-group
    desc: |
      Component that is only used internally for displaying a `nxComparisonTableRowGroup` in desktop and tablet view.
    inputs:
      - name: group
        type: "NxComparisonTableRowGroupDirective"
      - name: isExpanded
        desc: "Sets if the row group is expanded. Default: false."
        type: "BooleanInput"
      - name: useFullRowForExpandableArea
        desc: "Sets if the expansion cell uses the full row of the table or leaves out the first column. Default: false."
        type: "BooleanInput"
    outputs:
      - name: isExpandedChange
        type: "EventEmitter<boolean>"
    methods:
      - name: toggleGroup
        params: 
        returnType: void
      - name: getOpenState
        params: 
        returnType: "open" | "closed"
  - name: NxComparisonTablePopularCell
    selector: nx-comparison-table-popular-cell
    inputs:
      - name: forColumn
        desc: "Sets the id of the column above which the popular cell should be displayed.  Note: counting starts from 1. If set to 1 the popular cell will appear above the first header column of the table."
        type: "NumberInput"

---