--- 
title: Spinner
category: components
alias: progress spinner

module: NxSpinnerModule
components:
  - name: NxSpinnerComponent
    selector: nx-spinner
    inputs:
      - name: ariaPoliteness
        desc: "Sets the aria live regions of the spinner. Default is 'assertive'."
        default: ARIA_POLITENESS_ASSERTIVE
        type: "'polite' | 'assertive' | 'off'"
      - name: size
        desc: "Sets the size of the spinner. Default is 'small'."
        type: "'small' | 'medium' | 'large'"
      - name: negative
        desc: "Whether the spinner should use a negative styling."
        type: "BooleanInput"
      - name: activationAnnouncement
        desc: "Message that will be announced by screen readers at instantiation. Do __not__ combine with an `aria-live` area. Empty messages will be ignored. Defaults to empty/no message"
        type: "string"
      - name: completionAnnouncement
        desc: "Message that will be announced by screen readers at destroy. Do __not__ combine with an `aria-live` area. Empty messages will be ignored. Defaults to empty/no message"
        type: "string"

---