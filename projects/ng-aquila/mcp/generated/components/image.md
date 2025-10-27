--- 
title: Images
category: components

module: NxImageModule
components:
  - name: NxFigureComponent
    selector: figure[nxFigure]
    inputs:
      - name: nxFigure
        desc: "Sets the type of the visual appearance of the image. The default value  is 'auto'."
        type: "| 'auto'  | '1by1'  | '1dot8by1'  | '1dot2by1'  | '1by1dot1'  | '2dot6by1'  | 'rounded' | string | null | undefined"
  - name: NxImageDirective
    selector: img[nxImg]

---