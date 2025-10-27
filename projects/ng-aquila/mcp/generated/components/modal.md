--- 
title: Modal
category: components
alias: dialog

desc: |
    this require adding cdk style to angular.json

    "styles": [
    ...,
    "node_modules/@angular/cdk/overlay-prebuilt.css"
    ]

module: NxModalModule
components:
  - name: NxModalComponent
    selector: nx-modal
    inputs:
      - name: modalBody
        desc: "A template reference variable pointing to the template which contains the content of the modal view."
        type: "TemplateRef<any>"
      - name: hideOnEsc
        desc: "Whether the modal view should close when the user hits the escape key. Default: `true`."
        default: true
        type: "boolean"
      - name: hideOnClickOutside
        desc: "Whether the modal view should close when the user clicks on the backdrop. Default: `true`."
        default: true
        type: "boolean"
      - name: showCloseIcon
        desc: "Whether the modal view should have a close icon in the upper right corner. Default: `true`."
        default: true
        type: "boolean"
      - name: windowSize
        desc: "Controls the width of the dialog. On `auto` the width is controlled by the content width, on `fixed` the dialog gets a fixed width of 736px if the viewport is big enough."
        default: 'auto'
        type: "'auto' | 'fixed'"
      - name: closeButtonLabel
        desc: "Sets the 'aria-label' of the modal close button needed for accessibility.  Default: `'Close dialog'`."
        type: "string"
    outputs:
      - name: closeEvent
        desc: "An event emitted when the user clicks on the backdrop or uses the built-in close button. This event can be applied in conjunction with the custom open state handling of a modal to close it when requested by the user."
        type: "EventEmitter<void>"
    methods:
      - name: clickOutsideModal
        params: 
        returnType: void
      - name: closeButtonClick
        params: 
        returnType: void
      - name: cancelClick
        params:
          - name: evt
            type: MouseEvent
        returnType: void
  - name: NxOpenModalOnClickDirective
    selector: [nxOpenModalOnClick]
    inputs:
      - name: nxOpenModalOnClick
        desc: "One or multiple template reference variables pointing to elements which should trigger opening the modal on click.  Value: A single template reference variable or an array of template reference variables."
        type: "NxButtonBase | NxButtonBase[]"
  - name: NxModalActionsDirective
    selector: [nxModalActions]
    desc: |
      Container for the action buttons in a modal. Has a fixed position at the bottom of the modal on scroll.
  - name: NxModalContentDirective
    selector: [nxModalContent]
    desc: |
      Scrollable container for the content of a modal.
  - name: NxModalContainer
    selector: nx-modal-container
    desc: |
      Internal component that wraps user-provided modal content.
      Animation is based on https://material.io/guidelines/motion/choreography.html.
    methods:
      - name: attachComponentPortal
        params:
          - name: portal
            type: ComponentPortal<T>
        desc: "Attach a ComponentPortal as content to this modal container."
        returnType: ComponentRef<T>
      - name: attachTemplatePortal
        params:
          - name: portal
            type: TemplatePortal<C>
        desc: "Attach a TemplatePortal as content to this modal container."
        returnType: EmbeddedViewRef<C>
  - name: NxModalCloseDirective
    selector: [nxModalClose]
    desc: |
      Button that will close the current modal.
    inputs:
      - name: aria-label
        desc: "Screenreader label for the button."
        type: "string"
      - name: type
        desc: "Defaults to `'button'` to prevents accidental form submits."
        default: 'button'
        type: "'button' | 'submit' | 'reset'"
      - name: nxModalClose
        desc: "Dialog close input."
        type: "any"
  - name: NxModalTitleComponent
    selector: [nxModalTitle]
    desc: |
      Title of a modal.
    inputs:
      - name: status
        desc: "Show icon based on status type.  Default: `undefined`."
        type: "any"

---
# Overview
The `NxDialogService` can be used to open modals from components or predefined templates.

The class `nx-modal-margin-bottom` can be used to get the correct vertical spacing for the elements withing the modal.

**Important:** Please note that the module for this component depends on the Angular animations module, so in case you do not already have it, you need to explicitly import the `BrowserModule` and `BrowserAnimationsModule` in your app.module.

The visual representation of modal overlay depends on Angular CDK styles. Make sure you [enable Angular CDK styles](./documentation/overlay/overview#angular-cdk) in your application.
