--- 
title: Data Display
category: components

module: NxDataDisplayModule
components:
  - name: NxDataDisplayComponent
    selector: nx-data-display
    desc: |
      Data display component.
    inputs:
      - name: label
        desc: "Label describing the data."
        type: "string | null | undefined"
      - name: labelColumns
        desc: "Column span of the label text based on a 12 column system, when in `orientation='horizontal-columns'` layout.  Accepted values: `3, 4, 6, 8, 9`.  Default: `6`."
        type: "NumberInput"
      - name: size
        desc: "Size of the data display.  Default: `'large'`."
        type: "'small' | 'medium' | 'large' | null | undefined"
      - name: orientation
        desc: "Layout orientation of the label and value.  - 'vertical': label and value are vertically stacked. - 'horizontal': label and value are on the same line. - 'horizontal-columns': label and value are on the same line in a fixed position.  Default: `'vertical'`."
        type: "'vertical' | 'horizontal' | 'horizontal-columns' | null | undefined"
  - name: NxDataDisplayLabelComponent
    selector: nx-data-display-label
    desc: |
      Label within a `<nx-data-display>`.

---
# Overview
The data display component resembles a HTML description list element. It consists of a label and a value.
