--- 
title: Icons
category: components

module: NxIconModule
components:
  - name: NxIconComponent
    selector: nx-icon
    inputs:
      - name: font
        desc: "Sets the font name that should be used."
        default: ''
        type: "string"
      - name: name
        desc: "Sets the name for specifying the icon."
        type: "string"
      - name: outline
        desc: "Whether the icon has an outline."
        type: "BooleanInput"
      - name: fill
        desc: "Whether the icon is filled."
        type: "BooleanInput"
      - name: size
        desc: "Specifies the size of the icon."
        type: "'auto' | 's' | 'm' | 'l' | 'xl'"
  - name: NxStatusIconComponent
    selector: nx-status-icon
    inputs:
      - name: type
        desc: "Sets status type"
        type: "'success' | 'info' | 'error' | 'warning'"
      - name: size
        desc: "Specifies the size of the icon."
        type: "'auto' | 's' | 'm' | 'l' | 'xl'"

---
# Overview
<div class="docs-private">
