# 🥗 Algorithmic Meal & Macro Optimization Engine

An end-to-end Python engine that leverages proportional nutrient-density modeling and constraint-satisfaction algorithms to generate daily, macro-balanced, cost-controlled meal plans in seconds.

---

## 📌 Executive Summary & Problem Statement

Manually constructing a daily meal plan that simultaneously satisfies strict macronutrient splits (Protein/Carbs/Fats), financial budget caps, and structural meal guidelines (Breakfast, Lunch, Dinner) is an extraordinarily tedious process. 

Using traditional manual methods, balancing high-protein demands against strict fat caps often leads to endless trial-and-error, rounding errors, and unviable portion sizes. 

This project solves that combinatorial challenge by implementing a **heuristic search and matrix-scaling algorithm** in Python (`Pandas`, `NumPy`). The engine programmatically samples structural food sub-pools, applies global fat compression, and dynamically scales lean macronutrient vehicles across up to 5,000 iterations to output an optimized, real-world meal plan.

---

## 📊 Performance & Optimization Impact

By transitioning from manual combinatorial meal planning to an algorithmic execution model, the system achieved drastic improvements in both efficiency and computational precision:

- **Manual Baseline:** ~60 minutes (manual lookup, macro balancing, constraint checking)
- **Automated Execution:** ~0.2 seconds computational runtime (~2 mins total workflow)
- **Time Saved:** 96% efficiency improvement per planning cycle
- **Reliability:** 100% elimination of manual floating-point calculation errors

---

## 🛠️ Key Engine Architecture & Features

* **Proportional Nutrient Density Model:** Automatically identifies "clean vehicles" (foods with high target macro-to-fat ratios) to scale up protein and carb targets without breaching strict fat ceilings.
* **Global Fat Compression:** Downscales fat allocations upfront across initial selections to guarantee fat caps are respected before scaling proteins or carbohydrates.
* **Dynamic Fallback Tolerance:** Features robust error-handling logic that gracefully handles missing sub-pools (e.g., missing Breakfast Starches) by sampling from general database fallbacks without deadlocking.
* **Atwater Audit Pipeline:** Eliminates floating-point rounding drift by performing a final mathematical re-computation from raw CSV data using standard Atwater factors ($4\text{ kcal/g}$ Protein, $4\text{ kcal/g}$ Carbs, $9\text{ kcal/g}$ Fat).
* **Segmented Daily Output:** Formats solved menus cleanly into distinct Breakfast, Lunch, Dinner, and Snack blocks with exact gram weight distributions.

---

## 💻 Tech Stack & Requirements

* **Language:** Python 3.x
* **Core Libraries:** `pandas`, `numpy`
* **Data Storage:** Flat CSV (`Food_items_for_meal_engine.csv`)

---

## 🚀 Project Status & Roadmap

> ⚠️ **Project Status: Active / Work in Progress**
> Currently, the engine generates optimized, single-day meal allocations based on user target parameters (e.g., Gym Day vs. Running Day splits). Active development is underway to expand the engine from single-day generation to automated weekly menu planning.

### 🛣️ Development Roadmap
- [x] **Phase 1:** Core mathematical scaling algorithm and macro balancing engine.
- [x] **Phase 2:** Defensive data parsing, sub-pool fallbacks, and segmented meal printing.
- [ ] **Phase 3 (In Progress):** Expansion to **7-Day Weekly Generation** with dynamic recipe variety constraints (preventing duplicate consecutive meals).
- [ ] **Phase 4:** Grocery List Aggregator (consolidating weekly meal output into a single shopping list with total budget tracking).
- [ ] **Phase 5:** Simple GUI / Web interface for dynamic macro target inputs.
