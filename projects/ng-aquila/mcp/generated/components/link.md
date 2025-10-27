--- 
title: Link
category: components

module: NxLinkModule
components:
  - name: NxLinkComponent
    selector: nx-link
    desc: |
      `Input('nxStyle') classNames` sets the style of the link, thereby altering the visual appearance.
      You can use any combination of 'black', 'icon-right', 'icon-only', 'negative' or 'text'.
    inputs:
      - name: size
        desc: "Sets the size of the link. Default: 'small'."
        default: input<NxLinkSize>('small')
        type: "InputSignal<'xsmall' | 'small' | 'large'>"
      - name: type
        desc: "Sets the type of the link. Default: 'primary'."
        default: input<NxLinkType>('primary')
        type: "InputSignal<'primary' | 'secondary'>"
      - name: prominence
        desc: "Sets the prominence of the link. Default: 'default'."
        default: input<NxLinkProminence>('default')
        type: "InputSignal<'default' | 'subtle'>"

---
# Overview
The nxLink provides a styled link without interfering with the functionality of the Angular router. Embed a link to lead the user towards more information or an action he/she wants to execute.

Note that

-   the `nx-link` component wraps an `<a></a>` element in combination with e.g. an href-attribute or a routerLink directive.
-   disabled links should have the attribute `aria-disabled="true"` and will be styled accordingly.
-   disabled links should either omit the href attribute or add `tabindex="-1"`. If you use `routerLink` you can pass `null` and the href attribute will not be rendered.

Depending on the context, pick one of the following types - or a reasonable combination thereof.
