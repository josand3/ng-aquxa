--- 
title: Timefield
category: components
alias: timepicker

module: NxTimefieldModule
components:
  - name: NxTimefieldOption
    selector: [nxTimefieldOption]
    inputs:
      - name: value
        default: ''
        type: "string"
      - name: selected
        default: false
        type: "boolean"
    methods:
      - name: setActiveStyles
        params: 
        returnType: void
      - name: setInactiveStyles
        params: 
        returnType: void
      - name: getLabel
        params: 
        returnType: string
  - name: NxTimefieldControl
    selector: nx-timefield-control
    inputs:
      - name: value
        default: null
        type: "string | null"
      - name: focused
        default: false
        type: "boolean"
      - name: required
        default: false
        type: "boolean"
      - name: disabled
        default: false
        type: "boolean"
      - name: readonly
        default: false
        type: "boolean"
      - name: errorState
        default: false
        type: "boolean"
      - name: placeholder
        default: ''
        type: "string"
      - name: updateOn
        default: 'change'
        type: "'change' | 'blur'"
    methods:
      - name: setDescribedByIds
        params:
          - name: ids
            type: string[]
        returnType: void
      - name: setAriaLabel
        params:
          - name: value
            type: string
        returnType: void
  - name: NxTimefieldComponent
    selector: nx-timefield
    inputs:
      - name: appearance
        default: this._formfieldDefaultOptions?.appearance ?? 'auto'
        type: "'outline' | 'auto'"
      - name: hint
        default: ''
        type: "string"
      - name: optionalLabel
        default: ''
        type: "string"
      - name: inputMode
        desc: "The inputmode for the formfield."
        default: 'decimal'
        type: "'decimal' | 'numeric' | 'tel' | 'text'"
      - name: enableTimeValidation
        default: false
        type: "boolean"
      - name: pickerStartTime
        default: DEFAULT_START_TIME
        type: "string"
      - name: pickerEndTime
        default: DEFAULT_END_TIME
        type: "string"
      - name: pickerTimeInterval
        default: DEFAULT_TIME_SPAN
        type: "number"
      - name: withTimepicker
        type: "boolean"
      - name: twelveHourFormat
        desc: "Whether to show the time in 12-hour format with AM/PM toggle. Default: false."
        type: "BooleanInput"
      - name: label
        desc: "Sets the label which is displayed on top of timefield."
        type: "string"
      - name: labelAM
        desc: "Sets the AM radio button label which is displayed in radio group."
        type: "string"
      - name: labelPM
        desc: "Sets the PM radio button label which is displayed in radio group."
        type: "string"
      - name: placeholderHours
        desc: "Sets the placeholder of hours field. Default: 'hh'"
        type: "string"
      - name: placeholderMinutes
        desc: "Sets the placeholder of minutes field. Default: 'mm'"
        type: "string"
      - name: required
        desc: "Whether the timefield is required."
        type: "BooleanInput"
      - name: negative
        desc: "Whether the timefield uses the negative set of styling."
        type: "BooleanInput"
      - name: disabled
        desc: "Whether the timefield is disabled."
        type: "BooleanInput"
    outputs:
      - name: valueChange
        type: "EventEmitter<string>"
    methods:
      - name: handleKeyDown
        params:
          - name: event
            type: KeyboardEvent
        returnType: void
      - name: validate
        params:
          - name: control
            type: AbstractControl<any, any, any>
        returnType: ValidationErrors | null
      - name: updateErrorState
        params: 
        returnType: void
      - name: toggleOverlay
        params: 
        returnType: void
      - name: openOverlay
        params: 
        returnType: void
      - name: closeOverlay
        params: 
        returnType: void
      - name: toggleButtonClick
        params: 
        returnType: void
      - name: selectOption
        params:
          - name: value
            type: string | undefined
        returnType: void
      - name: preventFocus
        params:
          - name: event
            type: Event
        returnType: void
      - name: scrollSelectedItemIntoView
        params: 
        returnType: void
      - name: findClosestOption
        params:
          - name: time
            type: string
        returnType: NxTimefieldOption | undefined
      - name: scrollOptionIntoView
        params:
          - name: option
            type: NxTimefieldOption
        returnType: void
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
      - name: getLabelledBy
        params: 
        returnType: any

---
# Overview
The timefield component makes it easier for users to enter time inputs. Maximum character length per input field is 2 and by default it accepts time inputs in 24h format (ex: 23:00, 12:35,...). Programmatic time input is always accepted in `ISO 24h` time format.

In 24h format you can enter hours between 0-23 and minutes between 0-59. Using the `twelveHourFormat` input of the timefield component, the AM/PM toggler can be activated. In 12h format you can enter hours between 1-12 and minutes between 0-59. Note that the model will always accept and return time in 24h format.
