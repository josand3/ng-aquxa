--- 
title: Progress Bar
category: components

module: NxProgressbarModule
components:
  - name: NxProgressbarComponent
    selector: nx-progressbar
    inputs:
      - name: ariaLabel
        desc: "Overrides the `aria-label` of the nx-progressbar. Defaults to 'Progress'"
        default: 'Progress'
        type: "string | undefined"
      - name: ariaLabelledBy
        desc: "Sets the `aria-labelledby` of the nx-progressbar"
        type: "string | undefined"
      - name: value
        desc: "Sets the value of the progress bar. Defaults to zero. Mirrored to aria-valuenow."
        default: 0
        type: "number"
      - name: min
        desc: "The minimum value of the progress bar. Used for percentage calculation and mirrored to `aria-valuemin`. Defaults to 0"
        default: 0
        type: "number"
      - name: max
        desc: "The maximum value of the progress bar. Used for percentage calculation and mirrored to `aria-valuemax`. Defaults to 1"
        default: 1
        type: "number"

---
# Overview
The progress bar module provides a simple horizontal bar to show progress.
