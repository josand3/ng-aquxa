--- 
title: Checkbox
category: components

module: NxCheckboxModule
components:
  - name: NxCheckboxComponent
    selector: nx-checkbox
    inputs:
      - name: ariaLabel
        default: null
        type: "string | null"
      - name: ariaLabelledBy
        default: null
        type: "string | null"
      - name: name
        desc: "Name of the checkbox."
        type: "string"
      - name: disabled
        desc: "Whether the checkbox is disabled."
        type: "BooleanInput"
      - name: readonly
        desc: "Whether the checkbox should be readonly."
        type: "boolean"
      - name: labelSize
        desc: "Sets the label size of the checkbox.  Default: `'small'`."
        type: "'small' | 'large'"
      - name: negative
        desc: "Whether the checkbox has negative styling."
        type: "BooleanInput"
      - name: checked
        desc: "Whether the checkbox is checked."
        type: "BooleanInput"
      - name: indeterminate
        desc: "Whether the checkbox is indeterminated."
        type: "BooleanInput"
      - name: required
        desc: "Whether the checkbox is required."
        type: "BooleanInput"
      - name: value
        desc: "Sets the value of the checkbox. Default value is the checked status."
        type: "string"
    outputs:
      - name: indeterminateChange
        desc: "An event emitted when the indeterminate value has changed"
        type: "EventEmitter<boolean>"
      - name: checkedChange
        desc: "An event emitted when the checked value has changed.  Emits the boolean checked value of the changed checkbox."
        type: "EventEmitter<boolean>"
      - name: checkboxChange
        desc: "An event emitted when the checked value has changed.  Emits a NxCheckboxChangeEvent."
        type: "EventEmitter<NxCheckboxChangeEvent>"
    methods:
      - name: labelContentChanged
        params: 
        desc: "Callback for when the content of the label has changed."
        returnType: void
      - name: setReadonly
        params:
          - name: value
            type: boolean
        returnType: void
      - name: validate
        params:
          - name: control
            type: AbstractControl<any, any, any>
        returnType: ValidationErrors | null
      - name: toggle
        params: 
        desc: "Toggles the checked state of the checkbox."
        returnType: void
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
      - name: focus
        params:
          - name: focusOrigin
            type: FocusOrigin | undefined
        desc: "Focuses the checkbox element."
        returnType: void
      - name: touch
        params: 
        returnType: void
  - name: NxCheckboxGroupComponent
    selector: nx-checkbox-group
    inputs:
      - name: name
        desc: "Sets the name of the checkboxes inside the nx-checkbox-group."
        type: "string"
      - name: disabled
        desc: "Disables all checkboxes inside the nx-checkbox-group."
        type: "BooleanInput"
      - name: readonly
        desc: "Sets all checkboxes in the group to readonly."
        type: "boolean"
      - name: negative
        desc: "Set the negative styles for all the checkboxes inside the nx-checkbox-group"
        type: "BooleanInput"
      - name: labelSize
        desc: "Sets the label size of the checkboxes inside the group"
        type: "'small' | 'large'"
      - name: required
        desc: "Whether the nx-checkbox-group are required."
        type: "BooleanInput"
    outputs:
      - name: selectionChange
        type: "EventEmitter<NxCheckboxGroupChangeEvent>"
    methods:
      - name: setReadonly
        params:
          - name: value
            type: boolean
        returnType: void
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
      - name: change
        params:
          - name: value
            type: unknown
        returnType: void
      - name: updateErrorState
        params: 
        returnType: void
      - name: getLabelledby
        params: 
        returnType: string | null

---
# Overview
The Checkbox is used when there is a list of options and the user may select one or more options, including all or none. This component appears also in case of yes or no choices (e.g. “Remember me” by Login). It's an efficient and elegant way to select/deselect an item or enable/disable certain actions.

This component implements the checkbox as the combination of a label and an input tag. It is not intended that you use the checkbox without a label.
