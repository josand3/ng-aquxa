--- 
title: Phone Input
category: components

module: NxPhoneInputModule
components:
  - name: NxPhoneInputComponent
    selector: nx-phone-input
    inputs:
      - name: required
        desc: "Whether the component should be required."
        type: "BooleanInput"
      - name: disabled
        desc: "Whether the component should be disabled."
        type: "BooleanInput"
      - name: readonly
        desc: "Whether the component should be read only."
        type: "BooleanInput"
      - name: countryCode
        desc: "Sets the initial country to be selected in the dropdown. Format is the international country code like DE, US. If there is already a number in the input field changing this property has no effect."
        type: "string"
      - name: areaCodeLabel
        desc: "Set the text at the top of the dropdown and aria-label of area code field. The default value is 'Area Code'."
        type: "string"
      - name: lineNumberLabel
        desc: "Sets the aria-label of line number field."
        type: "string"
      - name: countryNames
        desc: "Set the translations of the countries."
        type: "LocalizedCountryNames<any>"
      - name: placeholder
        desc: "The placeholder to be shown in the input field."
        type: "string"
      - name: inputFormatter
        desc: "Function to format the value in the input part of the component. The function is called on blur. The default function removes leading zeros. Please note: to determine the model value the component will remove parenthesis, whitespace and dash characters from the formatted input."
        type: "(inputValue: string, countryCode: string) => string"
    outputs:
      - name: focusOut
        type: "EventEmitter<boolean>"
      - name: focusIn
        type: "EventEmitter<boolean>"
    methods:
      - name: setReadonly
        params:
          - name: value
            type: boolean
        desc: "set readonly state"
        returnType: void
      - name: setDescribedByIds
        params:
          - name: ids
            type: string[]
        returnType: void
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
      - name: updateErrorState
        params: 
        returnType: void
      - name: updateModel
        params: 
        returnType: void
      - name: getModelValue
        params: 
        desc: "Returns the combined string of selected calling code + input number"
        returnType: string

---