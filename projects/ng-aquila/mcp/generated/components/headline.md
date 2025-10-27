--- 
title: Headline
category: components
alias: heading, title

module: NxHeadlineModule
components:
  - name: NxHeadlineComponent
    selector: [nxHeadline]
    inputs:
      - name: size
        type: "| 's'  | 'm'  | 'l'  | 'xl'  | '2xl'  | '3xl'  | '4xl'  | '5xl'  | '6xl'  | undefined"
      - name: type
        default: input<NxHeadlineType>('primary')
        type: "InputSignal<'primary' | 'secondary'>"
      - name: nxHeadline
        desc: "Changes the type of the headline which affects the visual appearance.  You can combine a HeadlineType and 'negative'."
        type: "string"
      - name: negative
        type: "BooleanInput"

---
# Overview
Headlines are decoupled from the actual markup. You can pick any tag from h1 - h6 to fulfill the expected semantics and adjust the appearance with the following attributes.
