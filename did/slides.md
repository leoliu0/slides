---
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
# background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide

theme: apple-basic 
fonts:
    sans: "Open Sans"
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

## Differences-in-Differences 

<br>

- Basic setup:

  $Y_{it} = \beta_1 D_i + \beta_2Post_t + \beta_3 (D_i \times Post_t)  + \epsilon_{ist}$

- Bertrand, Duflo, and Mullainathan (2003) Panel with treatment at state level

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

---

## When is it a problem?
- Most of the firms are treated with significant difference in timing
- In other words, it is not too big of a worry if you have majority of firms untreated
## Sollution?
- Some form of structural models and imputation (Callaway and Sant'Anna, 2021 and Borusyak et.al, 2021) 🤮 
- Stacked DiD (Gomley and Matsa, 2011 ...) 😋

    -- Create event-specific clean datasets.
---

## Stacked DiD
The idea is to stacked treated obs. with not-treated clean controls, For each event-specific treatment group, stack it with controls that never treated before the window.

| time | t-3 | t-2 | t-1 | t | t+1 | t+2 | t+3 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Treated Firm 1 | 0 | 0 | 0 | 1 | 1 | 1 | 1 |
| Treated Firm 2 | 0 | 0 | 0 | 1 | 1 | 1 | 1 |
| Control Firm 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| Control Firm 2 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| ... | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

and you do this for every events (e.g. different states receiving law change at different time) and stack them together.

---

## Stacked DiD (continued)
The regression model becomes


  $$Y_{itg} = \alpha_{ig} +\lambda_{tg} + \beta T_{it} + \epsilon_{itg}$$

  $g$ indicates event-specific treatment and control group

  Simulation confirms the stacked DiD are effective comparing to other remedy procedures.

---

## What's trending in DiD? (JE forthcoming)
<img src="/trend.png" />
