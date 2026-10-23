# Local Reward Terms

This file reproduces the **Local Reward Terms** table that was moved out of the
manuscript (PI-rMAPPO / IEEE-TVT submission). The reward equations and the
definitions of the normalized error signals are unchanged in the manuscript
(Section V, "Local Reward Function"); only the weight table is released here.

All terms are normalized to remove physical units; safety terms receive the
largest weights. The weights were fixed before evaluation.

| Weight symbol | Reward term | Value | Normalized range |
|---|---|---|---|
| $w_0$ | alive reward | 0.25 | constant |
| $w_d$ | CTH spacing error | 1.25 | unbounded square |
| $w_s$ | envelope shortfall | 4.00 | nonneg. square |
| $w_t$ | TTC below 3 s | 5.00 | $[0,1]$ before square |
| $w_v$ | leader-speed tracking | 0.35 | gated, dimensionless |
| $w_a$ | acceleration effort | 0.05 | $[0,1]$ square |
| $w_j$ | jerk and comfort | 0.08 | clipped to $[0,4]$ |
| $w_g$ | acceleration amplification | 0.75 | nonneg. square |
| $w_u$ | command effort | 0.05 | $[0,1]$ square |
| $w_c$ | local collision event | 100.0 | binary |
| $w_{\mathrm{arc}}$ | ARC intervention (PI-rMAPPO only) | 0.10 | nonneg. magnitude |

**Note.** "nonneg." denotes nonnegative. Collision and short-horizon risk terms
dominate the reward magnitude, followed by tracking; effort and comfort terms
serve as regularizers. The ARC intervention weight $w_{\mathrm{arc}}=0.10$
appears only in the PI-rMAPPO reward.
