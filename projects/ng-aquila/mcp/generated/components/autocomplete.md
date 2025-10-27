--- 
title: Autocomplete
category: components

module: NxAutocompleteModule
components:
  - name: NxAutocompleteComponent
    selector: nx-autocomplete
    inputs:
      - name: valueFormatter
        desc: "Value to string converter function. As an autocomplete option can hold any value, a converter might be needed to get a string representation of the value, which can be stored in the input.  Default: `value => value ? value.toString() : null`."
        default: (value: any) =>
      value ? value.toString() : null
        type: "(value: any) => string"
      - name: items
        desc: "Items observable. If given, autocomplete takes care of the options and ng-content is discarderd"
        type: "string[] | Observable<string[]>"
      - name: class
        desc: "Takes classes set on the host nx-autocomplete element and applies them to the panel inside the overlay container to allow for easy styling."
        type: "string"
    outputs:
      - name: optionSelected
        desc: "Event that is emitted whenever an option from the list is selected."
        type: "EventEmitter<NxAutocompleteSelectedEvent>"
      - name: opened
        desc: "Event that is emitted when the autocomplete panel is opened."
        type: "EventEmitter<void>"
      - name: closed
        desc: "Event that is emitted when the autocomplete panel is closed."
        type: "EventEmitter<void>"
  - name: NxAutocompleteOptionComponent
    selector: nx-autocomplete-option
    inputs:
      - name: value
        desc: "The value of the autocomplete option."
        type: "any"
      - name: disabled
        desc: "Whether the option is disabled."
        type: "BooleanInput"
    outputs:
      - name: onSelectionChange
        desc: "Event emitted when the option is selected or deselected."
        type: "EventEmitter<NxAutocompleteOptionSelected>"
    methods:
      - name: setActiveStyles
        params: 
        desc: "This method sets display styles on the option to make it appear active. This is used by the ActiveDescendantKeyManager so key events will display the proper options as active on arrow key events."
        returnType: void
      - name: setInactiveStyles
        params: 
        desc: "This method removes display styles on the option that made it appear active. This is used by the ActiveDescendantKeyManager so key events will display the proper options as active on arrow key events."
        returnType: void
      - name: getLabel
        params: 
        desc: "Gets the label to be used when determining whether the option should be focused."
        returnType: string
      - name: select
        params: 
        desc: "Selects the option."
        returnType: void
      - name: deselect
        params: 
        desc: "Deselects the option."
        returnType: void
      - name: focus
        params: 
        desc: "Sets focus onto this option."
        returnType: void
  - name: NxAutocompleteTriggerDirective
    selector: input[nxAutocomplete], textarea[nxAutocomplete]
    inputs:
      - name: nxAutocomplete
        desc: "The autocomplete panel to be attached to this trigger."
        type: "NxAutocompleteComponent"
      - name: panelGrow
        default: false
        type: "boolean"
      - name: panelMaxWidth
        default: ''
        type: "string | number"
      - name: nxAutocompleteItems
        desc: "The items callback. Called with input value, must return Observable of Array of strings"
        type: "(val: string) => Observable<string[]>"
      - name: nxAutocompleteDebounce
        desc: "Debounce in ms before items callback is triggered. Defaults to 400"
        type: "NumberInput"
      - name: nxAutocompleteDisabled
        desc: "Whether autocomplete functionality is disabled."
        type: "boolean"
    methods:
      - name: openPanel
        params: 
        desc: "Opens the autocomplete suggestion panel."
        returnType: void
      - name: closePanel
        params: 
        desc: "Closes the autocomplete suggestion panel."
        returnType: void
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void

---
# Overview
Autocomplete is a companion to the input element. When input element receives a focus or a down arrow is pressed and autocomplete items are defined, the autcomplete panel is displayed. On selecting the autocomplete option, it's value is used to set the value of input.
