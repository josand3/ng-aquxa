--- 
title: Number Stepper
category: components
alias: number input, range

module: NxNumberStepperModule
components:
  - name: NxNumberStepperComponent
    selector: nx-number-stepper
    desc: |
      `Input('size') classNames` defines the size of the number stepper.
      
      Values: `'big' | 'normal'`.
      
      Default: `'normal'`.
    inputs:
      - name: ariaDescribedBy
        default: input<string | null>(null)
        type: "InputSignal<string | null>"
      - name: label
        default: input<string | null>(null)
        type: "InputSignal<string | null>"
      - name: inputAriaLabel
        desc: "Sets the aria-label for the input of the number stepper."
        default: input<string | null>(null)
        type: "InputSignal<string | null>"
      - name: leadingZero
        desc: "Whether the number stepper value should have a leading zero.  Default: `true`."
        default: input(true, {
      transform: booleanAttribute,
    })
        type: "InputSignalWithTransform<boolean, unknown>"
      - name: inputFieldReadonly
        desc: "Whether the user can directly interact with the input value via input field. Default: false"
        default: input(false, {
      transform: booleanAttribute,
      alias: 'inputFieldReadonly',
    })
        type: "InputSignalWithTransform<boolean, unknown>"
      - name: resize
        desc: "Whether the input should be resized. Default: false"
        type: "BooleanInput"
      - name: incrementAriaLabel
        desc: "Sets the aria-label for the increment button."
        type: "string"
      - name: decrementAriaLabel
        desc: "Sets the aria-label for the decrement button."
        type: "string"
      - name: step
        desc: "Sets the step size. Default: 1"
        type: "NumberInput"
      - name: min
        desc: "Sets the minimum accepted number. Default: 0"
        type: "NumberInput"
      - name: max
        desc: "Sets the maximum accepted number. Default: 100"
        type: "NumberInput"
      - name: value
        desc: "Sets the value of the number-stepper."
        type: "number | null"
      - name: negative
        desc: "Whether the negative set of styling should be used."
        type: "BooleanInput"
      - name: disabled
        desc: "Whether the user input in the number stepper should be disabled.  Default: `false`."
        type: "BooleanInput"
      - name: readonly
        desc: "Whether the user can directly interact with the input field and buttons. Default: false"
        type: "BooleanInput"
    outputs:
      - name: valueChange
        desc: "An event emitted on value change."
        type: "EventEmitter<number>"
    methods:
      - name: onInputChange
        params:
          - name: event
            type: Event
        returnType: void
      - name: disabledButton
        params: 
        returnType: true | null
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        desc: "Disables the stepper. Part of the ControlValueAccessor interface required to integrate with Angular's core forms API."
        returnType: void
      - name: validateUserInput
        params:
          - name: input
            type: string
        returnType: boolean
      - name: incrementOnClick
        params: 
        returnType: void
      - name: incrementOnKey
        params:
          - name: event
            type: Event
        returnType: void
      - name: triggerResize
        params: 
        returnType: void
      - name: decrementOnClick
        params: 
        returnType: void
      - name: decrementOnKey
        params:
          - name: event
            type: Event
        returnType: void
      - name: enforceLimits
        params:
          - name: value
            type: number
        returnType: number
      - name: getNextLowerValue
        params:
          - name: start
            type: number
        returnType: number
      - name: getNextGreaterValue
        params:
          - name: start
            type: number
        returnType: number
      - name: isBetweenLimits
        params:
          - name: value
            type: number | Decimal
        returnType: boolean
      - name: isMinimum
        params: 
        returnType: boolean
      - name: isMaximum
        params: 
        returnType: boolean
      - name: isValidStep
        params:
          - name: value
            type: number | Decimal | null
        returnType: boolean
      - name: userInputToNumber
        params:
          - name: value
            type: string
        returnType: number
      - name: handleBlur
        params: 
        returnType: void
      - name: validate
        params:
          - name: c
            type: FormControl<any>
        returnType: { nxNumberStepperFormatError: string; nxNumberStepperStepError?: undefined; } | { nxNumberStepperStepError: string; nxNumberStepperFormatError?: undefined; } | null
  - name: NxAutoResizeDirective
    selector: input[nxAutoResize]
    inputs:
      - name: nxAutoResize
        type: "BooleanInput"
    methods:
      - name: updateInputWidth
        params: 
        returnType: void
      - name: sumStyles
        params:
          - name: left
            type: string
          - name: right
            type: string
        returnType: number
  - name: NxNumberStepperPrefixDirective
    selector: nx-number-stepper-prefix
    desc: |
      Directive used to pass a suffix to the number stepper.
  - name: NxNumberStepperSuffixDirective
    selector: nx-number-stepper-suffix
    desc: |
      Directive used to pass a suffix to the number stepper.

---