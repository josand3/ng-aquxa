--- 
title: Header
category: components
alias: toolbar, navbar

module: NxHeaderModule
components:
  - name: NxHeaderComponent
    selector: nx-header, [nx-header]
    desc: |
      The `<nx-header>` component is the main application header.
  - name: NxHeaderLinkComponent
    selector: a[nxHeaderLink]
    desc: |
      This component defines a header link within the `<nx-header>` component.
  - name: NxHeaderActionsDirective
    selector: nx-header-actions
    desc: |
      This directive defines the header actions section within the `<nx-header>` component.
    inputs:
      - name: showSeparator
        type: "BooleanInput"
  - name: NxHeaderNavigationComponent
    selector: nx-header-navigation
    desc: |
      This component defines the header navigation section within the `<nx-header>` component.
  - name: NxHeaderBrandDirective
    selector: nx-header-brand
    desc: |
      This directive defines the header brand section within the `<nx-header>` component.
  - name: NxHeaderRowDirective
    selector: nx-header-row
    desc: |
      This directive defines a header row within the `<nx-header>` component.
  - name: NxHeaderNavigationItemDirective
    selector: nx-header-navigation-item
    desc: |
      This directive defines a header navigation item within the `<nx-header-navigation>`.
  - name: NxHeaderAppTitleDirective
    selector: nx-header-app-title
    desc: |
      This directive defines the application title within the `<nx-header>` component.

---
# Overview
The header is placed at the top of your application and can have one or two rows. It usually contains a brand logo, navigation links and other actions like a user profile.

The header provides a layout consisting of three sections, `<nx-header-brand>`, `<nx-header-navigation>` and `<nx-header-actions>`. The `<nx-header-brand>` is the first section from the left and contains the applications/brands logo.

Next there is a `<nx-header-navigation>` section that can contain navigation links. The styling of the individual navigation links is provided by the `nxHeaderLink` directive.

The last section is the `<nx-header-actions>` which can contain any other actions like a user profile popover.
