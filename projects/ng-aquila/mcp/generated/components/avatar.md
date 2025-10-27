--- 
title: Avatar
category: components

module: NxAvatarModule
components:
  - name: NxAvatarComponent
    selector: [nxAvatar]
    inputs:
      - name: accentColor
        default: input<NxAvatarAccent>('default')
        type: "InputSignal<| 'yellow'  | 'orange'  | 'red'  | 'purple'  | 'teal'  | 'aqua'  | 'blue'  | 'green'  | 'gray'  | 'default'>"
      - name: attention
        default: input<boolean>(false)
        type: "InputSignal<boolean>"
      - name: size
        desc: "Sets the size of the avatar. Default: 'medium'."
        type: "'xsmall' | 'small' | 'small-medium' | 'medium' | 'large' | 'xlarge'"
  - name: NxAvatarButtonDirective
    selector: button[nxAvatar]

---
# Overview
Depending on the use case the avatar can be used as a non-clickable element or as a button.
