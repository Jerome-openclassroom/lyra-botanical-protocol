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

### 🇫🇷 Français
> Voici une plante observée début avril dans une prairie calcaire de basse altitude (environ 200 m), en milieu ouvert, sur sol sec. Elle mesure environ 20 cm. Les fleurs sont de couleur jaune, disposées en solitaire. Une deuxième plante voisine, de même hauteur, est une monocotylédone à fleurs violettes.
>
> Peux-tu me donner une liste des espèces les plus probables pour chacune, par ordre de probabilité décroissante jusqu'à une probabilité totale de 95 % ? 

### 🇬🇧 English
> Here is a plant observed in early April in a low-altitude calcareous prairie (~200 m), in an open dry environment. It is around 20 cm tall. The flowers are yellow, solitary. A second nearby plant of similar height is a monocotyledon with purple flowers.
>
> Can you provide a list of the most probable species for each, in decreasing order of likelihood, up to a total of 95% cumulative probability?

---

## 🌼 Secondary Prompt – Inference of Co-occurring Species

This prompt is used **after identifying two species**, to infer which third species is ecologically most likely in the same biotope.

### 🇫🇷 Français
> En prairie calcaire de basse altitude, début avril à mi-mai, deux plantes sont déjà présentes : *Narcissus assoanus* et *Iris lutescens*. Peux-tu me donner une liste, par ordre décroissant de probabilité, d'une **troisième plante à fleur** qu'on est susceptible de trouver à proximité, jusqu'à concurrence d'une probabilité totale de 95 % ?

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

## 📁 Files to Include

- `README.md` (this file)
- `prompt_exemple.txt` (prompt template)
- `template_observation.csv` (data capture template)
- `fiche_observation_A5.pdf` (printable sheet)
- Optional: NetLogo model of Mediterranean prairie

---

## ✒️ Author

**JérômeX1** — Alta Lux Project | Post-AGI Ecological AI  
GitHub: [https://github.com/Jerome-X1](https://github.com/Jerome-X1)

> “A flower seen ten years ago can become, today, the key to a retroactive ecological protocol powered by LLMs.”

---

**Version** : 1.0 — May 2025
