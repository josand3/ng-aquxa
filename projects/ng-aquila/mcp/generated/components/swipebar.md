--- 
title: Swipebar
category: components
alias: scrollbar

module: NxSwipebarModule
components:
  - name: NxSwipebarComponent
    selector: nx-swipebar
    inputs:
      - name: label
        desc: "The label for this swipebar.  Default: `''`."
        default: ''
        type: "string"

---
# Overview
The swipebar component is a visual indicator for an area that has horizontal overflow. This is especially helpful to interact with large content like tables on mobile devices. See table component for more examples.

Use with care as this is not a replacement for propper responsive layout but to handle edge cases!
