--- 
title: Toggle Button
category: components
alias: radio toggle

module: NxRadioToggleModule
components:
  - name: NxRadioToggleComponent
    selector: nx-radio-toggle
    inputs:
      - name: disableMobile
        desc: "Whether the component should switch to vertical buttons on mobile viewports."
        default: false
        type: "boolean"
      - name: disabled
        desc: "Sets the component to the disabled state."
        type: "BooleanInput"
      - name: readonly
        desc: "Sets the component to the readonly state."
        type: "boolean"
      - name: name
        type: "string"
      - name: ariaLabel
        type: "string | null"
      - name: ariaLabelledBy
        type: "string | null"
      - name: variant
        desc: "Sets the modifiers for the component."
        type: "string"
    methods:
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
      - name: change
        params:
          - name: value
            type: any
        returnType: void
      - name: updateErrorState
        params: 
        returnType: void
      - name: setReadonly
        params:
          - name: value
            type: boolean
        returnType: void
  - name: NxRadioToggleButtonComponent
    selector: nx-radio-toggle-button
    inputs:
      - name: disableMobile
        default: false
        type: "boolean"
      - name: disabled
        type: "BooleanInput"
      - name: readonly
        type: "boolean"
      - name: ariaLabel
        desc: "Aria label for screen reader users"
        type: "string | null"
      - name: selected
        desc: "Sets the checked state and notify siblings and the parent group about the change"
        type: "boolean"
    methods:
      - name: setReadonly
        params:
          - name: value
            type: boolean
        returnType: void
      - name: select
        params: 
        returnType: void
      - name: deselect
        params: 
        returnType: void
      - name: onKeyupSpace
        params: 
        returnType: void

---