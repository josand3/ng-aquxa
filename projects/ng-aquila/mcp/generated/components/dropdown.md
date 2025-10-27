--- 
title: Dropdown
category: components
alias: select, multi select

module: NxDropdownModule
components:
  - name: NxDropdownComponent
    selector: nx-dropdown
    inputs:
      - name: ariaLabelledBy
        default: null
        type: "string | null"
      - name: verticalAlignCheckmark
        default: 'top'
        type: "'top' | 'center'"
      - name: isMultiSelect
        desc: "Whether the dropdown should allow multi selection and additional checkboxes are shown. Note: Please make sure the value you bind is an array.@throws Error if true and the bound value is not an array.    * @deprecated Please use the new `<nx-multi-select>` component instead."
        default: false
        type: "boolean"
      - name: showFilter
        desc: "Whether the dropdown should be shown with an additional filter input."
        default: false
        type: "boolean"
      - name: filterPlaceholder
        desc: "Text displayed as placeholder for the filter."
        default: ''
        type: "string"
      - name: overlayLabel
        desc: "Text that is displayed at the top of the overlay. If not set the formfield label is used by default."
        default: ''
        type: "string"
      - name: overlayFallbackOrigin
        desc: "Can be used as a fallback to the CdkOverlayOrigin"
        type: "NxDropdownComponent"
      - name: panelMaxWidth
        type: "string | number"
      - name: readonly
        desc: "Whether the dropdown is readonly."
        type: "BooleanInput"
      - name: options
        desc: "Array of options for the dropdown."
        type: "NxDropdownOption[]"
      - name: filterInputType
        desc: "Type of filter input (default: text)."
        type: "| 'text'  | 'number'  | 'tel'  | 'search'  | 'date'  | 'datetime'  | 'month'  | 'email'"
      - name: tabIndex
        type: "number"
      - name: value
        desc: "Selected value"
        type: "any"
      - name: disabled
        desc: "Whether the dropdown is disabled."
        type: "BooleanInput"
      - name: required
        desc: "Whether the component is required. This adds an aria-required label to the component."
        type: "BooleanInput"
      - name: variant
        desc: "If set to 'negative', the component is displayed with the negative set of styles."
        type: "string"
      - name: placeholder
        desc: "Placeholder to be shown if no value has been selected."
        type: "string"
      - name: ignoreItemTruncation
        desc: "Disable truncation of long item texts. We recommend following UX guidelines and always truncating long items. Please only disable truncation if it's impossible to use short descriptions."
        type: "BooleanInput"
      - name: panelMinWidth
        desc: "Sets how the panel min width will be determined. 'trigger' will set the panels min-width to the trigger width. 'none' will not set a min-width and will let the panel grow naturally with its content so it can be smaller than the trigger. This is mostly for special use cases like the country code dropdown in the phone input."
        type: "'trigger' | 'none'"
      - name: panelGrow
        desc: "panelGrow: true means the overlay can grow larger than the trigger and grows with the longest label panelGrow: false means the overlay is the size of the trigger"
        type: "boolean"
      - name: valueFormatter
        desc: "Function that transforms the value into a string. This function is used for displaying and filtering the content.  Default: `(value: any) => value == null ? '' : value.toString()`."
        type: "((value: any) => any) | null | undefined"
      - name: compareWith
        desc: "Function to compare the option values with the selected values. The first argument is a value from an option. The second is a value from the selection. A boolean should be returned.  Defaults to object equality."
        type: "((o1: any, o2: any) => boolean) | null | undefined"
      - name: filterFn
        desc: "Function to be used when the user types into the search filter. The first argument is the user input, the second argument is the dropdown item value as displayed. The dropdown items will use this function to set their visibility state. A boolean should be returned.  Defaults to lower case inclusion."
        type: "((query: string, label: string) => boolean) | null | undefined"
    outputs:
      - name: openedChange
        desc: "Event emitted when the select panel has been toggled."
        type: "EventEmitter<boolean>"
      - name: focusOut
        desc: "Event emitted when the select panel has been focus out."
        type: "EventEmitter<boolean>"
      - name: filterResultChange
        desc: "Event emitted when the dropdown items get filtered. Returns the currently visible dropdown items."
        type: "EventEmitter<NxDropdownItemComponent[]>"
      - name: filterChanges
        desc: "Event emitted when the user types in the filter input."
        type: "EventEmitter<any>"
      - name: valueChange
        desc: "Event that emits whenever the raw value of the select changes. This is here primarily to facilitate the two-way binding for the `value` input."
        type: "EventEmitter<any>"
      - name: selectionChange
        desc: "Event emitted when the selected value has been changed."
        type: "EventEmitter<NxDropdownSelectChange<any>>"
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
      - name: focus
        params: 
        desc: "Focuses the select element."
        returnType: void
      - name: openPanel
        params:
          - name: $event
            type: Event
        desc: "Opens the panel of the dropdown."
        returnType: void
      - name: closePanel
        params: 
        desc: "Closes the panel of the dropdown."
        returnType: void
      - name: setDescribedByIds
        params:
          - name: ids
            type: string[]
        desc: "Formfield implementation."
        returnType: void
      - name: setAriaLabel
        params:
          - name: value
            type: string
        desc: "Support for aria-label removed in favor of aria-labelledby The NxFormfieldControl abstract class requires implementation of below method."
        returnType: string
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        desc: "Disables the select. Part of the ControlValueAccessor interface required to integrate with Angular's core forms API."
        returnType: void
      - name: formatValue
        params:
          - name: value
            type: any
        returnType: string
  - name: NxDropdownItemComponent
    selector: nx-dropdown-item
    inputs:
      - name: value
        desc: "The value of the dropdown item. You can't use undefined, null and '' (empty strings) as they are sentinel values signalling empty data."
        type: "any"
      - name: disabled
        desc: "Whether the dropdown item is disabled."
        type: "BooleanInput"
    outputs:
      - name: onSelectionChange
        desc: "Event emitted when the option is selected or deselected."
        type: "EventEmitter<NxDropdownItemChange>"
    methods:
      - name: show
        params: 
        returnType: void
      - name: hide
        params: 
        returnType: void
      - name: select
        params: 
        returnType: void
      - name: deselect
        params: 
        returnType: void
      - name: focus
        params: 
        returnType: void
      - name: setActiveStyles
        params: 
        returnType: void
      - name: setInactiveStyles
        params: 
        returnType: void
      - name: getLabel
        params: 
        desc: "Returns the list item's text label. Implemented as a part of the ListKeyManagerOption."
        returnType: string
  - name: NxDropdownGroupComponent
    selector: nx-dropdown-group
    inputs:
      - name: label
        desc: "Label displayed in the group."
        type: "string"
  - name: NxDropdownClosedLabelDirective
    selector: [nxClosedLabel]
  - name: NxMultiSelectComponent
    selector: nx-multi-select
    desc: |
      Multi Select component.
    inputs:
      - name: filterPlaceholder
        desc: "Placeholder for the filter input."
        default: 'Type to filter'
        type: "string"
      - name: selectValue
        desc: "Selector to get the value of an option. Can be either a property name or a selector function. When providing objects as options, it is recommended to set selectValue to specify a unique identifier for each option. If selectValue is empty, the whole object is used for selection, which may cause issues if object references change."
        default: ''
        type: "string | ((option: S) => T)"
      - name: selectLabel
        desc: "Selector to get the label of an option. Can be either a property name or a selector function. When empty the whole option is treated as the label."
        default: ''
        type: "string | ((option: S) => string)"
      - name: selectDisabled
        desc: "Selector to get the disabled state of an option. Can be either a property name or a selector function."
        type: "string | ((option: S) => boolean) | undefined"
      - name: panelGrow
        desc: "panelGrow: true means the overlay can grow larger than the trigger and grows with the longest label panelGrow: false means the overlay is the size of the trigger"
        default: false
        type: "boolean"
      - name: panelMaxWidth
        type: "string | number"
      - name: required
        type: "boolean"
      - name: disabled
        desc: "Whether the multi select is disabled."
        type: "boolean"
      - name: readonly
        desc: "Whether the multi select should be read only."
        type: "BooleanInput"
      - name: placeholder
        desc: "The placeholder shown in the multi select field."
        type: "string"
      - name: filter
        desc: "Whether this multi select can be filtered."
        type: "BooleanInput"
      - name: disableSelectAll
        desc: "Whether the (select all / clear all) should be disabled and hidden."
        type: "BooleanInput"
      - name: filterFn
        desc: "Function to be used when the user types into the search filter. The first argument is the user input, the second argument is the dropdown item value as displayed. The dropdown items will use this function to set their visibility state. A boolean should be returned.  Defaults to lower case inclusion."
        type: "((query: string, label: string) => boolean) | null | undefined"
      - name: tabIndex
        type: "number"
      - name: options
        type: "S[]"
    outputs:
      - name: openedChange
        desc: "Event emitted when the select panel has been toggled."
        type: "EventEmitter<boolean>"
      - name: selectionChange
        desc: "Event emitted when the selected value has been changed."
        type: "EventEmitter<T[]>"
      - name: focusOut
        desc: "Event emitted when the select panel has been focus out."
        type: "EventEmitter<boolean>"
      - name: filterChanges
        desc: "Event emitted when the user types in the filter input."
        type: "EventEmitter<any>"
    methods:
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
      - name: setDescribedByIds
        params:
          - name: ids
            type: string[]
        returnType: void
      - name: open
        params:
          - name: $event
            type: Event
          - name: origin
            type: FocusOrigin
        returnType: void
      - name: updateErrorState
        params: 
        returnType: void
  - name: NxMultiSelectOptionComponent
    selector: nx-multi-select-option
    desc: |
      A single option witin the multi select.
    inputs:
      - name: appearance
        default: 'auto'
        type: "'outline' | 'auto'"
      - name: value
        desc: "Value of this option."
        type: "T | undefined"
      - name: label
        desc: "Label of this option."
        default: ''
        type: "string"
      - name: selected
        desc: "Whether this option is selected."
        default: false
        type: "boolean"
      - name: disabled
        desc: "Whether this option is disabled."
        default: false
        type: "boolean"
    outputs:
      - name: selectedChange
        desc: "Emits an event when this option is selected or unselected by the user."
        type: "EventEmitter<boolean>"
    methods:
      - name: setActiveStyles
        params: 
        returnType: void
      - name: setInactiveStyles
        params: 
        returnType: void
      - name: selectViaInteraction
        params: 
        desc: "Selects this option as if the user clicked on it."
        returnType: void
      - name: getLabel
        params: 
        returnType: string
  - name: NxMultiSelectAllComponent
    selector: nx-multi-select-all
    desc: |
      A single option witin the multi select.
    inputs:
      - name: value
        desc: "Value of this option."
        type: "T | undefined"
      - name: label
        desc: "Label of this option."
        default: ''
        type: "string"
      - name: selected
        desc: "Whether this option is selected."
        default: false
        type: "boolean"
      - name: disabled
        desc: "Whether thisoption is disabled."
        default: false
        type: "boolean"
      - name: indeterminate
        desc: "Indeterminate"
        type: "boolean"
    outputs:
      - name: selectedAllChange
        desc: "Emits an event when this option is selected or unselected by the user."
        type: "EventEmitter<boolean>"
    methods:
      - name: setActiveStyles
        params: 
        returnType: void
      - name: setInactiveStyles
        params: 
        returnType: void
      - name: selectViaInteraction
        params: 
        desc: "Selects this option as if the user clicked on it."
        returnType: void
      - name: getLabel
        params: 
        returnType: string

---
# Overview
It is recommended to use the dropdown component in combination with NxFormField. Therefore, make sure to import this module as well:

```ts
import { NxFormfieldModule } from '@allianz/ng-aquila/formfield';
```

Dropdown requires Angular CDK (incl. CSS). Learn [how to enable Angular CDK styles](./documentation/overlay/overview#angular-cdk).
