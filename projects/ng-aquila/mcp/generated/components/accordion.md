--- 
title: Accordion
category: components
alias: expansion panel, collapse

module: NxAccordionModule
components:
  - name: NxAccordionDirective
    selector: nx-accordion
    inputs:
      - name: variant
        desc: "Value for the styling that should be chosen.  Default: `'regular'`."
        type: "'regular' | 'light' | 'extra-light'"
      - name: negative
        desc: "Whether the negative set of styles should be used."
        type: "BooleanInput"
      - name: flushAlignment
        type: "boolean"
  - name: NxExpansionPanelComponent
    selector: nx-expansion-panel
    inputs:
      - name: scrollIntoViewActive
        desc: "Whether scrollIntoView should be enabled."
        default: this._defaultOptions?.scrollIntoViewActive
        type: "boolean | undefined"
      - name: scrollIntoViewOptions
        desc: "Configuration for the scrollIntoView behaviour after the expand animation is done."
        default: this._defaultOptions?.scrollIntoViewOptions
        type: "ScrollIntoViewOptions | undefined"
      - name: negative
        desc: "Whether the negative set of styles should be used."
        type: "BooleanInput"
      - name: variant
        desc: "Value for the styling that should be chosen. Default: `'regular'`."
        type: "'regular' | 'light' | 'extra-light'"
      - name: flushAlignment
        desc: "Setting flush alignment style: no left/right padding in expansion panel header and body"
        type: "boolean"
    methods:
      - name: getOpenState
        params: 
        returnType: "open" | "closed"
      - name: bodyExpansionDone
        params:
          - name: event
            type: AnimationEvent
        returnType: void
  - name: NxExpansionPanelHeaderComponent
    selector: nx-expansion-panel-header
    methods:
      - name: isExpanded
        params: 
        returnType: boolean
      - name: getOpenState
        params: 
        returnType: string
      - name: toggle
        params: 
        desc: "Toggle the expansion panel."
        returnType: void
      - name: keydown
        params:
          - name: event
            type: KeyboardEvent
        returnType: void
  - name: NxExpansionPanelDescriptionDirective
    selector: nx-expansion-panel-description
    desc: |
      This directive is to be used inside of the NxExpansionPanelHeader component.
  - name: NxExpansionPanelTitleDirective
    selector: nx-expansion-panel-title
    desc: |
      This directive is to be used inside of the NxExpansionPanelHeader component.
  - name: NxExpansionPanelBodyDirective
    selector: [nxExpansionPanelBody]

---