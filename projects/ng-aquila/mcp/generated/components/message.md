--- 
title: Notifications
category: components
alias: message banner, toast, snackbar, alert, info, error, warning, success

module: NxMessageModule
components:
  - name: NxMessageComponent
    selector: nx-message
    inputs:
      - name: context
        desc: "Sets the context of the message. The message box will color accordingly. Default: 'regular'."
        type: "'regular' | 'info' | 'error' | 'success' | 'warning'"
      - name: closable
        desc: "Whether a message should have a close icon in order to be dismissed."
        type: "BooleanInput"
      - name: closeButtonLabel
        desc: "Sets the label of the close button of the message."
        type: "string"
    outputs:
      - name: closeEvent
        desc: "Event emitted when the close icon of the message has been clicked."
        type: "EventEmitter<void>"
  - name: NxMessageToastComponent
    selector: nx-message-toast
    desc: |
      Internal component that wraps user-provided message toast content.
    methods:
      - name: attachComponentPortal
        params:
          - name: portal
            type: ComponentPortal<T>
        desc: "Attach a component portal as content to this message toast container."
        returnType: ComponentRef<T>
      - name: attachTemplatePortal
        params:
          - name: portal
            type: TemplatePortal<C>
        desc: "Attach a template portal as content to this message toast container."
        returnType: EmbeddedViewRef<C>
      - name: onAnimationEnd
        params:
          - name: event
            type: AnimationEvent
        desc: "Handle end of animations, updating the state of the notification."
        returnType: void
      - name: enter
        params: 
        desc: "Begin animation of message toast entrance into view."
        returnType: void
      - name: exit
        params: 
        desc: "Begin animation of the message toast exiting from view."
        returnType: void
  - name: NxMessageBannerComponent
    selector: nx-message-banner
    inputs:
      - name: context
        desc: "Sets the context of the message banner. The message box will color accordingly.  Default: `'info'`."
        type: "'info' | 'error' | 'warning'"

---