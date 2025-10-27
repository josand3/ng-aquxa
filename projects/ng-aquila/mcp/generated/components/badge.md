--- 
title: Badge
category: components
alias: chip

module: NxBadgeModule
components:
  - name: NxBadgeComponent
    selector: nx-badge
    inputs:
      - name: type
        desc: "Sets the class name for the badge element."
        type: "'active' | 'positive' | 'critical' | 'negative' | '' | string | null | undefined"
      - name: vibrant
        desc: "Change badge style to vibrant."
        type: "BooleanInput"

---