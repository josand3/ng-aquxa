--- 
title: Circle Toggle
category: components
alias: button, radio, toggle, checkbox

module: NxCircleToggleModule
components:
  - name: NxCircleToggleGroupComponent
    selector: nx-circle-toggle-group
    inputs:
      - name: name
        desc: "Name that is used for accessibility."
        type: "string"
      - name: disabled
        desc: "Whether the circle toggle group is disabled."
        type: "BooleanInput"
      - name: readonly
        type: "boolean"
      - name: negative
        desc: "Whether the circle toggle group uses the negative styling."
        type: "BooleanInput"
      - name: value
        desc: "The value of the selected circle toggle in the circle toggle group."
        type: "any"
      - name: responsive
        desc: "Whether the circle toggle group has a responsive behavior."
        type: "BooleanInput"
      - name: appearance
        desc: "**Expert option**  Sets the appearance of the circle toggle group.  Default: `'default'`."
        type: "'default' | 'expert'"
    outputs:
      - name: valueChange
        desc: "An event emitted when the selection changes. Outputs the value of the currently selected button."
        type: "EventEmitter<any>"
    methods:
      - name: touch
        params: 
        returnType: void
      - name: setReadonly
        params:
          - name: isReadonly
            type: boolean
        returnType: void
      - name: subscribeToSelectionChanges
        params: 
        returnType: void
      - name: notifySelectedChild
        params:
          - name: newValue
            type: string
        desc: "Inform the selected button if the group selection is set programattically at the beginning."
        returnType: void
      - name: updateToggleButtonsNames
        params: 
        returnType: void
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
  - name: NxCircleToggleComponent
    selector: nx-circle-toggle
    inputs:
      - name: ariaDescribedBy
        default: input<string | null>(null)
        type: "InputSignal<string | null>"
      - name: name
        desc: "Name that is used for accessibility."
        type: "string"
      - name: checked
        desc: "Whether the circle toggle is checked."
        type: "BooleanInput"
      - name: value
        desc: "The value that is used in the model."
        type: "any"
      - name: icon
        desc: "Id of the icon that should be displayed."
        type: "string"
      - name: svg
        desc: "SVG that is displayed if the circle toggle is unchecked."
        type: "string"
      - name: svgChecked
        desc: "SVG that is displayed if the circle toggle is checked."
        type: "string"
      - name: circleText
        desc: "A text that is displayed inside the circle toggle."
        type: "string"
      - name: label
        desc: "Label displayed below the circle."
        type: "string"
      - name: hint
        desc: "Additional hint displayed below the label."
        type: "string"
      - name: negative
        desc: "Whether the circle toggle uses the negative set of styling."
        type: "boolean"
      - name: responsive
        desc: "Whether the circle toggle has a responsive behavior."
        type: "boolean"
      - name: disabled
        desc: "Whether the circle toggle is disabled."
        type: "boolean"
      - name: readonly
        type: "boolean"
      - name: appearance
        desc: "**Expert option**  Sets the appearance of the circle toggle.  Default: `'default'`."
        type: "'default' | 'expert'"
    outputs:
      - name: checkedChange
        desc: "An event that is emitted when the checked state fo the circle toggle changes."
        type: "EventEmitter<boolean>"
      - name: selectionChange
        desc: "An event that is emitted when the checked state of the circle toggle changes. The event object contains the circle toggle itself and its value (see ToggleChangeEvent)."
        type: "EventEmitter<ToggleChangeEvent>"
    methods:
      - name: onMouseEnter
        params: 
        returnType: void
      - name: onMouseLeave
        params: 
        returnType: void
      - name: onTouchStart
        params: 
        returnType: void
      - name: setReadonly
        params:
          - name: isReadonly
            type: boolean
        returnType: void
      - name: attachListenerForGroup
        params: 
        returnType: void
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
      - name: focus
        params:
          - name: focusOrigin
            type: FocusOrigin | undefined
        desc: "Focuses the radio button element."
        returnType: void
      - name: toggle
        params:
          - name: event
            type: Event
        returnType: void
      - name: setGroupSelection
        params:
          - name: checked
            type: boolean
        desc: "Method called by the group if the internal value of the group is changed programatically, does not trigger change emission."
        returnType: void
      - name: handleEnterKey
        params:
          - name: event
            type: Event
        returnType: void
      - name: touch
        params: 
        returnType: void
  - name: NxIconToggleButtonComponent
    selector: nx-icon-toggle-button
    inputs:
      - name: inGroup
        default: true
        type: "boolean"
      - name: hint
        default: ''
        type: "string"
      - name: label
        default: ''
        type: "string"
      - name: checked
        default: false
        type: "boolean"
      - name: icon
        default: ''
        type: "string"
      - name: disabled
        default: false
        type: "boolean"
      - name: negative
        default: false
        type: "boolean"
      - name: touched
        default: false
        type: "boolean"
      - name: circleText
        default: ''
        type: "string"
      - name: readonly
        default: false
        type: "boolean"
      - name: svg
        default: ''
        type: "string"
  - name: NxMobileToggleButtonComponent
    selector: nx-mobile-toggle-button
    inputs:
      - name: checked
        default: false
        type: "boolean"
      - name: negative
        default: false
        type: "boolean"
      - name: disabled
        default: false
        type: "boolean"
      - name: readonly
        default: false
        type: "boolean"
      - name: hint
        default: ''
        type: "string"
      - name: label
        default: ''
        type: "string"
      - name: circleText
        default: ''
        type: "string"
    methods:
      - name: setFirstButton
        params: 
        returnType: void
      - name: setLastButton
        params: 
        returnType: void
      - name: resetClasses
        params: 
        returnType: void

---
# Overview
The toggle circle can be used as standalone toggle circle (checkbox role) or multiple toggle circles can be grouped with the circle toggle group wrapper and fullfill a radio group role.

Use this component to illustrate what information your checkbox communicates by integrating an icon or custom SVG. In order to edit your SVGs correctly, it should be 80x80px in size. You can use the viewBox attribute to do so. Since the circle has a diameter of 80, it will fit neatly at the edges and cut off the images' corners.<br> This is how the feature is currently implemented in the desktop version.<br> To avoid cutting off the corners you may, however, decide to place a smaller version of the SVG wholly inside the circle. The icon or SVG you use should not have a border as it is a part of the component itself and in case the icon is not shown the user will still see a good looking empty button with a label.
