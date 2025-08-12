# Table of Contents

## Front Matter
- Preface
- Acknowledgments
- List of Abbreviations
- List of Figures and Tables

## Chapter 1: Introduction – The Challenge of Color Synthesis
- 1.1 What is color synthesis?
- 1.2 From pigments to photons: historical context
- 1.3 The gap between instrumental measurement and human perception
- 1.4 The role of material constraints in color reproduction
- 1.5 Objectives of this work: from theory to formulation

## Chapter 2: Color Science Foundations
- 2.1 CIE Colorimetry: XYZ, L\*a\*b\*, L\*u\*v\*
- 2.2 Perceptual uniformity: CIELAB vs. CAM16-UCS, DIN99d
- 2.3 Hue, chroma, lightness — beyond Euclidean space
- 2.4 Color difference metrics: CIEDE2000, CAM16-ΔE
- 2.5 The role of viewing conditions in appearance models

## Chapter 3: Models of Color Mixing
- 3.1 Additive mixing (light, screens)
- 3.2 Subtractive mixing (dyes, paints)
- 3.3 Spatial mixing: melange, inkjet, halftone
- 3.4 Kubelka-Munk theory and its limitations
- 3.5 Yule–Nielsen correction for dot/fiber gain
- 3.6 Neugebauer and extended models for printing

## Chapter 4: Dyeing and Formulation Chemistry
- 4.1 Acid, reactive, disperse dyes — spectral behavior
- 4.2 Concentration vs. chroma: extremal behavior
- 4.3 Dye-dye interactions: aggregation, metamerism
- 4.4 Spectral measurement and database creation
- 4.5 Total dye load and solubility limits

## Chapter 5: The Triad Approach – Building Color from Mixtures
- 5.1 Why three dyes? (Gamut, control, stability)
- 5.2 Full factorial design: 9 levels × 13 dyes → 208,594 triads
- 5.3 Chroma vs. hue plots: identifying protuberances
- 5.4 Synergy in triads: exceeding individual dye chroma
- 5.5 Case studies: red, blue, yellow triads

## Chapter 6: Iso-Hue Chroma Scales – A New Paradigm
- 6.1 The problem: non-monotonic chroma in individual dyes
- 6.2 Definition: *iso-hue chroma series* and *perceptual chroma scale*
- 6.3 Anchor points: maximum chroma of individual dyes
- 6.4 Building the scale: constant hue, increasing chroma
- 6.5 Validation in CIELAB and CAM16-UCS
- 6.6 Application: textile shade builds, ink formulation

## Chapter 7: Database-Driven Color Formulation
- 7.1 From experimental data to digital library
- 7.2 Structure of the dye mixture database
- 7.3 Reverse modeling: from target Lab → dye recipe
- 7.4 kNN, regression, and optimization methods
- 7.5 Constraints: total dye, cost, fastness

## Chapter 8: Computational Tools for Color Synthesis
- 8.1 Python and the `colour-science` library
- 8.2 Generating chroma vs. hue plots (rectangular and polar)
- 8.3 Finding triads that exceed individual dye chroma
- 8.4 Building iso-hue scales algorithmically
- 8.5 Visualization and GUI design (optional)

## Chapter 9: Advanced Color Systems
- 9.1 Plasmon resonance and structural color
- 9.2 Mie theory, DDA, FDTD for nanoparticle color
- 9.3 From simulation to CIELAB
- 9.4 Comparison with dye-based color
- 9.5 Hybrid systems: dyes + nanostructures

## Chapter 10: Spatial Color Synthesis – Melange and Inkjet
- 10.1 Melange: fiber-level spatial mixing
- 10.2 Inkjet: dot-level spatial mixing
- 10.3 Similarities and differences in perception
- 10.4 Linear reflectance mixing and Yule–Nielsen correction
- 10.5 Texture, gloss, and perceived chroma

## Chapter 11: Art to Fiber – Digital Reproduction of Paintings in Tapestry
- 11.1 From painting to digital image: calibration and capture
- 11.2 Color quantization: k-means in CAM16-UCS
- 11.3 Matching digital colors to dyed fibers
- 11.4 Weaving layout generation
- 11.5 Case study: reproduction of a classical painting

## Chapter 12: Future Directions and Open Problems
- 12.1 Machine learning for predictive formulation
- 12.2 Real-time color matching with AR/VR
- 12.3 Sustainable dyeing: minimizing chroma loss
- 12.4 Perceptual sensitivity testing using material scales
- 12.5 Towards a universal color formulation engine

## Appendices
- A. Python code examples
- B. Sample dataset structure (CSV format)
- C. Dye database template
- D. Glossary of terms
- E. List of software and libraries

## Bibliography
- Comprehensive list of scientific and industrial references

## Index
- Detailed keyword index