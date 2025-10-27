--- 
title: Video
category: components

module: NxVideoModule
components:
  - name: NxVideoComponent
    selector: nx-video
    inputs:
      - name: videoId
        desc: "Sets the id of the YouTube video."
        type: "string"
      - name: altText
        desc: "Sets the value of the alt attribute for the preview image."
        type: "string"
      - name: playButtonAriaLabel
        desc: "Sets the value of the aria-label attribute on the play button (Default: Play Video)."
        type: "string"
      - name: previewImageSrc
        desc: "Sets the preview image. If this is not provided, an image from YouTube will be used as default."
        type: "string"
      - name: showPlayerControls
        desc: "Sets player controls. If set to false, player controls are not available."
        type: "BooleanInput"
      - name: allowFullScreen
        desc: "Sets fullscreen option. If set to false, fullscreen option is not available."
        type: "BooleanInput"
      - name: interfaceLanguage
        desc: "Sets interface language. Can be used to override the interface language determined by YouTube."
        type: "string"
    methods:
      - name: select
        params: 
        returnType: void

---
# Overview
The video component only supports YouTube videos. We embedded the YouTube player as iframe tag. For detailed information about this technique, please check out the official [documentation](https://developers.google.com/youtube/player_parameters?hl=en). In order to save bandwidth, the iframe will only be loaded after the user has selected the preview image. Please note that the width of the video depends on the enclosing element and that the player has a fixed aspect ratio of 16:9. YouTube recommends that players should be at least 480px wide and 270px tall.
