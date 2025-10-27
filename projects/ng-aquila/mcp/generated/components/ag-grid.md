--- 
title: Ag-grid
category: Third-party
noApi: true



---
# Overview
For complex data tables (data grids) we suggest using the [ag-grid](https://www.ag-grid.com/) library. 

With the major update in `ag-grid-angular` v33, AG Grid introduced the **Theming API**, where themes are imported as JavaScript objects and passed via the `[theme]` input.  
We provide `themeAquila` (for open-source) and `themeAllianz` (for internal Allianz projects), both built on top of AG Grid’s Alpine theme. These support our custom styling via the `theming-api-aquila` class and optional param sets:
- `themeAquilaDenseParams` for more compact rows
- `themeAquilaZebraParams` for zebra striped rows
