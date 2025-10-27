--- 
title: Licence Plate
category: components

module: NxLicencePlateModule
components:
  - name: NxLicencePlateValidatorDirective
    selector: [nxLicensePlate]
    inputs:
      - name: nxLicensePlate
        desc: "Licence plate type. Supports validation for german standard and special plate numbers. Choose `other` to allow all values."
        default: 'other'
        type: "'de_standard' | 'de_season' | 'de_special' | 'other' | 'euro'"
    methods:
      - name: validate
        params:
          - name: control
            type: AbstractControl<any, any, any>
        returnType: ValidationErrors | null
  - name: NxLicencePlateEuroPrefixComponent
    selector: nx-licence-plate-euro-prefix
    desc: |
      Euro country prefix for the licence plate input.
  - name: NxLicencePlateSeasonSuffixComponent
    selector: nx-licence-plate-season-suffix
    desc: |
      Suffix for seasonal licence plate inputs.
    inputs:
      - name: startMonth
        desc: "Start month of the licence plate."
        default: 1
        type: "number"
      - name: endMonth
        desc: "End month of the licence plate."
        default: 1
        type: "number"

---
# Overview
The licence plate module contains different components to create an input for european licence plate numbers. It constists of a prefix `<nx-licence-plate-euro-prefix>` for the european country code, a validator directive `nxLicencePlate` and a suffix `nx-licence-plate-season-suffix` for seasonal licence plates. The optional validator currently supports only german standard and special number formats. For other countries please use your own validation by providing a `pattern`. All parts are meant to be combined with the form field to create an individual input for different licence plate fromats.
