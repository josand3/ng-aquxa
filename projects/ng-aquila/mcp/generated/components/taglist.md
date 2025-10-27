--- 
title: Tag
category: components
alias: chip

module: NxTaglistModule
components:
  - name: NxTaglistComponent
    selector: nx-taglist
    inputs:
      - name: tags
        desc: "Sets the list of tags."
        type: "any[]"
      - name: tabindex
        desc: "Sets the tabindex of the contained tags. Default value: -1."
        type: "NumberInput"
      - name: allowTagDeletion
        desc: "Whether the tags can be removed from the list. Default: true."
        type: "BooleanInput"
      - name: isKeywordList
        desc: "Whether the tags can be styled as keywords."
        type: "BooleanInput"
      - name: labelProperty
        desc: "Sets the label property, in case tags represent objects."
        type: "string"
      - name: aria-labelledby
        desc: "Sets the label property to improve accessibility."
        type: "string"
      - name: valueFormatter
        desc: "Sets the customization function for tag value."
        type: "(value: any) => string"
    outputs:
      - name: tagsChange
        desc: "An event is dispatched each time when the list of tags changed."
        type: "EventEmitter<any[]>"
      - name: tagClickEvent
        desc: "An event is dispatched each time when a tag is clicked."
        type: "EventEmitter<any>"
    methods:
      - name: delete
        params:
          - name: index
            type: number
          - name: value
            type: any
        desc: "Allows to delete a tag given index. Takes index of the tag to be deleted as a parameter"
        returnType: void
      - name: addTag
        params:
          - name: tag
            type: any
        desc: "Allows to add a tag. Takes tag object as an input"
        returnType: void
      - name: clearTags
        params: 
        desc: "Allows to clear the tag list."
        returnType: void
      - name: renderTag
        params:
          - name: tag
            type: any
        returnType: string
      - name: tagClick
        params:
          - name: index
            type: number
          - name: value
            type: any
        returnType: void
  - name: NxTagComponent
    selector: nx-tag
    inputs:
      - name: removableInput
        desc: "Whether the tag should be readonly."
        default: input(false, { alias: 'removable', transform: booleanAttribute })
        type: "InputSignalWithTransform<boolean, unknown>"
      - name: tabindex
        desc: "@deprecated Keyboard accessibility support will come from different solutions.    *    * Sets the tab-index of a tag. Default value: -1."
        default: input(-1, { transform: numberAttribute })
        type: "InputSignalWithTransform<number, unknown>"
      - name: value
        desc: "Sets the value of the tag. This value will be used in the tag group model. If no content projection is used this will be used as the visual label."
        default: input<any>('')
        type: "InputSignal<any>"
      - name: typeInput
        desc: "Sets the appearance of the tag."
        default: input<NxTagType>('tag', { alias: 'type' })
        type: "InputSignal<'tag' | 'keyword'>"
      - name: deleteAriaLabel
        desc: "Set an aria-label on the remove button explicitly and not from the NxTagIntl class."
        default: input('')
        type: "InputSignal<string>"
      - name: disabledInput
        desc: "Whether the tag should be disabled."
        default: input(false, { transform: booleanAttribute, alias: 'disabled' })
        type: "InputSignalWithTransform<boolean, unknown>"
    outputs:
      - name: clicked
        desc: "An event is dispatched each time when the tag is clicked.@deprecated Tags should not be clickable with the supported patterns. Needs to be kept for now for backwards compatibility with the deprecated taglist."
        type: "EventEmitter<any>"
      - name: removed
        desc: "An event dispatched when the tag should be deleted."
        type: "EventEmitter<any>"
    methods:
      - name: setReadonly
        params:
          - name: value
            type: boolean
        returnType: void
      - name: removeHandler
        params:
          - name: event
            type: MouseEvent
        returnType: void
      - name: emitLegacyClicked
        params:
          - name: event
            type: Event
        returnType: void
      - name: handleInputClick
        params:
          - name: event
            type: Event
        returnType: void
      - name: toggleSelected
        params: 
        returnType: void
  - name: NxTagGroupComponent
    selector: nx-tag-group
    inputs:
      - name: disabledInput
        desc: "Whether the tags should be disabled."
        default: input(false, { transform: booleanAttribute, alias: 'disabled' })
        type: "InputSignalWithTransform<boolean, unknown>"
      - name: removable
        desc: "Whether the tags should be removable."
        default: input(false, { transform: booleanAttribute })
        type: "InputSignalWithTransform<boolean, unknown>"
      - name: type
        desc: "Switches the appearance of the tags."
        default: input<NxTagType>('tag')
        type: "InputSignal<'tag' | 'keyword'>"
    methods:
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
      - name: setReadonly
        params:
          - name: value
            type: boolean
        returnType: void
      - name: addValue
        params:
          - name: value
            type: any
        returnType: void
      - name: removeValue
        params:
          - name: value
            type: any
        returnType: void
      - name: onBlur
        params:
          - name: event
            type: FocusEvent
        returnType: void

---
# Overview
Tags are an interactive element that are used for selection e.g. for filters of data or show a list of removable tags. Tags are not meant to be used as purely informational, non-interactive element. For this use case, please use the badge component.
