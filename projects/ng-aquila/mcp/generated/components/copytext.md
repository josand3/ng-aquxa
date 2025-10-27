--- 
title: Copytext
category: components

module: NxCopytextModule
components:
  - name: NxCopytextComponent
    selector: [nxCopytext]
    inputs:
      - name: nxCopytext
        desc: "Sets the type and whether the negative set of styling should be used.  You can combine the values of type NxCopytextType and 'negative'.  Default: `'normal'`."
        type: "string"

---
# Overview
Copytext is implemented as a component which can be used optionally. Instead of applying the full set of BEM classes like `c-copy c-copy--medium` to a paragraph, you can use this component by directly passing the size property.
