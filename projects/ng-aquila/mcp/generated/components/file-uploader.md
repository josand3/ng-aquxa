--- 
title: File uploader
category: components

module: NxFileUploaderModule
components:
  - name: NxFileUploaderComponent
    selector: nx-file-uploader
    inputs:
      - name: ariaDescribedBy
        desc: "aria-describedby ids that will be applied to the inner controls"
        default: input<string | null>()
        type: "InputSignal<string | null | undefined>"
      - name: strictAcceptValidation
        desc: "Whether to validate files that don't have provide a file type. Disabled by default."
        default: false
        type: "boolean"
      - name: noBlockingValidators
        desc: "Whether the file uploader use common validators (file type, file size)."
        type: "BooleanInput"
      - name: required
        desc: "Whether the file uploader is required."
        type: "BooleanInput"
      - name: value
        desc: "The value of the file upload."
        type: "FileItem[] | undefined"
      - name: name
        desc: "Name that is used for accessibility."
        type: "string"
      - name: disabled
        desc: "Whether the file uploader is disabled."
        type: "BooleanInput"
      - name: multiple
        desc: "Whether the file uploader accepts multiple files to be added."
        type: "BooleanInput"
      - name: accept
        desc: "The accepted file types"
        type: "string"
      - name: maxFileSize
        desc: "The max file size in bytes used for validation"
        type: "NumberInput"
      - name: uploader
        desc: "Sets the file uploader for the component."
        type: "NxFileUploader"
      - name: maxFileNumber
        desc: "The max number of files that is accepted."
        type: "NumberInput"
      - name: itemTemplate
        desc: "Sets the template for the file items."
        type: "TemplateRef<any>"
    outputs:
      - name: valueChange
        desc: "An event emitted when queue is changed.  Emits the changed array of FileItems."
        type: "EventEmitter<FileItem[]>"
      - name: fileDeleted
        desc: "An event emitted when a file is deleted from the queue.  Emits the deleted FileItem."
        type: "EventEmitter<FileItem>"
      - name: filesSelected
        desc: "An event emitted when one or more files were added to the file input.  Emits the selected `FileItem | FileItem[]`."
        type: "EventEmitter<FileItem[]>"
      - name: openedChange
        desc: "Event emitted when the file picker dialog has been toggled."
        type: "EventEmitter<boolean>"
    methods:
      - name: updateErrorState
        params: 
        returnType: void
      - name: removeFile
        params:
          - name: file
            type: any
        desc: "Removes a file from the value list of the file upload input."
        returnType: void
      - name: uploadFiles
        params: 
        desc: "Uploads the files via the defined uploader."
        returnType: void
      - name: setDisabledState
        params:
          - name: isDisabled
            type: boolean
        returnType: void
  - name: NxFileUploaderButtonDirective
    selector: [nxFileUploadButton]
    inputs:
      - name: disabled
        desc: "Whether the file uploader is disabled"
        type: "boolean"
    methods:
      - name: setDescribedByIds
        params:
          - name: ids
            type: string[]
        returnType: void
      - name: onClick
        params: 
        returnType: void
  - name: NxFileUploaderHintDirective
    selector: [nxFileUploadHint]
  - name: NxFileUploaderDropZoneComponent
    selector: nx-file-uploader-drop-zone
    inputs:
      - name: disabled
        desc: "Whether the file uploader is disabled."
        type: "boolean"
    outputs:
      - name: fileDropped
        desc: "An event emitted when files were dropped."
        type: "EventEmitter<File[]>"
    methods:
      - name: onDrop
        params:
          - name: event
            type: DragEvent
        returnType: void
      - name: onDragOver
        params:
          - name: event
            type: DragEvent
        returnType: void
      - name: onDragLeave
        params:
          - name: event
            type: DragEvent
        returnType: void
      - name: onDragEnd
        params:
          - name: event
            type: DragEvent
        returnType: void
      - name: onDragStart
        params:
          - name: event
            type: DragEvent
        returnType: void
  - name: NxFileUploaderTriggerDirective
    selector: [nxFileUploadTriggerFor]
    inputs:
      - name: nxFileUploadTriggerFor
        desc: "References the file upload component instance that the trigger is associated with."
        type: "NxFileUploaderComponent"
  - name: NxFileUploaderItemName
    selector: nx-file-upload-name
    desc: |
      Shows the file name.
    inputs:
      - name: name
        desc: "The filename."
        type: "string"
  - name: NxFileUploaderItemSize
    selector: nx-file-upload-size
    desc: |
      Shows a file size in Megabyte (MB) or an alternative label while the file is uploading.
    inputs:
      - name: size
        desc: "The size of the file in bytes."
        type: "number"
      - name: isUploading
        desc: "Whether the file is uploading at the moment. Default: false."
        type: "boolean"
      - name: uploadingLabel
        desc: "The label that is shown while uploading the file."
        type: "string"
  - name: NxFileUploaderItemStatus
    selector: nx-file-upload-status
    desc: |
      Shows the current uploading status of a file.
    inputs:
      - name: isUploading
        desc: "Whether the file is uploading at the moment. If this is true, a spinner is shown. Default: false."
        type: "boolean"
      - name: isUploaded
        desc: "Whether the file was uploaded. If this is true, a `check-circle` icon is shown. Default: false."
        type: "boolean"
      - name: uploadedLabel
        desc: "The label that is used once the file has been uploaded (used by screen readers)."
        type: "string"
  - name: NxFileUploaderItemDelete
    selector: nx-file-upload-delete
    desc: |
      Shows a delete button.
    inputs:
      - name: isUploading
        desc: "Whether the file is uploading at the moment. If true, the button is disabled. Default: false."
        default: false
        type: "boolean"
      - name: disabled
        desc: "Whether this button is disabled. The button is additionally disabled while uploading. Default: false."
        default: false
        type: "boolean"
      - name: deleteLabel
        desc: "The label that is used for the delete button (used by screen readers)."
        type: "string"

---
# Overview
Use this component when you want users to upload files. The files can be uploaded via file selection or dropped in the drop zone. The `nx-file-uploader` shows the selected files in the queue list. In each row of this list, the file name is displayed with the current status and the available actions. The component is a wrapper around the native `input[type=file]` element and ensures that the standard HTML attributes (e.g. multiple) work as expected.

Please note that if you allow multiple files upload, users will also be able to upload the same file multiple times. If this is an issue for your project, make sure to implement a backend check.
