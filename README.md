# Lyra Botanical Protocol – Probabilistic LLM Method for Field Plant Identification

## 🧭 Context and Scope

This protocol was designed based on real field conditions in **southern France**, in a **low-altitude calcareous prairie** during **early to mid-spring** (April–May), where associations between species are particularly structured. The method applies when one or more flowering plants are photographed and observed, and aims to identify these species or predict other likely co-occurring ones.

### 🌍 Ecological context elements
- **Location**: Low-altitude southern France (<500 m)
- **Season**: Spring (April–mid-May)
- **Soil**: Calcareous
- **Habitat**: Open dry prairie or garrigue
- **Vegetation**: Bulbous and perennial Mediterranean flora

---

## 🧠 LLM-based reasoning and suitability

This method leverages the **probabilistic structure of LLM outputs**, particularly:
- The **softmax function**, which transforms logits into a probability distribution.
- **Temperature**: tunes the randomness of output sampling.
- **Top_p (nucleus sampling)**: restricts the generation to the most probable tokens, making answers both diverse and plausible.

The prompt format is specifically designed to:
- **Match LLM inner probabilistic reasoning**
- **Elicit a cumulative ranked list** up to 95% likelihood
- **Support structured ecological inference**

---

## 🌱 Primary Prompt – Direct Identification

This prompt is used when one or two plants are visible and described (via photo + morphology). The goal is to identify the most likely species.

### 🇬🇧 English
> Here is a plant observed in early April in a low-altitude calcareous prairie (~200 m), in an open dry environment. It is around 20 cm tall. The flowers are yellow, solitary. A second nearby plant of similar height is a monocotyledon with purple flowers.
>
> Can you provide a list of the most probable species for each, in decreasing order of likelihood, up to a total of 95% cumulative probability?

---

## 🌼 Secondary Prompt – Inference of Co-occurring Species

This prompt is used **after identifying two species**, to infer which third species is ecologically most likely in the same biotope.

### 🇬🇧 English
> In a low-altitude calcareous prairie, from early April to mid-May, two flowering species are already present: *Narcissus assoanus* and *Iris lutescens*. Can you provide a ranked list of likely **third companion flowering plants**, in decreasing order of probability, up to a cumulative 95%?

---

## 📦 Output Format and Use Cases

- Results are expected in the form of:
  - One or more **ranked species lists**
  - Probabilities optionally attached (if supported)
  - Separate analysis per identified plant (primary prompt)
  - Single co-occurrence prediction (secondary prompt)
- This protocol is designed to be:
  - Interpretable by any GPT-4-class LLM
  - Extendable to JSON/CSV or NetLogo format
  - Compatible with future AI fine-tuning (e.g. Lyra Floris)

---

## 📁 File Structure (with comments)
```
plants_pictures/                        # 📸 8 field photographs of 2 flowering plant species
prompts_and_results/                   # 🧠 Prompt input and model response
├── prompt_example.txt                     # English + French example prompt used
└── GPT4_Lyra_Protocol_Results.pdf         # GPT-4o responses to the 2-prompt protocol
```

---

## 🔗 Related field project

This protocol is part of a broader AI ecology initiative.  
You can explore its **field counterpart** here:

👉 [AI_Assisted_Lake_Ecology – GitHub Repository](https://github.com/Jerome-openclassroom/AI_Assisted_Lake_Ecology) – A full-scale NPP model combining field measurements, physical modeling, and GPT-4o-assisted ecological interpretation. Includes empirical correction for realistic annual productivity in clear lakes.
- [Lyra_Leaf_SPAD_Calibration](https://github.com/Jerome-openclassroom/Lyra_Leaf_SPAD_Calibration) – SPAD sensor calibration for estimating chlorophyll density in leaves.
- [Lyra_LowCost_Soil_Leaf](https://github.com/Jerome-openclassroom/Lyra_LowCost_Soil_Leaf) – Integrated low-cost soil and leaf model for terrestrial primary productivity.
- [Leaf_Chlorose_CNN_Training](https://github.com/Jerome-openclassroom/Leaf_Chlorose_CNN_Training) – CNN-based classification of chlorotic vs. healthy leaves from scanned images.
- [Lyra_DO_Green_Mesurim](https://github.com/Jerome-openclassroom/Lyra_DO_Green_Mesurim) - A low-tech protocol combining MesurimPro and ImageJ to estimate chlorophyll levels from scanned leaves, with validation against SPAD readings and AI-assisted correlation analysis.
- [TurbiditySensor_OpenScience](https://github.com/Jerome-openclassroom/TurbiditySensor_OpenScience) - A low-cost optical turbidity sensor calibrated in JTU, illustrating an open science approach for accessible, field-based water quality monitoring.
- [LimonTree_NPP_Model](https://github.com/Jerome-openclassroom/LimonTree_NPP_Model) — Low-cost water and NPP model for a potted lemon tree.
- [Mountain_Bocage_Soil_Analysis](https://github.com/Jerome-openclassroom/Mountain_Bocage_Soil_Analysis) — Complete soil dataset for a mid-mountain bocage site (Haute-Loire, France): texture, CEC, pH, nitrates, structural stability, and Berlèse funnel microfauna extraction. Ready for AI-assisted ecological modeling.
- [Lyra_Sentinel_MODIS_Site_HauteLoire](https://github.com/Jerome-openclassroom/Lyra_Sentinel_MODIS_Site_HauteLoire) — Combined Sentinel-2 NDVI and MODIS LST for a semi-natural site in Haute-Loire (France): ROI clipping, clean map, and reproducible notebook. Ready for AI-assisted ecological modeling.
- [Eco_Profile_Saint_Julien_1060](https://github.com/Jerome-openclassroom/eco-profile-saint-julien-1060) — 1-ha eco-climatological site (1060 m, Massif Central) with 2017–2018 records and multi-disciplinary field data.

It shows real-world sampling and physical/chemical water analysis, complementing the logic of this protocol with practical data.

---

## ✒️ Author

**JérômeX1** — Alta Lux Project | Post-AGI Ecological AI  
GitHub: [https://github.com/Jerome-X1](https://github.com/Jerome-X1)

> “A flower seen ten years ago can become, today, the key to a retroactive ecological protocol powered by LLMs.”

---

**Version** : 1.0 — May 2025
