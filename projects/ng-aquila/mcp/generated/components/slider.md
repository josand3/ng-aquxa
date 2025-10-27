--- 
title: Slider
category: components
alias: number input, range

module: NxSliderModule
components:
  - name: NxSliderComponent
    selector: nx-slider
    inputs:
      - name: valueFormatter
        desc: "Sets the customization function for the value which is displayed above the slider handle (Default:(value) => value). )."
        default: (value: any) => value
        type: "(value: any) => any"
      - name: labelMinFormatter
        desc: "Sets the customization function for the label on the min-side of the slider (Default:(value) => value)."
        default: (value: any) => value
        type: "(value: any) => any"
      - name: labelMaxFormatter
        desc: "Sets the customization function for the label on the max-side of the slider (Default:(value) => value)."
        default: (value: any) => value
        type: "(value: any) => any"
      - name: tickInterval
        desc: "How often to show ticks. Relative to the step so that a tick always appears on a step. Ex: Tick interval of 4 with a step of 3 will draw a tick every 4 steps (every 12 values)."
        type: "NumberInput"
      - name: tabindex
        desc: "Sets the tabindex of the slider."
        type: "NumberInput"
      - name: min
        desc: "Sets the minimum value (Default: 0)."
        type: "NumberInput"
      - name: max
        desc: "Sets the maximum value (Default: 100)."
        type: "NumberInput"
      - name: step
        desc: "Sets the step size by which the value of the slider can be increased or decreased (Default: 1)."
        type: "NumberInput"
      - name: label
        desc: "Sets the label which is displayed on top of the slider."
        type: "string"
      - name: disabled
        desc: "Whether the input to the control of the slider should be disabled."
        type: "BooleanInput"
      - name: inverted
        desc: "Whether the max value is to the right (false) or left (true)."
        type: "BooleanInput"
      - name: thumbLabel
        desc: "Whether to display the thumb label on top of the slider."
        type: "BooleanInput"
      - name: value
        desc: "Sets the current value of the slider."
        type: "NumberInput"
      - name: negative
        desc: "Whether the negative set of styles is applied (Default: 'false')."
        type: "BooleanInput"
      - name: hideLabels
        desc: "Hides the min/max labels (Default: 'false')."
        type: "BooleanInput"
      - name: longTicks
        desc: "Sets the array of value which will render as long tick (Default: Middle value if present)."
        type: "number[]"
    outputs:
      - name: valueChange
        desc: "An event is dispatched on each value change."
        type: "EventEmitter<number>"
    methods:
      - name: setDisabledState
        params:
          - name: disabled
            type: boolean
        returnType: void
  - name: NxSliderAppendixDirective
    selector: [nxSliderAppendix]

---
# Overview
The slider component allows the user to select a value from a range between a minimum and a maximum value, using a given granularity (e.g. step size). The value can be selected via mouse, touch or keyboard (arrow keys).

For better decimal/floating point handling this module is using the 3rd party library [decimal.js](http://mikemcl.github.io/decimal.js/) which is required in the library dependencies and will be installed automatically.
