--- 
title: Pagination
category: components
alias: pager, paginator

module: NxPaginationModule
components:
  - name: NxPaginationComponent
    selector: nx-pagination
    inputs:
      - name: ariaLabel
        desc: "Sets the aria label on the nav element of the pagination. Use this to override the global aria-label from PaginationTexts."
        type: "string"
      - name: page
        desc: "Sets the current page."
        type: "number"
      - name: count
        desc: "Number of total items over all pages."
        type: "number"
      - name: perPage
        desc: "Sets the number of items you want to show per page."
        type: "number"
      - name: type
        desc: "Determines the type of pagination.  Values: simple | advanced | slider, default: simple."
        type: "string"
    outputs:
      - name: goPrev
        desc: "An event emitted when the previous page button is clicked."
        type: "EventEmitter<void>"
      - name: goNext
        desc: "An event emitted when the next page button is clicked"
        type: "EventEmitter<void>"
      - name: goPage
        desc: "An event emitted when a page number is clicked. Provides the number of the page as parameter."
        type: "EventEmitter<number>"
    methods:
      - name: getMin
        params: 
        desc: "Returns the number of the first page."
        returnType: number
      - name: getMax
        params: 
        desc: "Returns the number of the last page."
        returnType: number
      - name: calculateTotalPages
        params: 
        desc: "Returns the total number of pages"
        returnType: number
      - name: onPage
        params:
          - name: n
            type: number
        desc: "Directs to the page with number n."
        returnType: void
      - name: onPrev
        params: 
        desc: "Directs to the previous page."
        returnType: void
      - name: onNext
        params: 
        desc: "Directs to the next page."
        returnType: void
      - name: onFirst
        params: 
        desc: "Directs to the first page."
        returnType: void
      - name: onLast
        params: 
        desc: "Directs to the last page."
        returnType: void
      - name: lastPage
        params: 
        desc: "Returns if the current page is the last page."
        returnType: boolean
      - name: getSlides
        params: 
        returnType: Page[]
      - name: getPages
        params: 
        returnType: Page[]
      - name: getMobilePages
        params: 
        returnType: Page[]
      - name: getPaginationItemClasses
        params:
          - name: page
            type: Page
        returnType: object
      - name: getPaginationNumberClasses
        params:
          - name: page
            type: Page
        returnType: object
      - name: isPaginationVisible
        params: 
        desc: "Returns true, if `nxCount` is greater than 0, else false."
        returnType: boolean
      - name: isPaginationCompactVisible
        params: 
        desc: "Returns true, if `nxCount` is greater than 0 and the type of pagination is 'simple', else false."
        returnType: boolean
      - name: isPaginationSliderVisible
        params: 
        desc: "Returns true, if `nxCount` is greater than 0 and the type of pagination is 'slider', else false."
        returnType: boolean
      - name: isPaginationContainerVisible
        params: 
        returnType: boolean

---
# Overview
Pagination is used for splitting up content or data into several pages, with controls for navigating to the next or previous page. You can choose between two options:

-   Advanced pagination where parts are referred to by numbers and arrows.
-   Simple pagination where parts are referred with “previous” and “next” buttons.
