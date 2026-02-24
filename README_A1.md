# Assessment #1 — CIE-Luv and CIE-Lab Color Spaces
**CS 5330: Computer Vision and Pattern Recognition**
**Northeastern University — Spring 2026**
**Sushma Ramesh**

---

## Video Presentation
[▶️ Watch the full presentation here](https://drive.google.com/file/d/1q012V2e1oq-aTj5iyOq9XE3IemhIrv_b/view?usp=drive_link)

> **Duration:** ~10 minutes
> **Format:** Narrated slide presentation covering CIE-Luv and CIE-Lab color spaces

---

## Topic Overview
**Assigned Topic:** Color Spaces — Explain CIE-Luv and CIE-Lab: their intent, design, and appropriate uses.

This topic sits within the **Color Spaces** module of CS 5330, following the introduction of the CIE XYZ color space and preceding the discussion of chromaticity spaces and histograms. The audience is assumed to be familiar with RGB, HSV, and XYZ color spaces from prior lectures.

The central question this presentation answers is:
> *If we already have XYZ, why did we need CIE-Luv and CIE-Lab?*

The answer lies in **perceptual uniformity** — the idea that equal numerical distances in a color space should correspond to equal perceived differences by the human visual system. XYZ fails this criterion. CIE-Luv and CIE-Lab, both standardized by the CIE in 1976, were designed specifically to address this failure.

---

## Presentation Structure

### Slide 1 — Title & Introduction
Introduces the presenter, the topic, and where it fits within the course (after XYZ, before chromaticity histograms).

### Slide 2 — Motivation: The Problem with XYZ
Explains why XYZ, despite being device-independent and physically grounded, is perceptually non-uniform. Equal distances in XYZ do not correspond to equal perceived color differences, which is a critical limitation for color difference calculations.

### Slide 3 — MacAdam Ellipses
Introduces MacAdam Ellipses (1942) as the key visual demonstration of XYZ's perceptual non-uniformity. Colors within each ellipse are indistinguishable to the human eye, yet the ellipses vary dramatically in size and orientation across the XYZ chromaticity diagram — showing the space is far from perceptually uniform.

### Slide 4 — The 1976 CIE Solutions
Presents the historical context: in 1976, the CIE standardized two new color spaces as solutions — CIELUV (CIE-Luv) and CIELAB (CIE-Lab). Both share the L* lightness axis but differ in how they encode chromaticity.

### Slide 5 — Shared Foundation: The L* Lightness Channel
Explains L* (perceptual lightness), which is shared by both spaces. L* = 0 is black, L* = 100 is white, and the scale is designed to be perceptually linear — a step from L*=20 to L*=30 looks the same size as a step from L*=70 to L*=80 to a human observer.

### Slide 6 — CIE-Luv: Design and Formula
Covers the CIE-Luv color space in detail:
- The u* and v* chromaticity axes derived from a projective transformation of XYZ
- Why Luv uses a linear chromaticity diagram (u'v'), making it geometrically intuitive
- The mathematical formulas for L*, u*, and v*
- The reference white point (D65)

### Slide 7 — CIE-Lab: Design and Formula
Covers the CIE-Lab color space in detail:
- The a* axis (green ↔ red) and b* axis (blue ↔ yellow), reflecting opponent color theory
- How Lab's axes align with how the human visual system encodes color
- The cube-root nonlinearity used to achieve perceptual uniformity
- The mathematical formulas for L*, a*, and b*

### Slide 8 — Delta E: Measuring Color Difference
Introduces Delta E (ΔE) as the practical payoff of perceptually uniform spaces. In Lab or Luv, color difference between two colors is simply the Euclidean distance in the space. Explains ΔE thresholds (e.g., ΔE < 1 is imperceptible, ΔE > 5 is clearly noticeable) and their use in industry and computer vision.

### Slide 9 — LCH: Cylindrical Representation
Briefly introduces LCH (Lightness, Chroma, Hue) as a cylindrical reparameterization of both Lab and Luv, making the spaces more intuitive for color selection and manipulation (similar to how HSV relates to RGB).

### Slide 10 — CIE-Luv vs CIE-Lab: When to Use Which
Provides a direct comparison and practical "rule of thumb":
- **Luv** → best for **emissive/additive color** (displays, monitors, lighting)
- **Lab** → best for **reflective/surface color** (printing, physical objects, most CV tasks)
Explains why Lab has become the dominant choice in computer vision and image processing.

### Slide 11 — Computer Vision Application: Skin Detection
Demonstrates a real CV use case — skin color segmentation is significantly more reliable in Lab space than in RGB or HSV, because skin tones cluster more tightly and consistently in the a*b* plane. This directly ties the topic to the course's CV focus.

### Slide 12 — Summary & Takeaways
Recaps the key ideas:
- XYZ is not perceptually uniform → MacAdam ellipses show this
- CIE-Luv and CIE-Lab were the 1976 solutions
- Both share L* lightness; they differ in chromaticity encoding

---

## Files in This Repository

| File | Description |
|------|-------------|
| `README.md` | This file — overview, structure, reflection, acknowledgements |
| `slides.pdf` | PDF export of the full slide deck used in the presentation |

---

## Reflection

For this assessment, I was assigned CIE-Luv and CIE-Lab color spaces. I structured the presentation around the core problem these spaces solve — perceptual non-uniformity in XYZ — and built from motivation to concept to application, using MacAdam Ellipses, Delta E, and a skin detection example to make the content relevant to a computer vision audience. The most challenging part was clearly distinguishing Luv from Lab, which I resolved using a simple rule of thumb: Luv for emissive/display color, Lab for surface/CV tasks.

---

## Acknowledgements

### Course Context
This presentation was created for CS 5330: Computer Vision and Pattern Recognition at Northeastern University's Khoury College of Computer Sciences, Spring 2026.

### Resources Used
- CIE 1976 official documentation and technical reports
- Wikipedia articles on CIELUV and CIELAB (used for formula verification and historical context)
- MacAdam, D.L. (1942). "Visual sensitivities to color differences in daylight." *Journal of the Optical Society of America* — referenced for the MacAdam Ellipses diagram
- Fairchild, M.D. *Color Appearance Models* — referenced for perceptual uniformity concepts
- Course lecture slides, topic outlines, and readings from CS 5330

### LLM Usage
I used **Claude (Anthropic)** as a learning and production aid during this project in the following specific way:

**Concept verification** — To verify my understanding of the mathematical formulas for L*, u*, v*, a*, and b* and confirm that my explanations were technically accurate before including them in slides

---

*Submitted to Gradescope for CS 5330 Assessment #1 — Spring 2026*