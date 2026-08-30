# Paper 4 Formula Sheet

Formulas actually used in the model solutions of the past papers in `papers/`.
Grows daily as the curriculum advances. Everything here in **kCal / kg / hr / °C**
unless stated.

> This sheet **cannot go into the exam hall**. Its purpose is to tell you what to
> memorise and what to tab in the guidebooks. See `open-book-strategy.md`.

---

## 1. Boilers — Day 1–3

**Direct method**

    η = [ Q × (h_steam − h_fw) ] / [ q × GCV ] × 100

**Evaporation ratio**

    ER = Q / q                          (kg steam / kg fuel)
    ER = η × GCV / (h_steam − h_fw)
    η  = ER × (h_steam − h_fw) / GCV

`h_fw ≈ feedwater temperature in °C`

Typical ER: coal 4–6 · oil 13–15 · gas 11–13 · bagasse/husk 2–3.5

**Steam cost**

    Fuel cost per tonne steam = fuel price per tonne / ER
    Total steam cost          = fuel cost + auxiliary cost

**Indirect method**

    η = 100 − (L1 + L2 + L3 + L4 + L5 + L6 + L7)

| Loss | Name | Formula |
|---|---|---|
| L1 | Dry flue gas | m_dfg × Cp × (Tg − Ta) / GCV × 100 |
| L2 | H₂ in fuel | 9 × H₂ × [584 + Cp_s(Tg − Ta)] / GCV × 100 |
| L3 | Moisture in fuel | M × [584 + Cp_s(Tg − Ta)] / GCV × 100 |
| L4 | Moisture in air | AAS × humidity factor × Cp_s × (Tg − Ta) / GCV × 100 |
| L5 | CO / incomplete combustion | %CO × C / (%CO + %CO₂) × 5744 / GCV × 100 |
| L6 | Radiation & convection | usually given |
| L7 | Unburnt in ash | ash × GCV_ash / GCV × 100 |

`Cp flue gas = 0.24` · `Cp superheated steam = 0.45` · `584 = latent heat const.`

Blowdown loss is **not** part of the indirect method — a recurring True/False trap.

### Specific heats — do not mix these up

Two different substances, two different numbers, and they appear in adjacent
lines of the same calculation.

| Substance | Cp (kCal/kg°C) | Used in |
|---|---|---|
| **Flue gas** | **0.24** (0.23–0.29) | **L1** — dry flue gas |
| **Superheated steam / water vapour** | **0.45** (or 0.43) | **L2, L3, L4** — water losses |
| Air | 0.24 | air-side heating |
| Water (liquid) | 1.0 | feedwater, blowdown |

L1 heats *gas*. L2/L3/L4 heat *water vapour*. Using 0.45 in L1 roughly doubles the
loss and is a silent error — the answer still looks plausible.

**Which value to use:** whatever the question gives. Only if the question is
silent do you take the guidebook value. The 18th sitting gave 0.45 for vapour;
the 24th gave neither and its model answer used 0.24 for gas and 0.43 for vapour.

---

## 2. Fuels & combustion — Day 3

**Theoretical air**

    A_th = { 11.6·C + 34.8·(H₂ − O₂/8) + 4.35·S } / 100     kg air / kg fuel

(C, H₂, O₂, S as percentages from the ultimate analysis)

**Excess air from flue gas O₂**

    % EA = [ %O₂ / (21 − %O₂) ] × 100

**Actual air supplied**

    AAS = (1 + EA/100) × A_th

**Mass of dry flue gas** — two routes, both accepted:

    m_dfg = C×(44/12) + S×(64/32) + (AAS − A_th)×0.23 + AAS×0.77
    m_dfg = (AAS + 1) − 9·H₂ − M

Air is 23% O₂ and 77% N₂ by mass.

---

## 3. Cogeneration & turbines — Day 4

    Isentropic efficiency = (h_in − h_out,actual) / (h_in − h_out,isentropic)

    Turbine power (kW) = steam flow (kg/hr) × (h_in − h_out) / 860

    Heat rate = heat input (kCal/hr) / power output (kW)

    Overall cogen efficiency = (power + useful heat) / fuel energy input

`860 kCal = 1 kWh`

---

## 4. Heat exchangers — Day 5

    Q = m × Cp × ΔT                     (either side)

    LMTD = (ΔT1 − ΔT2) / ln(ΔT1 / ΔT2)

    Q = U × A × LMTD × F                (F = correction factor, 1.0 for true counterflow)

    Effectiveness ε = Q_actual / Q_max
    Q_max = (m·Cp)_min × (T_hot,in − T_cold,in)

    NTU = U·A / (m·Cp)_min

