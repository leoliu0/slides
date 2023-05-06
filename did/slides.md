---
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
# background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
theme: apple-basic
canvasWidth: 850
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
# css: unocss
---

<br>
<br>
<br>

# How much should we trust staggered 
# Difference-in-Difference Estimate?
<br>

Andrew C. Baker , David F. Larcker , Charles C.Y. Wang 

---

## How Much Should We Trust Differences-in-Differences Estimates?

<br>
 Marianne Bertrand, Esther Duflo, Sendhil Mullainathan
<br>
<br>

- Basic setup:

  $Y_{it} = \beta_1 D_i + \beta_2Post_t + \beta_3 (D_i \times Post_t)  + \epsilon_{ist}$

- Bertrand et al. (Panel with treatment at state level)

  $Y_{ist} = A_s + B_t + \beta T_{st} + \epsilon_{ist}$

where $A_s$ is State FE and $B_t$ is year FE 

- With two-way fixed effect (TWFE)

  $Y_{it} = \alpha_i +\lambda_t + \beta T_{it} + \epsilon_{it}$

  $\alpha_i$ is firm FE and $\lambda_t$ is year FE 

---

## Staggered Difference-in-Difference

- Difference-in-Differences with Variation in Treatment Timing (by Goodman-Bacon, JE)
- The paper shows that the calculation of $\beta$ is a "weighted average of all possible two-group/two-period DiD estimators"

<img src="/f1.png" style="height:70%" />

---

## Pairwise Group Comparison

<img src="/f2.png" style="height:100%" />
---

## The problematic pair
<img src="/f3.png" style="height:100%" />
<SlideCurrentNo /> / <SlidesTotal />

---


