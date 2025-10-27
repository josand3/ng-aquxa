--- 
title: Overlay
category: components

module: NxOverlayModule
components:
  - name: NxOverlayContainerComponent
    selector: nx-overlay-container
    desc: |
      Internal component that wraps user-provided overlay content.
    methods:
      - name: attachComponentPortal
        params:
          - name: portal
            type: ComponentPortal<T>
        desc: "Attach a ComponentPortal as content to this overlay container."
        returnType: ComponentRef<T>
      - name: attachTemplatePortal
        params:
          - name: portal
            type: TemplatePortal<C>
        desc: "Attach a TemplatePortal as content to this overlay container."
        returnType: EmbeddedViewRef<C>
      - name: restoreFocus
        params: 
        desc: "Restores focus to the element that was focused before the overlay opened."
        returnType: void

---