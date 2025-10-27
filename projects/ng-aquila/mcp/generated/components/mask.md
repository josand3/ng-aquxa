--- 
title: Input Mask
category: components

module: NxMaskModule
components:
  - name: NxMaskDirective
    selector: input[nxMask]
    inputs:
      - name: deactivateMask
        desc: "Whether the mask validation should be deactivated."
        type: "BooleanInput"
      - name: nxMask
        desc: "Sets the mask."
        type: "string"
      - name: nxConvertTo
        desc: "Sets the case sensitivity of the mask."
        type: "'lower' | 'upper' | null | undefined"
      - name: separators
        desc: "Sets the keys that are recognized as separators. Default separators: / ( ) . : - + , and space."
        type: "string[]"
      - name: dropSpecialCharacters
        desc: "Whether the separators should be dropped in the control value accessor."
        type: "BooleanInput"
      - name: validateMask
        desc: "Whether the mask validation should be applied on the input. Default: true."
        type: "BooleanInput"
    methods:
      - name: registerBeforeInputHook
        params:
          - name: beforeInput
            type: (event: Event) => void
        desc: "Registers a function to be executed before the onInput handler."
        returnType: void
      - name: registerAfterInputHook
        params:
          - name: afterInput
            type: (event: Event) => void
        desc: "Registers a function to be executed after the onInput handler. The registered hook receives a `KeyboardEvent` from the onInput event handler as a parameter.  **Note:** If you register a `afterInputHook`, you may also register a `beforePasteHook` to perform similar changes for pasting."
        returnType: void
      - name: registerBeforePasteHook
        params:
          - name: beforePaste
            type: (event: ClipboardEvent) => void
        desc: "Registers a function to be executed before the onPaste handler. The registered hook receives a `ClipboardEvent` from the onPaste event handler as a parameter."
        returnType: void
      - name: getUnmaskedValue
        params: 
        returnType: string
      - name: setMask
        params:
          - name: value
            type: string
          - name: withUpdate
            type: boolean
        desc: "Sets the mask (for programmatical use). Use `withUpdate = false` to not call the internal updateValue function if needed.  No `_onChangeCallback()` will be called!"
        returnType: void
      - name: getMaskedString
        params:
          - name: inputValue
            type: string
          - name: maskStartIndex
            type: number
        returnType: string
      - name: validate
        params: 
        returnType: { nxMaskLengthError: { length: number; actual: any; }; } | null
  - name: NxIbanMaskDirective
    selector: input[nxIbanMask]
    desc: |
      To use the `NxIbanMaskDirective`, you have to install the **peer dependency** `iban.js`.
    methods:
      - name: validate
        params: 
        returnType: { nxIbanInvalidCountryError: string; nxIbanParseError?: undefined; } | { nxIbanParseError: string; nxIbanInvalidCountryError?: undefined; } | null

---