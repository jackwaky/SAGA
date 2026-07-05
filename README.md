# SAGA: Stage-wise Attention-Guided Region Sequencing for Adversarial Attacks on Large Vision-Language Models

Official repository for:

**Stage-wise Attention-Guided Region Sequencing for Adversarial Attacks on Large Vision-Language Models**

SAGA is a black-box region-sequencing framework for targeted adversarial attacks on Large Vision-Language Models (LVLMs).  
It uses cross-modal attention maps from an open-source LVLM to guide where localized perturbation updates should be applied and in what order.

> Code will be released soon.

## Overview

Targeted adversarial attacks on LVLMs aim to steer model responses toward attacker-specified target content using small image perturbations. Under an L-infinity constraint, this becomes a perturbation budget allocation problem: attack success depends not only on the optimization objective, but also on which image regions receive updates and how those regions are sequenced.

SAGA addresses this problem through **stage-wise attention-guided region sequencing**. It first extracts a fixed cross-modal attention map from an open-source LVLM, constructs an ordered sequence of high-attention hotspots, and then applies localized perturbation updates following this sequence. The target model is treated as a black box: SAGA does not require access to target-model parameters, gradients, or attention maps.

## Method

SAGA consists of three main steps:

1. **Attention Map Extraction**  
   Extract a cross-modal attention map from an open-source LVLM using the source image.

2. **Stage-wise Hotspot Construction**  
   Construct an ordered sequence of high-attention hotspot regions from the attention map.

3. **Region-Sequenced Perturbation Optimization**  
   Apply localized perturbation updates according to the hotspot sequence while keeping the adversarial image within the global L-infinity constraint.

## Main Results

SAGA is evaluated on ten LVLMs, including both closed-source and open-source models. It achieves state-of-the-art attack success rates while also improving imperceptibility compared with prior localized attack baselines.

Key findings:

- Cross-modal attention identifies adversarially sensitive image regions.
- Perturbing high-attention hotspots induces structured attention redistribution toward subsequent salient regions.
- Stage-wise region sequencing improves attack success beyond single-hotspot or stochastic localization strategies.
- SAGA improves both attack effectiveness and perturbation budget efficiency.

## Citation

```bibtex
@article{kwak2026saga,
  title={Stage-wise Attention-Guided Region Sequencing for Adversarial Attacks on Large Vision-Language Models},
  author={Kwak, Jaehyun and Cao, Nam and Cho, Boryeong and Lee, Segyu and Ahn, Sumyeong and Yun, Se-Young},
  journal={arXiv preprint},
  year={2026}
}