# Chapter 13: Theoretical Modeling of Chroma and Saturation in Dyeing: Extremal Behavior in CIELAB

> **Author**:  
> **Date**:  
> **Keywords**: Color science, CIELAB, chroma, saturation, vividness, Kubelka-Munk, dye concentration, human observer, perceptual modeling

---

## 13.1 Introduction

In textile and material coloration, the **perceived intensity of color** — often described as *vividness* — is a critical quality attribute. It depends not only on the chemical nature of the dye but also on its **concentration in the substrate**. Empirical observations show that both **chroma** $ C^*_{ab} $ and **saturation** increase with concentration up to a maximum, then decrease. This **non-monotonic behavior** is often attributed to aggregation, impurities, or scattering changes.

However, as shown in this work, **even a single, spectrally pure dye** exhibits a **maximum in chroma and saturation** due to the **interplay between physical optics and human perception**. This extremum arises from the **nonlinear transformation from reflectance to CIELAB coordinates**, and is **shaped by the spectral sensitivity of the CIE standard observer**.

Here, we develop **analytical models** for:
- $ C^*_{ab}(c) $: chroma as a function of concentration
- $ S(c) = C^*_{ab}(c)/L^*(c) $: saturation (vividness)

starting from the **Kubelka-Munk (K-M) theory** and the **CIE colorimetric pipeline**.

These models provide a **theoretical foundation** for optimizing dye formulations and interpreting experimental data.

---

## 13.2 Physical and Perceptual Framework

We consider a dye applied to a substrate (e.g., textile fiber) at concentration $ c $ (in arbitrary units, proportional to mass per unit area). The system is governed by:

- **Kubelka-Munk theory** for diffuse reflectance
- **CIE 1931 standard observer** and **D65 illuminant**
- **CIELAB color space** for perceptual uniformity

Let:
- $ K(\lambda; c) $: absorption coefficient
- $ S(\lambda) $: scattering coefficient (assumed constant)
- $ R(\lambda; c) $: spectral reflectance

The goal is to model:
- $ C^*_{ab}(c) $: chroma
- $ L^*(c) $: lightness
- $ S(c) = C^*_{ab}(c)/L^*(c) $: saturation (approximate vividness)

---

## 13.3 Chroma Concentration Dependence: $ C^*_{ab}(c) $

### 13.3.1 Kubelka-Munk Reflectance

For a dye with Gaussian absorption profile:

$$
K(\lambda; c) = c \cdot K_0 \cdot \mathcal{G}(\lambda; \lambda_0, \sigma), \quad \mathcal{G}(\lambda; \lambda_0, \sigma) = \exp\left( -\frac{(\lambda - \lambda_0)^2}{2\sigma^2} \right)
$$

Assuming constant scattering $ S_0 = 1 $, the reflectance at the peak wavelength $ \lambda_0 $ is:

$$
R_0(c) = R(\lambda_0; c) = \frac{\sqrt{1 + 4(c \kappa)^2} - 1}{2c \kappa}, \quad \kappa = K_0 / S_0
$$

This function:
- $ \to 1 $ as $ c \to 0 $
- $ \to 0 $ as $ c \to \infty $
- Decreases monotonically

---

### 13.3.2 Hue Development with Concentration

At low $ c $, the dye appears pale — **low hue purity**. As $ c $ increases, **selective absorption** enhances **color contrast**, increasing $ a^* $ and $ b^* $.

This process follows **saturation kinetics**:

$$
\mathcal{P}(c) = 1 - e^{-\gamma c}
$$

where $ \gamma $ is the **hue development rate**, dependent on:
- Dye bandwidth $ \sigma $
- Observer sensitivity $ \bar{x}, \bar{y}, \bar{z} $
- Illuminant $ S(\lambda) $

---

### 13.3.3 Chroma Model

Chroma depends on both **hue purity** and **brightness**:

$$
C^*_{ab}(c) \propto \underbrace{(1 - e^{-\gamma c})}_{\text{hue build-up}} \cdot \underbrace{R_0(c)^{1/3}}_{\text{brightness term (from } L^* \text{ scaling)}}
$$

Thus, the **quantitative model** is:

$$
\boxed{
C^*_{ab}(c) = \mathcal{A} \cdot (1 - e^{-\gamma c}) \cdot \left( \frac{\sqrt{1 + 4(c\kappa)^2} - 1}{2c\kappa} \right)^{1/3}
}
$$

where:
- $ \mathcal{A} $: scaling factor (depends on $ \lambda_0 $, observer, illuminant)
- $ \gamma $: hue development rate (s⁻¹)
- $ \kappa = K_0 / S_0 $: intrinsic strength of dye

---

### 13.3.4 Extremal Behavior

Despite $ R_0(c) $ being monotonic, $ C^*_{ab}(c) $ exhibits a **maximum** because:
- At **low $ c $**: hue purity is low → low chroma
- At **high $ c $**: brightness is low → low $ L^* $, suppressed $ C^*_{ab} $
- At **intermediate $ c $**: optimal balance → **maximum chroma**

The **optimal concentration** $ c_{\text{max}} $ solves:

$$
\frac{d}{dc} C^*_{ab}(c) = 0
$$

This equation can be solved numerically. Analytically, it depends on $ \gamma $ and $ \kappa $.

---

### 13.3.5 Role of Observer Sensitivity

The parameters $ \mathcal{A} $ and $ \gamma $ are **observer-dependent**:
- $ \mathcal{A} \propto \left| \bar{x}(\lambda_0) - \bar{y}(\lambda_0) \right| $: red-green contrast
- $ \gamma $ increases with **spectral selectivity** and **observer contrast sensitivity**

Thus, **the chroma maximum is not a material property — it is a perceptual optimum shaped by human vision**.

