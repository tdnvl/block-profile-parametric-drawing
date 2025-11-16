# Block Profile Parametric Drawing

A tiny, self-contained HTML app that draws a parametric side view of a chanter and key block on an HTML `<canvas>`.  

---

## Overview

The app lets you:

- Enter a few geometric parameters in millimeters
- See a clean side view update instantly on the canvas
- Toggle dimension annotations on and off
- Export the drawing as a transparent PNG

It is designed for quick visual checks of proportions rather than precise manufacturing drawings.

---

## Parameters

All dimensions are in millimeters.

- **Chanter diameter (mm)**  
  Outside diameter of the chanter at the block location.

- **Block outside diameter (mm)**  
  Outside diameter of the block.

- **Block width (mm)**  
  Width of the block along the chanter axis.

- **Block fillet radius (mm)**  
  Corner radius at the top of the block.

  --

## How to run it

1. Save the file as `index.html` (or any `.html` name you like).
2. Open it in a modern browser (Chrome, Firefox, Safari, Edge).

That is all you need. There are no dependencies beyond the browser.

---

## Controls

At the top of the page you will find:

- Number fields for:
  - Chanter diameter
  - Block outside diameter
  - Block width
  - Block fillet radius

  As you type or change values, the canvas redraws automatically.

- **Show dimensions** checkbox  
  - Checked: dimension lines and labels appear on the drawing.  
  - Unchecked: only the geometry is drawn.

- **Export as transparent PNG** button  
  - Downloads the current canvas as `block-profile.png`.
  - The PNG keeps the canvas background, which is styled in CSS.  
    You can change the background in the `canvas` CSS rule if you want a fully transparent export.

---

## Exporting as PNG

The **Export as transparent PNG** button triggers `canvas.toDataURL("image/png")` and downloads the image.

If you want a fully transparent drawing:

1. Change the canvas background in the CSS:

   ```css
   canvas {
     border: 1px solid #ddd;
     border-radius: 4px;
     width: 100%;
     height: auto;
     max-height: 420px;
     background: transparent; /* or remove this line */
     display: block;
   }