--- 
title: Tree
category: components

module: NxTreeModule
components:
  - name: NxTreeComponent
    selector: nx-tree
    desc: |
      Wrapper for the CdkTree with custom design styles and keyboard nav mechanics.
    inputs:
      - name: tabIndex
        type: "number"
    methods:
      - name: insertToA11yNodeTracking
        params:
          - name: index
            type: number
          - name: data
            type: T
          - name: node
            type: FocusableOption
          - name: parentData
            type: T | undefined
        desc: "Add tree node to data list based on owner of parent view container."
        returnType: void
      - name: removeFromA11yNodeTracking
        params:
          - name: index
            type: number
          - name: parentData
            type: T | undefined
        desc: "Remove a node data from node list based on the owner of view container."
        returnType: void
      - name: moveInA11yNodeTracking
        params:
          - name: previousIndex
            type: number
          - name: currentIndex
            type: number
          - name: parentData
            type: T | undefined
        desc: "Update node's index information based on the owner of view container."
        returnType: void
      - name: updateFocusedData
        params:
          - name: newFocusedData
            type: T
        desc: "When a tree node is focused, update the current focused data."
        returnType: void
      - name: focus
        params: 
        desc: "Focus first node when the tree is focused"
        returnType: void
      - name: focusFirstVisibleNode
        params: 
        desc: "Change focus to first visible node in the tree."
        returnType: void
      - name: focusLastVisibleNode
        params: 
        desc: "Change focus to last visible node in the tree."
        returnType: void
      - name: focusPreviousVisibleNode
        params: 
        desc: "Change focus to previous visible node."
        returnType: void
      - name: focusNextVisibleNode
        params: 
        desc: "Change focus to next visible node."
        returnType: void
      - name: collapseCurrentFocusedNode
        params: 
        desc: "Collapse the current node if it's expanded. Otherwise move to parent."
        returnType: void
      - name: expandCurrentFocusedNode
        params: 
        desc: "Expand the current node if it's not expanded. Otherwise move to its first child."
        returnType: void
      - name: expandAllNodes
        params: 
        desc: "Expand all the nodes in the tree"
        returnType: void
      - name: toggleCurrentFocusedNode
        params: 
        desc: "Expand the current node if it's not expanded. Otherwise move to its first child."
        returnType: void
      - name: insertNode
        params:
          - name: nodeData
            type: T
          - name: index
            type: number
          - name: viewContainer
            type: ViewContainerRef | undefined
          - name: parentData
            type: T | undefined
        desc: "Extended CdkTree method to track new nodes for a11y."
        returnType: void
      - name: renderNodeChanges
        params:
          - name: data
            type: T[]
          - name: dataDiffer
            type: IterableDiffer<T>
          - name: viewContainer
            type: ViewContainerRef
          - name: parentData
            type: T | undefined
        desc: "⚠️  Here we override the method from cdk tree ⚠️ Adds some extra method calls to update the a11y node tracking."
        returnType: void
  - name: NxTreeNodeComponent
    selector: nx-tree-node
    desc: |
      Wrapper for the CdkTree node with custom design styles.
    methods:
      - name: focus
        params: 
        returnType: void
  - name: NxTreeNodeDefDirective
    selector: [nxTreeNodeDef]
    desc: |
      Wrapper for the CdkTree node definition with custom design styles.
    inputs:
      - name: nxTreeNode
        type: "T"
  - name: NxTreeNodePaddingDirective
    selector: [nxTreeNodePadding]
    desc: |
      Indent for the children tree dataNodes.
      This directive will add left-padding to the node to show hierarchy.
    inputs:
      - name: nxTreeNodePadding
        desc: "The level of depth of the tree node. The padding will be `level * indent` pixels."
        type: "NumberInput"
      - name: nxTreeNodePaddingOffset
        desc: "The offset is added once on top of each indent. Default number is 0."
        type: "NumberInput"
      - name: nxTreeNodePaddingIndent
        desc: "The indent for each level. Can be a number or a CSS string. Default number 24px from material design menu sub-menu spec."
        type: "NumberInput"
  - name: NxTreeNodeToggleDirective
    selector: [nxTreeNodeToggle]
    desc: |
      Wrapper for the CdkTree's toggle with custom design styles.
  - name: NxTreeNodeOutletDirective
    selector: [nxTreeNodeOutlet]
    desc: |
      Outlet for nested CdkNode. Put `[nxTreeNodeOutlet]` on a tag to place children dataNodes
      inside the outlet.
  - name: NxTreeNodeActionItem
    selector: [nxTreeNodeActionItem]
    desc: |
      Handles focussing of the tree action item and adds the necessary attributes for a11y
    methods:
      - name: focus
        params: 
        returnType: void

---
# Overview
The nx-tree provides a tree that can be used to display hierarchy data. This component is designed to work in conjunction with the [sidebar](./documentation/sidebar/overview). It is heavily inspired my the Angular Material Flat Tree. For an in depth documentation see [material.angular.io](https://material.angular.io/components/tree/overview).

A `<nx-tree>` is a flat tree consisting of `<nx-tree-node>` nodes.

<!-- example(tree) -->
