--- 
title: Breadcrumb
category: components
alias: location

module: NxBreadcrumbModule
components:
  - name: NxBreadcrumbItemComponent
    selector: [nxBreadcrumbItem]
    methods:
      - name: setAsLast
        params: 
        returnType: void
      - name: resetAriaLabel
        params: 
        returnType: void
  - name: NxBreadcrumbComponent
    selector: ol[nxBreadcrumb]
    inputs:
      - name: appearance
        desc: "Sets the appearance of the breadcrumb.  Default: `'default'`."
        type: "'default' | 'link'"
      - name: negative
        desc: "Whether the component uses the negative styling."
        type: "BooleanInput"

---
# Overview
A breadcrumb component is used to show the current page location to the user and serves as a navigation hint. It consists of a list of links to the parent pages of the current page in hierarchical order. Our breadcrumb component does not contain any routing logic and just displays the breadcrumb items it gets as input. **The breadcrumb items should be updated on routing changes by the application in which the breadcrumb is used.**

The last element of the breadcrumbs should not be interactive. To achieve that you can either set `[routerLink]="null"` or `[attr.href]="null"` on the last breadcrumb item to make the link non-interactive.
