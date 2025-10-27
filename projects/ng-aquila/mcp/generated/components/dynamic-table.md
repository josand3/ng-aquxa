--- 
title: Dynamic Tables
category: components

module: NxDynamicTableModule
components:
  - name: NxDynamicTableComponent
    selector: nx-dynamic-table
    inputs:
      - name: data
        desc: "Sets the data that it will show in the table."
        type: "any[]"
      - name: displayedColumns
        desc: "Sets the name order and type of columns."
        type: "NxDynamicTableColumnDefinition[] | undefined"
    outputs:
      - name: rowClick
        desc: "An event is dispatched when a row is clicked."
        type: "EventEmitter<any>"
    methods:
      - name: handleRowClick
        params:
          - name: row
            type: object
        returnType: void
      - name: isNumeric
        params:
          - name: column
            type: NxDynamicTableColumnDefinition
        returnType: boolean

---
# Overview
The **dynamic table** is a component to show data in an organized way in a simple table. This component implements the table using Angular CDK, specifically `cdk-table` that is an unopinionated, customizable data-table with a fully-templated API, dynamic columns, and an accessible DOM structure. When the viewport is smaller than the table, a horizontal scroll will appear on top of the table.

Please note that **supported data types** are string and numeric. Using markup, images or other components in dynamic tables is not currently possible.
