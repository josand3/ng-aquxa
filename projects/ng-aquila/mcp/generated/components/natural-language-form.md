--- 
title: Natural Language Form
category: components
alias: text form, inline field

module: NxNaturalLanguageFormModule
components:
  - name: NxNaturalLanguageFormComponent
    selector: nx-natural-language-form
    inputs:
      - name: negativeStyles
        desc: "Whether the negative set of stylings should be used."
        type: "BooleanInput"
      - name: size
        desc: "Sets the size of the NLF. Default value: large."
        type: "'small' | 'large'"
    methods:
      - name: onResize
        params:
          - name: event
            type: Event
        returnType: void
      - name: resizeWords
        params: 
        returnType: void
      - name: updatePositionPopovers
        params: 
        returnType: void
  - name: NxWordComponent
    selector: nx-word
    inputs:
      - name: size
        desc: "Provide a hint for a minimal width. The actual size will be determined for inputs for each change."
        default: 'regular'
        type: "'regular' | 'short' | 'long'"
      - name: label
        desc: "A word doesn't have a set place to show labels. In order to be accessible, you have to provide a label with this property. It will be attached to the given input through `aria-label`."
        default: ''
        type: "string"
      - name: describedByInput
        desc: "Sets the `aria-describedby` for the formfield. Should be used to refer to the individual error message.  If not set it will be set to the id of the entire error message or the error message inside the nx-word (deprecated)  Should be space seperated list of `id`s."
        default: input<string | undefined>(undefined, { alias: 'describedBy' })
        type: "InputSignal<string | undefined>"
    methods:
      - name: updateCurrentTextWidth
        params: 
        desc: "Calculate the width of the full text given by the input, that value is bound to this component so it can grow.  The involved input is known to have a width of 100% an will fit the additional space given which completes the auto growing behavior."
        returnType: void
      - name: repositionError
        params: 
        returnType: void
      - name: getConnectedOverlayOrigin
        params: 
        returnType: ElementRef<any>
      - name: updateErrorPopoverState
        params: 
        returnType: void
      - name: setupErrorPopover
        params: 
        returnType: void
      - name: showPopover
        params: 
        returnType: void
      - name: hidePopover
        params: 
        returnType: void
  - name: NxWordComponent
    selector: nx-word
    inputs:
      - name: size
        desc: "Provide a hint for a minimal width. The actual size will be determined for inputs for each change."
        default: 'regular'
        type: "'regular' | 'short' | 'long'"
      - name: label
        desc: "A word doesn't have a set place to show labels. In order to be accessible, you have to provide a label with this property. It will be attached to the given input through `aria-label`."
        default: ''
        type: "string"
      - name: describedByInput
        desc: "Sets the `aria-describedby` for the formfield. Should be used to refer to the individual error message.  If not set it will be set to the id of the entire error message or the error message inside the nx-word (deprecated)  Should be space seperated list of `id`s."
        default: input<string | undefined>(undefined, { alias: 'describedBy' })
        type: "InputSignal<string | undefined>"
    methods:
      - name: updateCurrentTextWidth
        params: 
        desc: "Calculate the width of the full text given by the input, that value is bound to this component so it can grow.  The involved input is known to have a width of 100% an will fit the additional space given which completes the auto growing behavior."
        returnType: void
      - name: repositionError
        params: 
        returnType: void
      - name: getConnectedOverlayOrigin
        params: 
        returnType: ElementRef<any>
      - name: updateErrorPopoverState
        params: 
        returnType: void
      - name: setupErrorPopover
        params: 
        returnType: void
      - name: showPopover
        params: 
        returnType: void
      - name: hidePopover
        params: 
        returnType: void

---