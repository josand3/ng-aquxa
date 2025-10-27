--- 
title: Notification panel
category: components
alias: popover

module: NxNotificationPanelModule
components:
  - name: NxNotificationPanelComponent
    selector: nx-notification-panel
  - name: NxNotificationPanelItemComponent
    selector: nx-notification-panel-item, [nxNotificationPanelItem]
    inputs:
      - name: read
        type: "BooleanInput"
      - name: clickable
        type: "BooleanInput"
    methods:
      - name: focus
        params:
          - name: focusOrigin
            type: FocusOrigin | undefined
        returnType: void
  - name: NxNotificationPanelTriggerDirective
    selector: [nxNotificationPanelTriggerFor]
    inputs:
      - name: nxNotificationPanelTriggerFor
        type: "TemplateRef<any>"
    methods:
      - name: open
        params: 
        returnType: void
      - name: close
        params: 
        returnType: void
  - name: NxNotificationItemActionsDirective
    selector: nx-notification-item-actions
  - name: NxNotificationItemContentDirective
    selector: nx-notification-item-content
  - name: NxNotificationItemMetadataDirective
    selector: nx-notification-item-metadata
  - name: NxNotificationItemHeaderDirective
    selector: nx-notification-header

---
# Overview
The notification panel is supposed to be used in the header to give users quick access to recent messages and notifications. It consists of a trigger button that opens the notification flyout.
