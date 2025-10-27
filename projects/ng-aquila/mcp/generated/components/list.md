--- 
title: List
category: components

module: NxListModule
components:
  - name: NxListComponent
    selector: ul[nxList], ol[nxList]
    inputs:
      - name: nxList
        desc: "Sets the visual appearance of the list. You can combine different values:  xsmall | small | normal: The listed input values are expanded to the underlying BEM conform styles based on modifiers. Defaults to normal.  Negative: Display the list with a negative set of styling.  Ordered-circle: Display the list item numbers in a color filled circle."
        type: "string"
      - name: condensed
        desc: "Change the list mode to condensed"
        type: "boolean"
  - name: NxListIconComponent
    selector: li[nxListIcon]
    inputs:
      - name: nxListIcon
        desc: "Sets the name of the icon to be displayed."
        type: "string"

---
# Overview
The component library supports three types of lists: unordered lists, ordered lists and lists with icons.
