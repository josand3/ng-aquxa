--- 
title: Grid
category: components
desc:  grid is based on 12 columns with tiers spread over the given set of breakpoints. That way, you can maintain different layouts corresponding to each group of devices
alias: container, column, layout

module: NxGridModule
components:
  - name: NxLayoutComponent
    selector: [nxLayout]
    inputs:
      - name: containerQuery
        desc: "On `true` the Grid will use container queries instead of media queries. See [mdn docs](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_container_queries) for more info"
        default: false
        type: "boolean"
      - name: nxLayout
        desc: "Type of layout.  Values: grid | grid nogutters | grid maxwidth | grid nopadding. Default value: grid."
        type: "string"
  - name: NxRowComponent
    selector: [nxRow]
    inputs:
      - name: class
        desc: "Overwrite default class property to access user provided class."
        default: ''
        type: "string"
      - name: nxRow
        desc: "Values: row | row-reverse.  Default: `'row'`."
        type: "string"
      - name: rowJustify
        desc: "Align items on the main axis (horizontally)."
        type: "'start' | 'end' | 'center' | 'between' | 'around' | string"
      - name: rowAlignContent
        desc: "Similar to nxRowAlignItems, but instead of aligning flex items, it aligns flex lines."
        type: "'start' | 'end' | 'center' | 'between' | 'around' | 'stretch' | string"
      - name: rowAlignItems
        desc: "The default alignment for items inside the flexible container."
        type: "'start' | 'end' | 'center' | 'between' | 'stretch' | string"
      - name: rowWrap
        desc: "How the flexible items should be wrapped."
        type: "'wrap' | 'nowrap' | 'reverse'"
  - name: NxColComponent
    selector: [nxCol]
    inputs:
      - name: class
        desc: "Overwrite default class property to access user provided class."
        type: "string"
      - name: nxCol
        desc: "The `nxCol` attribute accepts up to seven comma-separated values for responsive layout Order of the used inputs correspond with tiers: nxCol='<tiny>, <small>, <medium>, <large>, <xlarge>, <2xlarge>, <3xlarge>'  - Use one input it will be used for all tiers. - If fewer than 7 values are provided, the last one repeats for the remaining breakpoints(tiers). - Use two inputs: nxCol='12,8' => nxCol='12,8,8,8,8,8,8' - Use three  inputs: nxCol='12,8,6' => nxCol='12,8,6,6,6,6,6'  Values: 1 - 12, default value: 12."
        type: "string"
      - name: colOffset
        desc: "The number of columns the column should be offset. accepts up to seven comma-separated values for responsive layout Order of the used inputs correspond with tiers: nxCol='<tiny>, <small>, <medium>, <large>, <xlarge>, <2xlarge>, <3xlarge> Use one input it will be used for all tiers. If fewer than 7 values are provided, the last one repeats for the remaining breakpoints(tiers).  Values: 1 - 12, default value: 12."
        type: "string"
      - name: alignSelf
        desc: "The alignment for a column inside the flexible container."
        type: "'auto' | 'start' | 'end' | 'center' | 'baseline' | 'stretch' | string"
      - name: colOrder
        desc: "Order of the column within the row."
        type: "'first' | 'last' | 'unordered' | string"
    methods:
      - name: isValueBetween
        params:
          - name: min
            type: number
          - name: max
            type: number
          - name: value
            type: string
        returnType: boolean
      - name: checkNotAllowedValues
        params:
          - name: values
            type: string[]
          - name: excludes
            type: string[]
        returnType: boolean
      - name: generateError
        params:
          - name: err
            type: string
        returnType: void
      - name: validateInput
        params:
          - name: value
            type: string[]
        returnType: void

---
# Overview
The application grid is based on 12 columns with tiers spread over the given set of breakpoints. That way, you can maintain different layouts corresponding to each group of devices.

**Note:** The borders here are only for visual support and not part of any grid definition.

This bar will show you the current tier of the grid. Change the size of your browser to see when the tiers change:

<div class="grid-component__current-grid-tier">
  <span class="current-grid__tier current-grid__tier-tiny">tiny</span>
  <span class="current-grid__tier current-grid__tier-small">small</span>
  <span class="current-grid__tier current-grid__tier-medium">medium</span>
  <span class="current-grid__tier current-grid__tier-large">large</span>
  <span class="current-grid__tier current-grid__tier-xlarge">xlarge</span>
  <span class="current-grid__tier current-grid__tier-2xlarge">2xlarge</span>
  <span class="current-grid__tier current-grid__tier-3xlarge">3xlarge</span>
</div>
