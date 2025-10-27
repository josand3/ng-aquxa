--- 
title: Formfield
category: components
alias: control

module: NxFormfieldModule
components:
  - name: NxFormfieldComponent
    selector: nx-formfield
    inputs:
      - name: label
        desc: "Sets the label which will act as a floating label. In addition, the component uses input and label to properly support accessibility."
        type: "string | null | undefined"
      - name: optionalLabel
        desc: "Set optional text, which will addtional show in label if a field is not mandatory."
        default: this._defaultOptions?.nxOptionalLabel
        type: "string | undefined"
      - name: floatLabel
        desc: "Whether the label should float once the input is focused or filled (auto, default) or force it to always float with a value of always to simulate a more static form."
        type: "'always' | 'auto'"
      - name: negative
        desc: "Sets the styling of the formfield. If 'negative', a negative set of stylings is used."
        type: "string"
      - name: appearance
        desc: "**Expert option**  Sets the appearance of the formfield."
        type: "'outline' | 'auto'"
      - name: updateOn
        desc: "Sets the event that triggers change detection in the formfield."
        type: "'change' | 'blur'"
    methods:
      - name: getDisplayedMessage
        params: 
        returnType: "" | "error" | "note"
      - name: getConnectedOverlayOrigin
        params: 
        desc: "Returns an element that overlays can attach to."
        returnType: ElementRef<any>
  - name: NxFormfieldHintDirective
    selector: [nxFormfieldHint]
  - name: NxFormfieldErrorDirective
    selector: [nxFormfieldError], [nxError]
  - name: NxFormfieldNoteDirective
    selector: [nxFormfieldNote]
  - name: NxFormfieldPrefixDirective
    selector: [nxFormfieldPrefix]
  - name: NxFormfieldSuffixDirective
    selector: [nxFormfieldSuffix]
  - name: NxFormfieldAppendixDirective
    selector: [nxFormfieldAppendix]
  - name: NxFormfieldLabelDirective
    selector: nx-formfield-label
    desc: |
      A directive for passing more complex custom label content.

---
# Overview
In most cases it is sufficient to only import the nxInputModule - this **already includes the NxFormfieldModule module**.

```ts
import { NxInputModule } from '@allianz/ng-aquila/input';
```

Alternatively you could import NxFormfieldModule, but in this case you are required to also add an [nxInput](./documentation/input/overview) control to the html template, like in the Basic Example below.

```ts
import { NxFormfieldModule } from '@allianz/ng-aquila/formfield';
```

The formfield component is only usable in combination with a compatible input like nxInput. You will get floating labels, hints and a space to properly render additional information and errors below the input.

You can't use the formfield without a matching input. A matching input fulfills the requirements of the `NxFormfieldControl` interface.

**Changes to formfield paddings:** Starting v16, bottom padding is now applied to both Error and Hint messages. The new bottom padding for Expert is 16px, Retail (Desktop) 32px and Retail (Mobile) 24px. If you would like to keep the old padding values, include `@allianz/ng-aquila/css/compatibility/formfield-padding.css` in your `angular.json`.
