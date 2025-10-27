--- 
title: Small stage
category: components
alias: page banner

module: NxSmallStageModule
components:
  - name: NxSmallStageImageDirective
    selector: nx-small-stage-image
    desc: |
      This is an image that can be placed into the small stage component.
    inputs:
      - name: src
        desc: "The source url of the image."
        type: "string"
  - name: NxSmallStageImageStartDirective
    selector: [nxSmallStageImageStart]
    desc: |
      A directive for passing the start image into small stage component.
  - name: NxSmallStageImageEndDirective
    selector: [nxSmallStageImageEnd]
    desc: |
      A directive for passing the end image into small stage component.
  - name: NxSmallStageHeaderDirective
    selector: [nxSmallStageHeader]
    desc: |
      A directive for passing contents to small stage header.
  - name: NxSmallStageComponent
    selector: nx-small-stage
    inputs:
      - name: appearance
        desc: "**Expert option**  Sets the appearance of the small stage.  Default: `'default'`."
        type: "'default' | 'expert'"
      - name: narrow
        desc: "Reduces the width of the text to 6/12 instead of 8/12.  **Only works with appearance = 'expert'.**."
        type: "BooleanInput"
  - name: NxSmallStageImageBottomDirective
    selector: [nxSmallStageImageBottom]
    desc: |
      A directive for passing the bottom image into small stage component.

---