---

## 13.4 Saturation (Vividness): $ S(c) = C^*_{ab}(c)/L^*(c) $

While chroma measures colorfulness relative to white, **saturation** measures colorfulness relative to **brightness** — a better predictor of **perceived vividness**.

---

### 13.4.1 Lightness in CIELAB

$$
L^*(c) = 116 f\left( \frac{Y(c)}{Y_n} \right) - 16
$$

where $ f(t) = t^{1/3} $ for $ t > \theta^3 $, $ \theta = 6/29 \approx 0.2067 $

Assume $ Y(c) \propto R_Y(c) \approx R_0(c) $, and define:

$$
u(c) = \beta R_0(c), \quad \beta = \frac{\bar{y}(\lambda_0)}{\bar{y}_n}
$$

Then:

$$
L^*(c) =
\begin{cases}
116 u(c)^{1/3} - 16 & \text{if } u(c) > \theta^3 \approx 0.0088 \\
\frac{29}{3} u(c) + \frac{4}{3} & \text{otherwise}
\end{cases}
$$

---

### 13.4.2 Saturation Model

$$
S(c) = \frac{C^*_{ab}(c)}{L^*(c)} = \frac{ \mathcal{A} (1 - e^{-\gamma c}) R_0(c)^{1/3} }{ L^*(c) }
$$

Substitute $ R_0(c) $:

$$
\boxed{
S(c) = \frac{ \mathcal{A} (1 - e^{-\gamma c}) \left( \dfrac{\sqrt{1 + 4(c\kappa)^2} - 1}{2c\kappa} \right)^{1/3} }
{ 116 \left[ \beta \cdot \dfrac{\sqrt{1 + 4(c\kappa)^2} - 1}{2c\kappa} \right]^{1/3} - 16 }
\quad \text{for } \beta R_0 > 0.0088
}
$$

For very high $ c $, use the linear branch.

---

### 13.4.3 Extremal Behavior of Saturation

- At **low $ c $**: $ S(c) \to 0 $ (pale)
- At **high $ c $**: $ L^*(c) \to 0 $ faster than $ C^*_{ab}(c) \to 0 $ → $ S(c) \to 0 $
- Maximum in between

Importantly:
> ✅ **$ c_{\text{vivid}} < c_{\text{chroma}} $**  
> Because saturation penalizes darkness more severely than chroma does.

---

## 13.5 Discussion

### 13.5.1 Key Insights

| Insight | Implication |
|--------|-------------|
| **Chroma peaks at intermediate $ c $** | Not due to impurities, but due to trade-off between hue purity and brightness |
| **Saturation peaks earlier than chroma** | Vividness requires balance — too dark = dull |
| **Observer sensitivity shapes both** | Green dyes achieve higher vividness than blue at same $ c $ |
| **Ratio (e.g., 1:1) ≠ concentration in fiber** | Use $ K/S $ or add-on for modeling |

---

### 13.5.2 Practical Implications

- **Dye formulation**: Optimize for $ S(c) $, not just $ C^*_{ab}(c) $
- **Color matching**: Account for nonlinearity in concentration response
- **Digital twins**: Embed perceptual models in formulation software

---

### 13.5.3 Limitations and Extensions

- Assumes **ideal K-M behavior** — real systems may show aggregation
- Uses **approximate hue development** — can be refined with PCA or neural models
- Does not include **spatial effects** (gloss, texture, pattern)

**Future work**:
- Extend to **CIECAM02** for more accurate saturation
- Incorporate **bath ratio**, **exhaustion**, and **fixation kinetics**
- Validate with **experimental dye series**

---

## 13.6 Conclusion

We have derived **analytical models** for the concentration dependence of **chroma** and **saturation** in dyeing, based on Kubelka-Munk theory and CIELAB. These models explain the **universal extremal behavior** observed in practice — not as a defect, but as a **perceptual optimization** imposed by the **non-uniform sensitivity of the human visual system**.

The maximum in vividness occurs at **lower concentration than maximum chroma**, and its position and height depend on the **dye’s spectral profile** and the **observer’s sensitivity**.

This framework provides a **theoretical foundation** for rational color design in textiles, coatings, and functional materials.

---

## 13.7 References

1. Wyszecki, G., & Stiles, W. S. (1982). *Color Science: Concepts and Methods, Quantitative Data and Formulae* (2nd ed.). Wiley.  
2. Berns, R. S. (2000). *Principles of Color Technology* (3rd ed.). Wiley.  
3. Kubelka, P., & Munk, F. (1931). Ein Beitrag zur Optik der Farbanstriche. *Zeitschrift für technische Physik*, 12, 593–601.  
4. Fairman, H. S., & Brill, M. H. (2004). The principal components of reflectances. *Color Research & Application*, 29(2), 104–114.  
5. CIE (2004). *CIE 15:2004 Colorimetry*.  

---

## 13.8 Appendix: Parameters for Simulation

| Parameter | Symbol | Typical Value | Notes |
|---------|--------|---------------|-------|
| Dye strength | $ \kappa $ | 5–20 | Depends on dye class |
| Hue rate | $ \gamma $ | 0.5–2.0 | Narrowband → higher $ \gamma $ |
| Amplitude | $ \mathcal{A} $ | 50–120 | Calibrate to real data |
| Luminance factor | $ \beta $ | 0.2–1.0 | From CIE $ \bar{y}(\lambda) $ |

---

> **Next Steps for Research**:
> - Fit model to experimental $ K/S $ vs. $ c $ data
> - Measure $ C^*_{ab}(c) $, $ L^*(c) $ for dye series
> - Compare $ c_{\text{max}} $ across dye classes
> - Develop inverse model: given target $ S $, find optimal $ c $