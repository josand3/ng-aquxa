--- 
title: Tabs
category: components
alias: navigation tabs

module: NxTabsModule
components:
  - name: NxTabComponent
    selector: nx-tab
    inputs:
      - name: label
        desc: "Sets the label of the tab shown in the tablist."
        type: "string"
      - name: disabled
        desc: "Sets the tab to disabled."
        type: "BooleanInput"
  - name: NxTabGroupComponent
    selector: nx-tab-group
    inputs:
      - name: selectedIndex
        desc: "Sets the selected tab."
        type: "NumberInput"
      - name: negative
        desc: "Whether the negative set of styling should be used."
        type: "BooleanInput"
      - name: disabled
        desc: "Whether the tab group is disabled. Default: false."
        type: "BooleanInput"
      - name: autoselect
        desc: "Whether the tab should be immediately selected on focus."
        type: "BooleanInput"
      - name: mobileAccordion
        desc: "Whether the tabs should to accordion on mobile viewports."
        type: "BooleanInput"
      - name: appearance
        desc: "**Expert option**  Sets the appearance of the tab group. Default: 'default'."
        type: "'expert' | 'default'"
    outputs:
      - name: selectedIndexChange
        desc: "An event emitted when the selected tab has changed."
        type: "EventEmitter<number>"
      - name: selectedTabChange
        desc: "An event emitted when the selected tab has changed."
        type: "EventEmitter<NxTabChangeEvent>"
      - name: focusChange
        desc: "An event emitted when focus has changed within a tab group.  **Note:** is not supported in mobile view."
        type: "EventEmitter<NxTabChangeEvent>"
    methods:
      - name: focusChanged
        params:
          - name: index
            type: number
        returnType: void
      - name: handleClick
        params:
          - name: index
            type: number
        returnType: void
      - name: getTabIndex
        params:
          - name: tab
            type: NxTabComponent
          - name: idx
            type: number
        desc: "Returns the tabindex for a tab label."
        returnType: number | null
  - name: NxTabLabelDirective
    selector: [nxTabLabel]
  - name: NxTabLabelWrapperDirective
    selector: [nxTabLabelWrapper]
    inputs:
      - name: disabled
        desc: "Whether the tab group is disabled. Default: false."
        type: "BooleanInput"
    methods:
      - name: focus
        params: 
        returnType: void
  - name: NxTabHeaderComponent
    selector: nx-tab-header
    inputs:
      - name: selectedIndex
        type: "number"
      - name: autoselect
        type: "boolean"
    outputs:
      - name: selectFocusedIndex
        type: "EventEmitter<number>"
      - name: indexFocused
        type: "EventEmitter<number>"
    methods:
      - name: scrollToButton
        params:
          - name: index
            type: number
        returnType: void
      - name: handleKeydown
        params:
          - name: event
            type: KeyboardEvent
        desc: "Handles keyboard inputs on the labels If autoselect is enabled the tab gets changed immediately If autoselect is disabled only the focus changes but the user still has to select the item by himself."
        returnType: void
  - name: NxTabBodyComponent
    selector: nx-tab-body
    inputs:
      - name: tab
        type: "NxTabComponent"
      - name: active
        type: "BooleanInput"
    methods:
      - name: attach
        params: 
        returnType: void
      - name: detach
        params: 
        returnType: void
  - name: NxTabNavBarComponent
    selector: nx-tab-nav-bar
    inputs:
      - name: negative
        desc: "Whether the tab nav bar has negative styling."
        type: "BooleanInput"
      - name: disabled
        desc: "Whether the tab nav bar has disabled styling."
        type: "BooleanInput"
      - name: appearance
        desc: "**Expert option**  Sets the appearance of the tab nav bar. Default: 'default'."
        type: "'expert' | 'default'"
  - name: NxTabLinkDirective
    selector: [nxTabLink]
    inputs:
      - name: active
        desc: "Whether the tab link is active and has the active styling."
        type: "BooleanInput"
      - name: disabled
        desc: "Whether the tab link is disabled. Default: false."
        type: "BooleanInput"
  - name: NxTabContentDirective
    selector: [nxTabContent]
    desc: |
      Decorates the `ng-template` tags and reads out the template from it.
  - name: NxTabHeaderOutletComponent
    selector: nx-tab-header-outlet
    inputs:
      - name: content
        type: "EmbeddedViewRef<any>"
    methods:
      - name: attach
        params: 
        returnType: void
      - name: detach
        params: 
        returnType: void
  - name: NxTabScrollIndicator
    selector: nx-tab-scroll-indicator
    inputs:
      - name: scrollDirection
        type: "'start' | 'end'"
      - name: isScrolledToStart
        type: "boolean"
      - name: isScrolledToEnd
        type: "boolean"
    outputs:
      - name: buttonClicked
        type: "EventEmitter<void>"
    methods:
      - name: getChevronName
        params: 
        returnType: string
      - name: scroll
        params: 
        returnType: void

---