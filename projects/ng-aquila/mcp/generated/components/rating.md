--- 
title: Rating
category: components

module: NxRatingModule
components:
  - name: NxRatingComponent
    selector: nx-rating
    inputs:
      - name: size
        type: "'auto' | 's' | 'm' | 'l' | 'xl'"
      - name: value
        desc: "Sets the selected rating 1 - 5."
        type: "NumberInput"
      - name: disabled
        desc: "Whether the rating component should be disabled."
        type: "BooleanInput"
      - name: negative
        desc: "Whether the negative colors be used."
        type: "BooleanInput"
      - name: startLabel
        desc: "Sets the label painted at the start of the rating component."
        type: "string"
      - name: endLabel
        desc: "Sets the label painted at the end of the rating component."
        type: "string"
      - name: ariaLabel
        type: "string[]"
      - name: ariaRatingLabels
        desc: "Sets an array of custom aria-label attributes for the individual ratings."
        type: "string[]"
      - name: ariaRatingGroupLabel
        type: "string | null"
      - name: iconColor
        type: "string"
    outputs:
      - name: valueChange
        desc: "An event is dispatched each time when the rating changes."
        type: "EventEmitter<number>"
    methods:
      - name: getRadioInputId
        params:
          - name: index
            type: number
        returnType: string
      - name: isSelected
        params:
          - name: index
            type: number
        desc: "Whether the given rating is selected."
        returnType: boolean
      - name: isVisuallyChecked
        params:
          - name: rating
            type: number
        returnType: boolean
      - name: setSelection
        params:
          - name: value
            type: number
        desc: "Allows to set the rating."
        returnType: void
      - name: handleKeyUp
        params:
          - name: event
            type: KeyboardEvent
          - name: rating
            type: number
        returnType: void
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
      - name: getAriaLabel
        params:
          - name: rating
            type: number
        returnType: string
      - name: getIconName
        params:
          - name: rating
            type: number
        returnType: string
      - name: setHover
        params:
          - name: rating
            type: number
        returnType: void
      - name: handleChange
        params:
          - name: ratingValue
            type: number
        returnType: void

---