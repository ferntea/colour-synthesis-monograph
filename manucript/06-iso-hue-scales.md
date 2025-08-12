# Chapter 6: Iso-Hue Chroma Scales – A New Paradigm

## 6.1 The Problem: Non-Monotonic Chroma in Individual Dyes

In traditional dyeing practice, it is often assumed that increasing the concentration of a dye leads to a proportional increase in color saturation. However, experimental data reveals a more complex behavior:  
> For many acid and reactive dyes, chroma ($ C^* $) increases with concentration up to a maximum, after which it declines.

This **extremal dependence** arises from physical effects such as:
- Molecular aggregation
- Absorption saturation
- Light scattering from undissolved dye or substrate

As a result, it becomes impossible to build a **monotonic shade series** using a single dye — a critical limitation for applications requiring predictable color progression, such as textile batch matching or digital color reproduction.

Moreover, even when chroma increases, the hue angle  
$ h^\circ = \tan^{-1}\left( \frac{b^*}{a^*} \right) $  
may drift, further complicating the formulation of uniform color scales.

## 6.2 Defining the Iso-Hue Chroma Scale

To overcome these limitations, we introduce the concept of the **iso-hue chroma scale**:

> An *iso-hue chroma scale* is a sequence of dye formulations (e.g., triads) that maintain an approximately constant hue angle in CIELAB space while exhibiting a **monotonic increase in chroma**.

This scale is not defined by concentration alone, but by **formulation strategy** — the intelligent combination of dyes to achieve controlled, perceptually uniform saturation.

A related concept is the **perceptual chroma scale**, which ensures that the perceived increase in saturation is uniform across steps, accounting for non-linearities in human vision and material behavior.

These scales are not theoretical constructs — they are **empirically grounded**, derived from large datasets of dye mixtures and validated through instrumental and perceptual evaluation.

## 6.3 Anchor Points: Maximum Chroma of Individual Dyes

To construct an iso-hue chroma scale, we begin with an **anchor point** — a color that defines the hue direction.

We define this anchor as:
- The **maximum chroma** of an individual dye
- At its corresponding **hue angle**
- Measured under standard conditions (D65, 10° observer)

From this point, we seek dye triads that:
- Match the hue within a small tolerance (±2°)
- Exceed the chroma of the individual dye
- Maintain acceptable lightness and fastness

This approach ensures that the scale starts at a perceptually relevant point and extends beyond the limits of single-dye performance.

## 6.4 Building the Scale: Constant Hue, Increasing Chroma

Once the anchor point is established, the scale is extended by increasing chroma along the fixed hue direction.

In CIELAB, this corresponds to moving along a radial line in the $ a^*b^* $ plane:
$$
a^* = C \cdot \cos(h^\circ), \quad b^* = C \cdot \sin(h^\circ)
$$
where $ C $ is the chroma, and $ h^\circ $ is the fixed hue angle.

For each target $ (L^*, a^*, b^*) $, we search the dye mixture database to find the **closest matching triad** — using reverse modeling, nearest-neighbor search, or optimization.

The resulting sequence of mixtures forms the **iso-hue chroma scale**, which can be:
- Visualized in Lab space
- Evaluated for perceptual uniformity
- Applied in formulation practice

## 6.5 Validation in CIELAB and CAM16-UCS

To validate the scale, we assess:
- **Hue stability**: deviation from target $ h^\circ $
- **Chroma monotonicity**: no decrease in $ C^* $
- **Perceptual uniformity**: using CAM16-UCS and CIEDE2000

In many cases, triad mixtures not only match the hue of the individual dye but **exceed its maximum chroma**, particularly when the dyes have complementary absorption spectra.

This phenomenon — **chroma synergy** — demonstrates that **mixtures can outperform their components**, opening new possibilities for high-saturation color design.

## 6.6 Application: Textile Shade Builds and Ink Formulation

The iso-hue chroma scale has practical applications in:
- **Textile dyeing**: creating uniform shade series from pale to deep tones
- **Digital printing**: designing ink sets with perceptually linear saturation
- **Color matching systems**: improving accuracy by preserving hue during formulation
- **Education and design**: teaching the principles of material-based color control

Moreover, the scale can be extended to **n-dye systems** (tetrads, pentads) to further expand the gamut and improve formulation flexibility.

## 6.7 Summary

The iso-hue chroma scale represents a **paradigm shift** in color formulation — from concentration-driven to **geometry-driven design** in color space. By leveraging mixture behavior and perceptual modeling, it enables the creation of **predictable, uniform, and material-accurate** color progressions.

This chapter lays the foundation for the computational tools and database approaches developed in the following chapters.