--- 
title: Date Field
category: components
alias: datepicker, calendar
desc: |
    This component requires a date adapter module. Choose one:

    | Module               | Date Type                   | Locale Support                          | Dependency | Import From                             |
    | -------------------- | --------------------------- | --------------------------------------- | ---------- | --------------------------------------- |
    | `NxNativeDateModule` | `Date`                      | `en-US` only                            | None       | `@aposin/ng-aquila/datefield`           |
    | `NxMomentDateModule` | `Moment`                    | [Moment locales](https://momentjs.com/) | Moment.js  | `@aposin/ng-aquila/moment-date-adapter` |
    | `NxIsoDateModule`    | ISO `string` (`YYYY-MM-DD`) | [dayjs locales](https://day.js.org/)    | dayjs      | `@aposin/ng-aquila/iso-date-adapter`    |

module: NxDatefieldModule
components:
  - name: NxDatefieldDirective
    selector: input[nxDatefield]
    desc: |
      Directive used to provide date processing functionality to an input.
    inputs:
      - name: hasPopup
        default: input(false)
        type: "InputSignal<boolean>"
      - name: datepicker
        desc: "The datepicker that this input is associated with."
        type: "NxDatepickerComponent<D>"
      - name: datefieldFilter
        desc: "Function that can be used to filter out dates within the datepicker and invalidate values in the datefield."
        type: "(date: D | null) => boolean"
      - name: dateFilter
        type: "(date: D | null) => boolean"
      - name: value
        desc: "Provide or read the current date. It's type <D> depends on the chosen date implementation"
        type: "D | null"
      - name: min
        desc: "Sets the minimum valid date."
        type: "D | null"
      - name: max
        desc: "Sets the maximum valid date."
        type: "D | null"
      - name: strict
        desc: "If supported by the date implementation enable strict parsing (applies to Moment's parse function here).  The date value is not updated on a `strict` change."
        type: "any"
      - name: parseFormat
        desc: "Override the parse format given with parse.dateInput with the token NX_DATE_FORMATS.  The date value is not updated on a `parseFormat` change."
        type: "string | string[]"
      - name: displayFormat
        desc: "Override the display format given with display.dateInput with the token NX_DATE_FORMATS"
        type: "string"
      - name: disabled
        desc: "Whether the datepicker-input is disabled."
        type: "BooleanInput"
    outputs:
      - name: dateChange
        desc: "Emits when a `change` event is fired on this `<input>`."
        type: "EventEmitter<NxDatepickerInputEvent<D>>"
      - name: dateInput
        desc: "Emits when an `input` event is fired on this `<input>`."
        type: "EventEmitter<NxDatepickerInputEvent<D>>"
    methods:
      - name: setReadonly
        params:
          - name: value
            type: boolean
        desc: "Whether the datefield is readonly."
        returnType: void
      - name: validate
        params:
          - name: c
            type: AbstractControl<any, any, any>
        returnType: ValidationErrors | null
      - name: getConnectedOverlayOrigin
        params: 
        desc: "Gets the element that the datepicker popup should be connected to."
        returnType: ElementRef<any>
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
      - name: getValidators
        params: 
        desc: "Returns the validators of the datefield."
        returnType: ValidatorFn[]
  - name: NxDatepickerComponent
    selector: nx-datepicker
    desc: |
      Component responsible for managing the datepicker popup/dialog.
    inputs:
      - name: startView
        desc: "The view that the calendar should start in."
        default: 'month'
        type: "'month' | 'year' | 'multi-year'"
      - name: showTodayButton
        desc: "Determines whether the today button is displayed in the calendar."
        default: false
        type: "boolean"
      - name: panelClass
        desc: "Classes to be passed to the date picker panel. Supports the same syntax as `ngClass`."
        type: "string | string[]"
      - name: rangeMode
        default: input<boolean>(false)
        type: "InputSignal<boolean>"
      - name: startAt
        desc: "The date to open the calendar initially."
        type: "D | null"
      - name: opened
        desc: "Whether the calendar is open."
        type: "boolean"
    outputs:
      - name: yearSelected
        desc: "Emits selected year in multiyear view. This doesn't imply a change on the selected date."
        type: "EventEmitter<D | DateRange<D>>"
      - name: monthSelected
        desc: "Emits selected month in year view. This doesn't imply a change on the selected date."
        type: "EventEmitter<D | DateRange<D>>"
      - name: openedStream
        desc: "Emits when the datepicker has been opened."
        type: "EventEmitter<void>"
      - name: closedStream
        desc: "Emits when the datepicker has been closed."
        type: "EventEmitter<void>"
      - name: todayButtonClick
        desc: "Emits when the Today button is clicked. This doesn't imply a change on the selected date."
        type: "EventEmitter<void>"
    methods:
      - name: select
        params:
          - name: date
            type: D | DateRange<D> | null
        desc: "Selects the given date."
        returnType: void
      - name: selectYear
        params:
          - name: normalizedYear
            type: D | DateRange<D> | null
        desc: "Emits the selected year in multiyear view."
        returnType: void
      - name: selectMonth
        params:
          - name: normalizedMonth
            type: D | DateRange<D> | null
        desc: "Emits selected month in year view."
        returnType: void
      - name: registerInput
        params:
          - name: input
            type: NxDatepickerInputInterface<D>
          - name: inputDateMode
            type: string
        desc: "Register an input with this datepicker."
        returnType: void
      - name: registerToggle
        params:
          - name: toggle
            type: NxDatepickerToggleComponent<D>
        desc: "Register an input toggle with this datepicker."
        returnType: void
      - name: open
        params: 
        desc: "Open the calendar."
        returnType: void
      - name: close
        params: 
        desc: "Close the calendar."
        returnType: void
      - name: getStartAtDate
        params: 
        returnType: D | null
      - name: handleTodayButtonClick
        params: 
        returnType: void
  - name: NxDatepickerToggleIconComponent
    selector: [nxDatepickerToggleIcon]
    desc: |
      Can be used to override the icon of a `nxDatepickerToggle`.
  - name: NxDatepickerToggleComponent
    selector: nx-datepicker-toggle
    inputs:
      - name: for
        desc: "Datepicker instance that the button will toggle."
        type: "NxDatepickerComponent<D>"
      - name: tabindex
        desc: "Sets the tabindex for the toggle button. Default: 0."
        type: "NumberInput"
    methods:
      - name: keydownHandler
        params:
          - name: event
            type: KeyboardEvent
        returnType: void
  - name: NxDatepickerContentComponent
    selector: nx-datepicker-content
    desc: |
      Component used as the content for the datepicker dialog and popup. We use this instead of using
      NxCalendarComponent directly as the content so we can control the initial focus. This also gives us a
      place to put additional features of the popup that are not part of the calendar itself in the
      future. (e.g. confirmation buttons).
  - name: NxCalendarComponent
    selector: nx-calendar
    desc: |
      A calendar that is used as part of the datepicker.
    inputs:
      - name: isRange
        desc: "Whether the datepicker should be in date range selection mode"
        default: input<boolean>(false)
        type: "InputSignal<boolean>"
      - name: startView
        desc: "Whether the calendar should be started in month or year view."
        default: 'month'
        type: "'month' | 'year' | 'multi-year'"
      - name: dateFilter
        desc: "A function used to filter which dates are selectable."
        type: "(date: D) => boolean"
      - name: showTodayButton
        desc: "Determines whether the today button is displayed in the calendar."
        default: false
        type: "boolean"
      - name: startAt
        desc: "A date representing the period (month or year) to start the calendar in."
        type: "D | null"
      - name: selected
        desc: "The currently selected date."
        type: "D | DateRange<D> | null"
      - name: minDate
        desc: "The minimum selectable date."
        type: "D | null"
      - name: maxDate
        desc: "The maximum selectable date."
        type: "D | null"
    outputs:
      - name: selectedChange
        desc: "Emits when the currently selected date changes."
        type: "EventEmitter<D | DateRange<D>>"
      - name: yearSelected
        desc: "Emits the year chosen in multiyear view. This doesn't imply a change on the selected date."
        type: "EventEmitter<D>"
      - name: monthSelected
        desc: "Emits the month chosen in year view. This doesn't imply a change on the selected date."
        type: "EventEmitter<D>"
      - name: todayButtonClick
        desc: "Emits when the Today button is clicked. This doesn't imply a change on the selected date."
        type: "EventEmitter<void>"
    methods:
      - name: todayButtonHandler
        params: 
        desc: "Handles event on the today button"
        returnType: void
      - name: todayButtonKeydownHandler
        params:
          - name: event
            type: KeyboardEvent
        returnType: void
  - name: NxCalendarBodyComponent
    selector: [nx-calendar-body]
    desc: |
      An internal component used to display calendar data in a table.
    inputs:
      - name: label
        desc: "The label for the table. (e.g. 'Jan 2017')."
        type: "string"
      - name: rows
        desc: "The cells to display in the table."
        type: "NxCalendarCell[][]"
      - name: todayValue
        desc: "The value in the table that corresponds to today."
        type: "number"
      - name: selectedValue
        desc: "The value in the table that is currently selected."
        default: null
        type: "number | null"
      - name: selectedEndDate
        default: input<number | null>(null)
        type: "InputSignal<number | null>"
      - name: betweenRange
        default: input<number[]>([])
        type: "InputSignal<number[]>"
      - name: numCols
        desc: "The number of columns in the table."
        default: 7
        type: "number"
      - name: allowDisabledSelection
        desc: "Whether to allow selection of disabled cells."
        default: false
        type: "boolean"
      - name: activeCell
        desc: "The cell number of the active cell in the table."
        default: 0
        type: "number"
      - name: previousItems
        desc: "The items to display in the first row in the offset space."
        default: 0
        type: "number"
      - name: followingItems
        desc: "The items to display in the last row in the offset space."
        default: 0
        type: "number"
    outputs:
      - name: selectedValueChange
        desc: "Emits when a new value out of rows is selected."
        type: "EventEmitter<number>"
      - name: hoverValueChange
        type: "EventEmitter<number>"
      - name: selectedValueChangeToPrevious
        desc: "Emits when a new value out of previousItems is selected."
        type: "EventEmitter<number>"
      - name: selectedValueChangeToFollowing
        desc: "Emits when a new value out of followingItems is selected."
        type: "EventEmitter<number>"
  - name: NxMonthViewComponent
    selector: nx-month-view
    desc: |
      An internal component used to display a single month in the datepicker.
    inputs:
      - name: isRange
        default: input(false)
        type: "InputSignal<boolean>"
      - name: dateFilter
        desc: "A function used to filter which dates are selectable."
        type: "(date: D) => boolean"
      - name: activeDate
        desc: "The date to display in this month view (everything other than the month and year is ignored)."
        type: "D"
      - name: selected
        desc: "The currently selected date."
        type: "D | DateRange<D> | null"
      - name: minDate
        desc: "The minimum selectable date."
        type: "D | null"
      - name: maxDate
        desc: "The maximum selectable date."
        type: "D | null"
    outputs:
      - name: selectedChange
        desc: "Emits when a new date is selected."
        type: "EventEmitter<D | DateRange<D> | null>"
      - name: activeDateChange
        desc: "Emits when any date is activated."
        type: "EventEmitter<D>"
      - name: hoverDateChange
        desc: "Emits when user is hovering on date cell or navigating on date cells by keyboard"
        type: "EventEmitter<D>"
    methods:
      - name: handleHoverChange
        params:
          - name: date
            type: number
          - name: monthsToAdd
            type: number
        returnType: void
  - name: NxMultiYearViewComponent
    selector: nx-multi-year-view
    desc: |
      An internal component used to display a year selector in the datepicker.
    inputs:
      - name: dateFilter
        desc: "A function used to filter which dates are selectable."
        type: "(date: D) => boolean"
      - name: activeDate
        desc: "The date to display in this multi-year view (everything other than the year is ignored)."
        type: "D"
      - name: selected
        desc: "The currently selected date."
        type: "D | DateRange<D> | null"
      - name: minDate
        desc: "The minimum selectable date."
        type: "D | null"
      - name: maxDate
        desc: "The maximum selectable date."
        type: "D | null"
    outputs:
      - name: selectedChange
        desc: "Emits when a new year is selected."
        type: "EventEmitter<D>"
      - name: yearSelected
        desc: "Emits the selected year. This doesn't imply a change on the selected date"
        type: "EventEmitter<D>"
      - name: activeDateChange
        desc: "Emits when any date is activated."
        type: "EventEmitter<D>"
  - name: NxYearViewComponent
    selector: nx-year-view
    desc: |
      An internal component used to display a single year in the datepicker.
    inputs:
      - name: isRange
        default: input(false)
        type: "InputSignal<boolean>"
      - name: dateFilter
        desc: "A function used to filter which dates are selectable."
        type: "(date: D) => boolean"
      - name: activeDate
        desc: "The date to display in this year view (everything other than the year is ignored)."
        type: "D"
      - name: selected
        desc: "The currently selected date."
        type: "D | DateRange<D> | null"
      - name: minDate
        desc: "The minimum selectable date."
        type: "D | null"
      - name: maxDate
        desc: "The maximum selectable date."
        type: "D | null"
    outputs:
      - name: selectedChange
        desc: "Emits when a new month is selected."
        type: "EventEmitter<D>"
      - name: monthSelected
        desc: "Emits the selected month. This doesn't imply a change on the selected date"
        type: "EventEmitter<D>"
      - name: activeDateChange
        desc: "Emits when any date is activated."
        type: "EventEmitter<D>"

---
# Overview
----------------- | --------------------------- | --------------------------------------- | ---------- | --------------------------------------- |
    | `NxNativeDateModule` | `Date`                      | `en-US` only                            | None       | `@aposin/ng-aquila/datefield`           |
    | `NxMomentDateModule` | `Moment`                    | [Moment locales](https://momentjs.com/) | Moment.js  | `@aposin/ng-aquila/moment-date-adapter` |
    | `NxIsoDateModule`    | ISO `string` (`YYYY-MM-DD`) | [dayjs locales](https://day.js.org/)    | dayjs      | `@aposin/ng-aquila/iso-date-adapter`    |
---
