--- 
title: Code Input
category: components

module: NxCodeInputModule
components:
  - name: NxCodeInputComponent
    selector: nx-code-input
    inputs:
      - name: length
        desc: "The length of the code input. Default: 6."
        type: "number"
      - name: type
        desc: "The type of HTML input"
        type: "string"
      - name: tabindex
        desc: "Sets the tabindex of the contained input elements."
        type: "number"
      - name: convertTo
        desc: "Whether the form should auto capitalize or lowercase (optional)."
        type: "'lower' | 'upper'"
      - name: negative
        desc: "Whether the code input uses the negative set of styling."
        type: "BooleanInput"
      - name: disabled
        desc: "Whether the code input is disabled."
        type: "BooleanInput"
    methods:
      - name: setInputLength
        params: 
        desc: "Sets the length of the input fields."
        returnType: void
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        desc: "Disables the code input. Part of the ControlValueAccessor interface required to integrate with Angular's core forms API."
        returnType: void
      - name: updateErrorState
        params: 
        returnType: void
      - name: getAriaLabel
        params:
          - name: keyIndex
            type: number
        returnType: string
      - name: selectInput
        params:
          - name: input
            type: HTMLInputElement
        desc: "Workaround preventing the selection error because the `setSelectionRange` is not supported on input['type=number']"
        returnType: void

---
# Overview
Use this component when you want users to input a one-time, fixed, and specific set of characters to be validated. There is no limit to how many fields can be used.

The code input component is primarily used for key codes that are generally meaningless and abide by specific character patterns.

This component can be used for anything ranging from one time codes sent via SMS or email verification codes on desktop or mobile.
