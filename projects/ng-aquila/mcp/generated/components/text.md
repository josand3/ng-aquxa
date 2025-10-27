--- 
title: Text
category: components

module: NxTextModule
components:
  - name: NxAttentionColorComponent
    selector: [nx-attention-color]
    desc: |
      Applies an attention color to inline text fragments.
      
      A1 only: not mapped / styled for NDBX brand. In NDBX it's mapped to opensource color.
    inputs:
      - name: color
        desc: "Required attention color. No implicit default: consumer must provide a valid color."
        default: input.required<NxAttentionColorOption>({ alias: 'nx-attention-color' })
        type: "InputSignal<'yellow' | 'orange' | 'red' | 'purple' | 'teal' | 'aqua' | 'blue' | 'green' | 'gray'>"
      - name: negative
        desc: "Whether to use the negative to invert color"
        default: input(false, { transform: booleanAttribute })
        type: "InputSignalWithTransform<boolean, unknown>"

---