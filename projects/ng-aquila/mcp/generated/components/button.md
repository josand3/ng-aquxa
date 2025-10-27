--- 
title: Button
category: components

module: NxButtonModule
components:
  - name: NxButtonComponent
    selector: button[nxButton], a[nxButton]
    desc: |
      Accepts multiple tokens via the `nxButton` attribute:
      
      - type (required):       'primary' | 'secondary' | 'tertiary' | 'cta' | 'emphasis' | 'attention'
      - size (optional):       'small' | 'small-medium' | 'medium' | 'large'
      - variant (optional):    'negative' | 'block' | 'danger'
      
      Examples: <button nxButton='{type} {size} {variant}'/>
  - name: NxIconButtonComponent
    selector: button[nxIconButton], a[nxIconButton]
  - name: NxPlainButtonComponent
    selector: button[nxPlainButton], a[nxPlainButton]
    inputs:
      - name: size
        desc: "The plain button size. Please only use it for the One Allianz Design."
        default: 'medium'
        type: "'medium' | 'small'"
      - name: variant
        desc: "The plain button variant. Please only use it for the One Allianz Design."
        default: 'primary'
        type: "'primary' | 'secondary'"
      - name: tabIndex
        type: "number | undefined"
      - name: _tabindexAttribute
        desc: "Use 'tabindex' to handle existing usages of `[tabindex]` bindings on button elements"
        type: "number | undefined"
      - name: loading
        desc: "Whether the button should be in a loading state."
        default: input<boolean, BooleanInput>(false, { transform: booleanAttribute })
        type: "InputSignalWithTransform<boolean, BooleanInput>"
      - name: critical
        desc: "Whether to show the critical/danger appearance"
        type: "BooleanInput"
      - name: disabled
        desc: "Whether the button should be disabled."
        type: "BooleanInput"
    methods:
      - name: setTriggerActive
        params: 
        returnType: void
      - name: setTriggerInactive
        params: 
        returnType: void

---
# Overview
Buttons are used to make common actions immediately visible and easy to perform. This component allows users to trigger an action – either by clicking on or tapping the button, or by pressing certain keyboard keys (such as Enter or the space bar). Depending on the use case, buttons contain a label and/or an icon. There are multiple styles, sizes, and variations that can be used for different situations. We attach buttons through a directive so that we can rely on the native abilities of a real **`<button>`** tag.

We work with five different types of buttons. The primary's heavy appearance is intended to direct the user to take a suggested primary action; the secondary's lighter design best works to compliment a primary action or to reduce visual noise if there are several hierarchically equal actions on the same page. Emphasis, call-to-action and disabled should be self-explanatory.
