--- 
title: Switcher
category: components
alias: slide toggle, checkbox

module: NxSwitcherModule
components:
  - name: NxSwitcherComponent
    selector: nx-switcher
    inputs:
      - name: ariaLabel
        default: null
        type: "string | null"
      - name: ariaLabelledBy
        default: null
        type: "string | null"
      - name: readonly
        desc: "Sets switcher to readonly."
        default: false
        type: "boolean"
      - name: ariaDescribedBy
        type: "string | null"
      - name: labelPosition
        desc: "Specifies the placement of the label"
        type: "'left' | 'right'"
      - name: name
        desc: "Sets the label text of the switcher"
        type: "string"
      - name: checked
        desc: "Whether the switcher is checked (on) or unchecked (off)"
        type: "boolean"
      - name: big
        desc: "Whether the big switcher is used"
        type: "BooleanInput"
      - name: labelSize
        desc: "Sets the size of the label"
        type: "'small' | 'large'"
      - name: negative
        desc: "Whether the style for a dark background is used"
        type: "BooleanInput"
      - name: disabled
        desc: "Whether the switcher is in the disabled state"
        type: "BooleanInput"
      - name: required
        type: "boolean"
    outputs:
      - name: checkedChange
        desc: "An event is dispatched each time the switcher value is changed"
        type: "EventEmitter<boolean>"
    methods:
      - name: validate
        params:
          - name: control
            type: AbstractControl<any, any, any>
        returnType: ValidationErrors | null
      - name: toggle
        params:
          - name: event
            type: Event
        desc: "Allows to toggle between the states"
        returnType: void
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
      - name: touch
        params: 
        returnType: void
      - name: updateErrorState
        params: 
        returnType: void
      - name: labelContentChanged
        params: 
        desc: "Callback for when the content of the label has changed."
        returnType: void
      - name: setReadonly
        params:
          - name: value
            type: boolean
        returnType: void

---
# Overview
The switcher component represents a boolean value, just like the native input of a checkbox.
