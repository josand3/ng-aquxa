--- 
title: Progress Indicator
category: components
alias: stepper

module: NxProgressStepperModule
components:
  - name: NxProgressStepperDirective
    selector: [nxProgressStepper]
    inputs:
      - name: currentStepLabel
        desc: "Sets the label on the left side showing the current step label. Used for mobile viewports."
        type: "string"
  - name: NxMultiStepperComponent
    selector: nx-multi-stepper
    inputs:
      - name: direction
        desc: "Sets the direction of the multi stepper."
        type: "'vertical' | 'horizontal'"
  - name: NxStepComponent
    selector: nx-step
    methods:
      - name: isErrorState
        params:
          - name: control
            type: FormControl<any> | null
          - name: form
            type: NgForm | FormGroupDirective | null
        desc: "Custom error state matcher that checks for validity of the step form."
        returnType: boolean
  - name: NxStepperNextDirective
    selector: button[nxStepperNext]
  - name: NxStepperPreviousDirective
    selector: button[nxStepperPrevious]
  - name: NxProgressStepperComponent
    selector: nx-progress-stepper
    inputs:
      - name: progressbarAriaLabel
        desc: "Overrides the `aria-label` of the nx-progressbar. Defaults to 'Progress'"
        default: 'Progress'
        type: "string | undefined"
      - name: progressbarAriaLabeledBy
        desc: "Sets the `aria-labelledby` of the nx-progressbar"
        type: "string | undefined"
      - name: progress
        desc: "Sets the current value/progress of the progress bar."
        type: "number"
  - name: NxSingleStepperComponent
    selector: nx-single-stepper
    inputs:
      - name: progressbarAriaLabel
        desc: "Overrides the `aria-label` of the nx-progressbar. Defaults to 'Progress'"
        default: 'Progress'
        type: "string | undefined"
      - name: progressbarAriaLabeledBy
        desc: "Sets the `aria-labelledby` of the nx-progressbar"
        type: "string | undefined"
      - name: nextLabel
        desc: "Sets the label on the right showing the next step."
        type: "string"
  - name: NxMultiStepItemComponent
    selector: nx-multi-step-item
    inputs:
      - name: label
        desc: "The label of the step."
        type: "string | CdkStepLabel"
      - name: direction
        desc: "The direction of the step"
        type: "'vertical' | 'horizontal'"
      - name: selected
        desc: "Sets the selected step."
        type: "BooleanInput"
      - name: active
        desc: "Sets the active step."
        type: "BooleanInput"
      - name: disabled
        type: "BooleanInput"
      - name: last
        desc: "Sets the last step."
        type: "BooleanInput"
      - name: completed
        desc: "Sets the step completed."
        type: "BooleanInput"
      - name: wasCompleted
        desc: "Sets the step was completed."
        type: "BooleanInput"
      - name: ariaControls
        type: "string"
  - name: NxMultiStepperGroupComponent
    selector: nx-step-group
    inputs:
      - name: label
        desc: "Sets the label of a group that is shown to the user."
        type: "string"

---
# Overview
An indicator is a wizard-like workflow that divides content into logical steps. You provide the content and distribute it in different steps. The indicator will ensure to show only the current content and inform the user about the overall progress.

You can choose between "Single Indicator", "Multi Indicator" and "Progress Indicator". Those indicators can show different details of the overall progress.

Ensure that you import the required modules. The progress indicator relies on the [Angular CDK stepper ](https://material.angular.io/cdk/stepper/overview) implementation so you have to fulfill the peer dependency on the CDK to use the indicator.
