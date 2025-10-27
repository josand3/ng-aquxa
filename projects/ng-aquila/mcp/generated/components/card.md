--- 
title: Cards
category: components
alias: card, selectable card

module: NxCardModule
components:
  - name: NxCardMainLinkDirective
    selector: [nxCardMainLink]
  - name: NxCardSecondaryInfoDirective
    selector: [nxCardSecondaryInfo]
  - name: NxCardComponent
    selector: nx-card
    inputs:
      - name: clickable
        default: false
        type: "boolean"
      - name: disabled
        default: false
        type: "boolean"
      - name: highlight
        desc: "Whether the card is highlight."
        type: "BooleanInput"
  - name: NxSelectableCardComponent
    selector: nx-selectable-card
    inputs:
      - name: appearance
        desc: "**Expert option**  Sets the appearance of the small stage. Default: 'default'."
        type: "'expert' | 'default'"
      - name: checked
        desc: "Whether the selectable card  is checked."
        type: "BooleanInput"
      - name: value
        desc: "The value attribute of the native input element"
        type: "string"
      - name: disabled
        desc: "Whether the selectable card is disabled."
        type: "BooleanInput"
      - name: negative
        desc: "Whether the selectable card is negative."
        type: "BooleanInput"
      - name: required
        desc: "Whether the selectable card is required."
        type: "BooleanInput"
      - name: name
        desc: "Name of the selectable card."
        type: "string"
      - name: tabindex
        desc: "The tabindex of the selectable card."
        type: "string"
      - name: highlight
        desc: "Whether the selectable card  is highlight."
        type: "BooleanInput"
    outputs:
      - name: selectionChange
        desc: "An event is dispatched each time the selectable card value is changed"
        type: "EventEmitter<NxSelectableCardChangeEvent>"
      - name: checkedChange
        desc: "An event is dispatched each time the selectable card value is changed"
        type: "EventEmitter<boolean>"
    methods:
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
      - name: toggle
        params: 
        desc: "Toggles the checked state of the selectable card ."
        returnType: void
  - name: NxCardHeaderComponent
    selector: nx-card-header
  - name: NxCardFooterComponent
    selector: nx-card-footer
  - name: NxSelectableCardGroupComponent
    selector: nx-selectable-card-group
    inputs:
      - name: value
        type: "any"
    methods:
      - name: change
        params:
          - name: value
            type: any
        returnType: void
      - name: updateErrorState
        params: 
        returnType: void

---
# Overview
Use this component to present a card with different options.
