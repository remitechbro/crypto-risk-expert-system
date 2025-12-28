# crypto-risk-expert-system
Rule-based expert system for cryptocurrency investment risk analysis using rough set theory

## Overview
This project implements an **expert financial advisory system** for **cryptocurrency investment risk analysis**.  
The system applies **Rough Set Theory** to derive **interpretable decision rules** from historical cryptocurrency data and uses those rules in a **rule-based inference engine**.

The goal is to demonstrate **knowledge engineering**, **symbolic reasoning**, and **expert system design principles**, rather than predictive machine learning.

---

## Project Objectives
- Design a **decision table** with multiple conditional attributes and a single decision attribute
- Apply **Rough Set Theory** to:
  - Identify indiscernibility relations
  - Compute lower and upper approximations
  - Measure approximation quality
  - Perform attribute reduction (CORE and reducts)
- Generate **sound IF–THEN decision rules**
- Implement an **expert system** supporting:
  - Forward chaining inference
  - Backward chaining inference
- Provide **clear documentation** and reproducible analysis

---

## Data Source
- **Dataset:** *Cryptocurrency Historical Prices*
- **Source:** Kaggle  
- **Description:**  
  The dataset contains historical price and volume information (OHLC + volume) for multiple cryptocurrencies.

### Why this dataset?
- Enables computation of standard financial risk indicators
- Publicly available and reproducible
- Suitable for symbolic discretization required by rough set methods

---

## Decision Table Design
Each object (row) in the decision table represents a cryptocurrency snapshot.

### Conditional Attributes
- `Volatility_30d_Level` → {Low, Medium, High}
- `Momentum_7d_Direction` → {Down, Neutral, Up}
- `Liquidity_7d_Level` → {Low, Medium, High}

### Decision Attribute
- `Decision_Risk_Category` → {Low, Medium, High}

The final decision table contains **30 objects**, satisfying the project requirements.

---

## Rough Set Analysis (Stage 2)
The following analyses were performed on the decision table:

- **Decision classes identification**
- **Indiscernibility relations (IND(B))**
- **Equivalence class construction**
- **Lower, upper, and boundary approximations**
- **Ambiguity analysis**
- **Approximation quality metrics**
- **Attribute reduction**
  - CORE attributes identified
  - Minimal reducts computed
- **Rule generation**
  - Rules derived from **lower approximations** (certain knowledge)
  - Rules simplified using reducts

All results are fully documented in `documentation.md`.

---

## Expert System Architecture
The system follows the **classical expert system structure**:

- **Knowledge Base**
  - Stored in `rules.txt`
  - Contains simplified IF–THEN rules
- **Inference Engine**
  - Forward chaining (data-driven)
  - Backward chaining (goal-driven)
- **Explanation Capability**
  - Displays which rule(s) fired for a given input

The system uses **symbolic reasoning only**, in line with expert system theory.

---

## Repository Structure

crypto-risk-expert-system/
│
├── decision_table_crypto_risk.csv # Decision table
├── colab_all_in_one.py # Full analysis + rule generation + inference
├── rules.txt # Knowledge base (IF–THEN rules)
├── documentation.md # Complete project documentation
├── README.md # Project overview (this file)

## How to Run (Google Colab)
1. Open Google Colab
2. Upload:
   - `decision_table_crypto_risk.csv`
   - `colab_all_in_one.py`
3. Run:
   ```bash
   !python colab_all_in_one.py
Sample Usage (Conceptual)

Input facts:

Volatility_30d_Level = High
Momentum_7d_Direction = Down
Liquidity_7d_Level = Low


Output:

Decision_Risk_Category = High


The decision is produced by matching the input facts against the rule base using forward or backward chaining.

Key Outcomes

Transparent, explainable decision-making

No black-box models

Reduced attribute set without loss of classification power

Fully traceable reasoning process

Conclusion

This project demonstrates how rough set theory can be effectively used to construct a compact, interpretable expert system for financial risk analysis.
The resulting system is logically sound, explainable, and aligned with classical expert system design principles.

Author

Student Project – Expert Systems / Artificial Intelligence


