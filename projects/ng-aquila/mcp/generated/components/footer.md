--- 
title: Footer
category: components

module: NxFooterModule
components:
  - name: NxFooterComponent
    selector: nx-footer, [nx-footer]
    inputs:
      - name: copyright
        type: "string | null | undefined"
  - name: NxFooterCopyrightDirective
    selector: nx-footer-copyright
  - name: NxFooterLinkDirective
    selector: nx-footer-link
  - name: NxFooterNavigationDirective
    selector: nx-footer-navigation

---
# Overview
This component provides a basic skeleton of the footer including two parts. On one hand there is the `nx-footer-copyright` section, which applies a basic styling to this block. On the other hand there is the `nx-footer-navigation` directive in order to give this element the `list` role. In there, you have the option to place all your footer links. They have to be placed inside of the `nx-footer-link` selector in order to get the `listitem` role and the corresponding styling and behaviour.
