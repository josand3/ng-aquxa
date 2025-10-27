--- 
title: Input Field
category: components

module: NxInputModule
components:
  - name: NxInputDirective
    selector: input[nxInput], textarea[nxInput], select[nxInput]
    inputs:
      - name: nxAriaLabel
        type: "string"
      - name: value
        desc: "The input element's value."
        type: "any"
      - name: readonly
        desc: "Whether the element is readonly."
        type: "BooleanInput"
      - name: disabled
        desc: "Whether the input is disabled."
        type: "BooleanInput"
      - name: required
        desc: "Whether the element is required."
        type: "any"
      - name: type
        desc: "Sets the type of the input element (e.g. password, text etc)."
        type: "string"
      - name: placeholder
        desc: "Sets the text for the input placeholder."
        type: "string"
      - name: updateOn
        desc: "Sets the event that triggers change detection in the input."
        type: "'change' | 'blur'"
    methods:
      - name: setReadonly
        params:
          - name: value
            type: boolean
        desc: "set readonly state"
        returnType: void
      - name: updateErrorState
        params: 
        returnType: void
      - name: setDescribedByIds
        params:
          - name: ids
            type: string[]
        desc: "Set a list of ids that is currently describing this input (if you have hints and errors for example)."
        returnType: void
      - name: setAriaLabel
        params:
          - name: value
            type: string
        desc: "Method to set the aria label. This is required if you use the input outside of a formfield where you don't have a label connected."
        returnType: void
  - name: NxPasswordToggleComponent
    selector: nx-password-toggle
    inputs:
      - name: control
        desc: "Input element using the toggle functionality."
        type: "HTMLInputElement"
      - name: ariaLabel
        desc: "Sets the aria-label needed for accessibility. Notice that this `aria-label` should describe the initial action according to the status of the visibility. E.g if you have an `input[type=password]` at the beginning then the password will be hidden and the correct aria-label would be 'Show password.'"
        type: "string"
    methods:
      - name: toggleInputType
        params: 
        desc: "Toggles the type of the input."
        returnType: void
      - name: toggleIcon
        params: 
        returnType: void

---