---

## 5. Furnaces & WHR — Day 6

    Furnace efficiency = heat in stock / heat in fuel × 100

    Specific fuel consumption = fuel / tonne of product

    Heat in stock = m × Cp × (T_final − T_initial)

---

## 6. Pumps — Day 8

    Hydraulic power (kW) = Q (m³/hr) × H (m) × ρ / 367

    Pump efficiency = hydraulic power / shaft power × 100

**Affinity laws** (speed N, diameter D):

    Q ∝ N        H ∝ N²        P ∝ N³

---

## 7. Fans & compressed air — Day 9

    Fan power (kW) = Q (m³/hr) × ΔP (mmWC) / (367 × 1000 × η)

Fan laws: same affinity relationships as pumps.

**Free air delivery, pump-up test**

    FAD = [ (P2 − P1) / P_atm ] × V_receiver / t          (Nm³/min)

    Specific power = kW / (m³/min)          — typical 5.5–6.5 kW per 100 cfm

---

## 8. Motors & VSD — Day 10

    Motor loading = input kW / (rated kW / η_rated) × 100

    Slip method: loading = (Ns − N_actual) / (Ns − N_rated) × 100

    Ns = 120 × f / P

    VSD saving ∝ (N1/N2)³   for centrifugal loads

---

## 9. Cooling towers — Day 10

    Range      = T_hot water − T_cold water
    Approach   = T_cold water − T_wet bulb
    Effectiveness = Range / (Range + Approach) × 100

    Evaporation loss (m³/hr) = 0.00085 × 1.8 × circulation × Range

---

## 10. HVAC & refrigeration — Day 11

    TR = m (kg/hr) × Cp × ΔT / 3024

    COP = cooling effect / work input
    kW/TR = 3.517 / COP

`1 TR = 3024 kCal/hr = 3.517 kW`

---

## 11. Power plants & PAT — Day 12

    Gross heat rate = heat input / gross generation          kCal/kWh

    Net heat rate = gross heat rate / [(100 − aux%) / 100]

    Turbine heat rate = heat in steam / power output

    e-Certificates = energy saved (kCal) / 10⁷

`1 TOE = 10⁷ kCal = 10,000 kCal/kg × 1000 kg` · `1 e-Cert = 1 TOE`

---

## 12. Financial analysis — Day 13

    Simple payback = investment / annual savings

    NPV = Σ [ CF_t / (1 + r)^t ] − initial investment

    Profitability index = PV of inflows / initial investment

IRR is the discount rate at which NPV = 0.

PI > 1 whenever NPV > 0 — but PI values do **not** rank in the same order as NPV
across different cash-flow patterns. That distinction was a True/False question
in the 25th sitting.

---

## Unit conversions — memorise

| | |
|---|---|
| 1 kWh | 860 kCal |
| 1 TR | 3024 kCal/hr = 3.517 kW |
| 1 TOE | 10⁷ kCal |
| 1 kCal | 4.187 kJ |
| 1 bar | ~1.02 kg/cm² |
| 1 MU | 10⁶ kWh |
| Air composition (mass) | 23% O₂, 77% N₂ |

---

## 13. CO₂ emissions & carbon balance — Day 2

Every carbon atom in the fuel leaves as CO₂ under complete combustion.

    C + O₂ → CO₂
    12 + 32 → 44          ⟹  1 kg C produces 44/12 = 3.67 kg CO₂

    CO₂ (kg/hr) = fuel rate (kg/hr) × carbon fraction × 3.67

Only **carbon** produces CO₂. Hydrogen → H₂O, sulphur → SO₂, nitrogen passes
through. Ignore them when asked for CO₂.

Note 3.67 = 44/12 is the same factor as the `C × (44/12)` term in the Route 1
dry flue gas mass formula. One fact, two uses.

**Green power offset**

    Green energy (kWh) = excess CO₂ (kg) / CO₂ displaced per kWh

Multiply by operating hours for a monthly figure. Sanity check: the kWh number
should be *larger* than the CO₂ number whenever the displacement factor is below
1 kg/kWh.

**Why gas beats oil on CO₂ — two compounding effects**

1. Lower carbon fraction (73% vs 84%)
2. Higher GCV (13,000 vs 10,000 kCal/kg) → fewer kg burnt for the same heat

The second is the larger effect and the one most often missed.
