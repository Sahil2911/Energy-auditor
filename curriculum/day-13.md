# Day 13 — Cement, Steel, Textile, Sugar and Financial Analysis

**Time: 3.5–4 hours. Book-4 Ch 13 (cement), 12 (steel), 15 (textile), 10 (financial).**

Rungs 134–153 (plus 137B). These are the **4th-edition chapters** — they did not exist in the
3rd edition, and they are exactly where recent papers have moved. Cement appears
in **7 of 8** machine-readable sittings, and in the last four sittings it has been
a 20-mark N-4 option every time.

> **Tab these now.** Guidebook pages from `reference/guidebook-index.md`:
> Ch 10 Financial p149, Ch 12 Steel p195, Ch 13 Cement p215, Ch 15 Textile p265.
> Label them **FI, ST, CE, TX**.

> **Prerequisite check — data-item level.** Every quantity in today's timed
> question (24th N-4(D), DRI steel) has a taught use: specific coal and power
> consumption → Day 6 SEC; captive plant efficiency → Day 12 `HR = 860/η`; yield
> → Rung 143 below. Nothing in it is unreachable.
>
> One warning about the *drill* questions. The 24th N-4(C) cement WHRB question
> supplies three gas temperatures (325 °C, 310 °C, 160 °C) that its own model
> answer never uses — it hands you the heat availability in kCal/kg of clinker
> directly. **The "unused data is the tell" rule is a check on my curriculum, not
> a guarantee about BEE's papers.** Real papers occasionally over-supply. If you
> have used every *named quantity the question asks about* and something is left
> over, it is context, not a missed step. Say so in one line and move on.

---

# Part 1 — Cement

## Rung 134 — What is physically happening in a cement plant

Cement is made by cooking ground limestone and clay until they chemically
rearrange into new minerals. The plant is a conveyor with a furnace in it:

```
  limestone + clay + iron ore
        │  (crush, grind, blend)
        ▼
   RAW MEAL  ─► PREHEATER ─► CALCINER ─► ROTARY KILN ─► CLINKER COOLER ─► clinker
                 ~900 °C      ~900 °C      ~1450 °C        ~100 °C
                   ▲             ▲            ▲               │
                   └── hot gas ──┴── fuel ────┘         cooling air
                                                              │
   clinker + ~5% gypsum (+ fly ash / slag) ─► CEMENT MILL ─► CEMENT
```

Three energy facts fall straight out of that picture.

**1. The kiln is the heat.** Everything upstream of the cooler is fired. A modern
dry-process kiln uses **700–800 kCal per kg of clinker**; older wet kilns used
1400. That is the number a cement auditor lives by.

**2. The mills are the electricity.** Raw meal grinding, coal grinding and cement
grinding are motors — typically **65–80 kWh per tonne of cement**, of which
grinding is over half. That is why the 20th sitting's question is a *vertical
roller mill* heat and mass balance, not a kiln one.

**3. The two products are not the same substance.** The kiln makes **clinker**.
The cement mill makes **cement** by grinding clinker with gypsum and, in blended
cements, fly ash or slag. One tonne of clinker becomes **more than** one tonne of
cement.

**That third fact is where marks are lost.** Thermal energy is quoted per kg of
**clinker**. Electrical energy is quoted per tonne of **cement**. Mix the two
denominators and every number is wrong. Write the denominator down before you
divide — every time.

---

## Rung 135 — Why cement costs so much heat: the calcination reaction

Limestone is calcium carbonate. To make cement you must first tear the CO₂ off it:

```
    CaCO₃  ──►  CaO  +  CO₂↑          ΔH = +178 kJ per mol
    (100 g)    (56 g)  (44 g)
```

That is **endothermic** — it absorbs heat. Put it per kilogram of the CaO you end
up with:

```
    178 kJ/mol ÷ 0.05608 kg/mol = 3174 kJ per kg of CaO
                                = 3174 / 4.1868
                                ≈ 758 kCal per kg of CaO
```

Hold that number: **~758 kCal/kg of CaO**. You are about to meet it again wearing
a disguise.

Two more things happen in the kiln, and they run the other way:

- The clay minerals give up their combined water (endothermic, smaller).
- Above ~1250 °C the CaO recombines with the silica and alumina to form the
  clinker minerals — **C₃S, C₂S, C₃A, C₄AF**. Compound formation *releases* heat
  (exothermic).

So the net heat the chemistry demands is:

```
    heat to break the carbonates and clays   (positive, large)
  − heat released forming the clinker minerals (negative, smaller)
  ─────────────────────────────────────────────
  = NET HEAT OF FORMATION OF CLINKER          ≈ 380–420 kCal/kg
```

This is a **theoretical minimum**. No kiln design, no fuel, no recuperation can go
below it, because it is chemistry, not engineering. Everything a real kiln burns
above ~420 kCal/kg is loss.

---

## Rung 136 — The heat-of-formation formula, and why it is not magic

BEE gives you this (Zur Strassen's formula), and most candidates memorise it:

```
    ΔH_R = 2.22·Al₂O₃ + 6.48·MgO + 7.646·CaO − 5.116·SiO₂ − 0.59·Fe₂O₃
```

where each symbol is the **percentage** of that oxide in the clinker, on a
**loss-free (ignited) basis**, and ΔH_R comes out in **kCal per kg of clinker**.

Do not memorise it. Read it.

Each coefficient is "kCal per 1% of that oxide". Multiply by 100 and you get
**kCal per kg of pure oxide** — and every one of them is a reaction you now
recognise:

| Term | ×100 → kCal/kg of oxide | What that heat actually is | Sign |
|---|---|---|---|
| **7.646 · CaO** | **765** | Decomposing CaCO₃ (we derived **758**) | **+** endothermic |
| 6.48 · MgO | 648 | Decomposing MgCO₃ (theory ~700; magnesia arrives partly as dolomite) | **+** |
| 2.22 · Al₂O₃ | 222 | Driving combined water out of the clay | **+** |
| −5.116 · SiO₂ | −512 | Heat **released** forming calcium silicates C₃S/C₂S | **−** exothermic |
| −0.59 · Fe₂O₃ | −59 | Heat **released** forming C₄AF | **−** |

**765 against the 758 we computed from ΔH = 178 kJ/mol is a 1% match.** The
formula is not a correlation someone fitted. It is Rung 135's chemistry with the
oxide percentages substituted in.

Three consequences worth more than the formula itself:

- **CaO dominates.** It is the biggest coefficient *and* the biggest percentage
  (~63–65%). A clinker with less lime needs less heat.
- **Silica is your friend, thermally.** Its term is negative. More silica, less
  net heat.
- So a **low-heat clinker** — more silica, less lime — genuinely has a lower heat
  of formation. That is not a marketing name; you can compute it. The 23rd
  sitting asks you to, and the answer is 413 vs 73 kCal/kg.

> **Sign discipline.** Al₂O₃ and MgO are **plus**, SiO₂ and Fe₂O₃ are **minus**.
> The single most common error on this question is a lost minus sign. Write the
> five terms in a column with their signs *before* you touch the calculator.

**Self-check.** For clinker of SiO₂ 22, Fe₂O₃ 6, Al₂O₃ 5, CaO 64, MgO 1:

<details><summary>Answer</summary>

```
  + 2.22 × 5    = +11.10
  + 6.48 × 1    =  +6.48
  + 7.646 × 64  = +489.34
  − 5.116 × 22  = −112.55
  − 0.59 × 6    =   −3.54
  ────────────────────────
  ΔH_R          = 390.8 kCal/kg of clinker      ✓ inside the 380–420 band
```
</details>

---

## Rung 137 — The kiln heat balance, and what it is really for

A kiln heat balance is the same statement you wrote for a boiler on Day 3:

```
    HEAT IN  =  HEAT OUT
```

only the list of terms is different, because a kiln makes a *chemical* product,
not steam.

```
  IN                                   OUT
  ───────────────────────────────      ────────────────────────────────────
  fuel combustion  m_f × GCV           heat of formation of clinker   ΔH_R
  sensible heat of raw meal            sensible heat in preheater exit gas
  sensible heat of combustion air      sensible heat in the discharged clinker
  sensible heat of cooler air          sensible heat in cooler exhaust air
                                       moisture evaporation
                                       radiation & convection from the shell
```

**The heat of formation sits on the OUT side.** That trips people. It is not a
loss — it is the useful output, the cement-plant equivalent of the heat that went
into your steam on Day 3. Everything *else* on the right is loss.

Now look at what that lets you do. If a question gives you every out-term and every
in-term except the fuel, the balance has exactly one unknown:

```
    m_f × GCV + (other heat in) = ΔH_R + (all heat out)

                        ΔH_R + Σ(losses) − Σ(other heat in)
    ⟹  m_f  =  ─────────────────────────────────────────────
                                   GCV
```

That is **specific fuel consumption, kg of coal per kg of clinker** — the single
most-asked cement calculation. The 16th sitting's N-4(D) is exactly this, with the
loss terms hidden inside pitot-tube gas flow measurements.

> **The one-mark tell.** In a cement rotary kiln, the largest heat loss is the
> **preheater exit gas**, not the clinker discharge. The 25th sitting asks this as
> a True/False (statement: "highest heat loss occurs through clinker discharge" →
> **False**). The clinker leaves the cooler at ~100 °C with a specific heat of
> ~0.19; the preheater gas leaves at ~320 °C in far greater mass. Gas wins.

---

## Rung 137B — Measuring the loss streams: a pitot tube in a hot duct

Rung 137 needs the mass flow of the preheater gas and the cooler exhaust. Nobody
puts a flow meter in a 8.5 m² kiln duct. You traverse it with a **pitot tube** —
Day 9 Rung 85 — but with two corrections that Day 9 did not need, because Day 9's
air was cold and near atmospheric.

**Correction 1 — the gas density is not 1.2.**

The pitot reading gives velocity through `v = √(2gΔp/ρ)`, so ρ must be the density
*in the duct*, at duct pressure and duct temperature. Start from the quoted density
at NTP and apply the gas law twice:

```
                      P_barometric + P_static        273
    ρ_duct = ρ_NTP × ───────────────────────── × ───────────
                            10 334                 273 + t
```

- `10 334` mmWC is one standard atmosphere. It is the *reference* the quoted NTP
  density belongs to — do not replace it with the site's barometric pressure.
- **`P_static` is signed, and in these ducts it is negative.** A preheater ID fan
  and a cooler exhaust fan both *pull*. A "static pressure of 640 mmWC" in a
  preheater duct is 640 mmWC of **draft** — the gas is at 10 329 − 640, not
  10 329 + 640. Get this sign wrong and the density is out by 13%, the velocity by
  6%, and every downstream number with it.

> **How to tell.** Ask which side of the fan you are on. Upstream of a fan
> (suction) → negative. Downstream (discharge) → positive. Furnace, kiln,
> preheater and cooler ducts feeding an ID fan are all suction.

**Correction 2 — the pitot constant.**

A real pitot tube does not recover the full velocity head. Its calibration
constant `C_p` (0.80–0.85 for an S-type probe) multiplies the velocity:

```
    v = C_p × √(2 g Δp_dynamic / ρ_duct)          m/s,  Δp in mmWC
```

Then the chain is straightforward, and each step has an honest unit:

```
    V̇  = v × A                    m³/s      →  × 3600  →  m³/h
    ṁ  = V̇ × ρ_duct               kg/h
    ṁ per kg of clinker = ṁ / clinker production rate in kg/h
    Q  = (kg gas/kg clinker) × Cp × (t_gas − t_reference)     kCal/kg clinker
```

**That last step is the one that makes the heat balance work.** Every term in a
kiln balance is *per kg of clinker*, so the measured gas flow must be divided by
the clinker rate before it can join the balance. Divide by the wrong rate — TPD
instead of kg/h — and the loss comes out 24 000 times wrong.

**Worked, 16th sitting N-4(D)** — preheater duct, ρ_NTP 1.436, barometric 10 329,
static 640 (draft), dynamic 15.8, t 320 °C, area 8.5 m², C_p 0.85, clinker
4127 TPD:

```
  ρ_duct = 1.436 × (10 329 − 640)/10 334 × 273/(273 + 320)   = 0.6198 kg/m³
  v      = 0.85 × √(2 × 9.81 × 15.8 / 0.6198)                = 19.0 m/s
  V̇      = 19.0 × 8.5 = 161.5 m³/s                            = 581 400 m³/h
  ṁ      = 581 400 × 0.6198                                   = 360 351 kg/h

  clinker = 4127 × 1000/24                                    = 171 958 kg/h
  gas per kg clinker = 360 351/171 958                        = 2.095 kg/kg

  Q_preheater = 2.095 × 0.247 × (320 − 20)     = 155.2 kCal/kg of clinker
```

**Sanity:** 155 kCal/kg against a total fuel input of ~750 is **21% of the fuel
leaving through the preheater stack** — which is exactly why Rung 137 said the
preheater gas is the biggest kiln loss, and exactly why WHR boilers get put there.

---

## Rung 138 — SEEC and STEC: two specific energies, two denominators

An auditor reports cement plant performance as two numbers, and they are
deliberately not combined:

```
    SEEC  =  net electricity for cement production  ÷  tonnes of CEMENT
             (kWh / tonne of cement)          typical 65–80

    STEC  =  total kiln fuel heat  ÷  kg of CLINKER
             (kCal / kg of clinker)           typical 700–800
```

**Why two, and why not add them up?** Because they answer different questions.
STEC tells you how well the *kiln* runs; SEEC tells you how well the *mills and
everything else* run. A plant that raises its blend ratio (more fly ash, less
clinker per tonne of cement) improves SEEC and leaves STEC untouched. Adding them
via a heat rate would hide that.

**Computing SEEC — the accounting is the question.** All electricity into the
plant, minus everything that did not go into making cement:

```
    Net kWh = (CPP generation + WHR generation + grid import)
              − export to grid − colony & township − any other non-process use
```

Then divide by **cement**, not clinker:

```
    cement tonnes = clinker tonnes × (clinker-to-cement ratio)
```

> **Read the ratio's direction carefully.** BEE's papers write "clinker-to-cement
> ratio 1.4" and their model answer computes `cement = clinker × 1.4`. Literally,
> a *clinker-to-cement* ratio of 1.4 would mean 1.4 kg clinker per kg cement,
> which is impossible. The intended meaning is the **cement-to-clinker factor**:
> 1 kg of clinker yields 1.4 kg of cement (i.e. ~71% clinker in the cement).
> **Follow the physics, not the label** — cement always exceeds clinker. If your
> cement tonnage comes out below your clinker tonnage, you have inverted it.

**Computing STEC.** Add up every fuel's mass × GCV and divide by **kg of clinker**:

```
    STEC = Σ(mass_i × GCV_i) / clinker in kg
```

> **The PAT convention.** Strictly, fuel burnt in the captive power plant is
> *electrical* energy, not kiln heat, so you might expect to deduct it. BEE's
> model answers (25th N-4(A)) **do not deduct it** — they put the whole fuel bill
> over the clinker. Follow the model answer's convention in the exam and **write
> one line saying which convention you used.** An examiner reading "as per PAT
> convention, no CPP deduction applied" gives the mark either way.

---

## Rung 139 — Fuel blending: the one-line linear mix

Cement plants burn whatever is cheapest — Indian coal, imported coal, pet coke,
biomass, tyre chips — usually blended. Blending arithmetic is one idea:

**Heat is conserved when you mix fuels.** Blend x kg of fuel A with (1−x) kg of
fuel B, per kg of blend:

```
    GCV_blend = x·GCV_A + (1 − x)·GCV_B
```

Solve for x:

```
              GCV_B − GCV_blend
    x  =  ─────────────────────────
              GCV_B − GCV_A
```

You do not need to memorise the rearrangement — write the mixing line and solve.

**Worked, 25th sitting.** Indian coal 4500, imported 7200, blend wanted 6000:

```
    6000 = 4500x + 7200(1 − x)
    6000 = 7200 − 2700x
    2700x = 1200      →  x = 0.444
```

**Answer the question asked**: "the coal blending ratio by weight" is
**Indian : Imported = 44 : 56**, not "x = 0.444".

> **By weight, not by volume.** This mixing line is only linear because GCV is per
> kg and the fractions are mass fractions. A volume basis would need densities.

---

## Rung 140 — Waste heat recovery in cement: why it works so well

Two gas streams leave a cement plant hot and clean-ish:

| Stream | Temperature | Why it is hot |
|---|---|---|
| **Preheater exit gas** | 300–350 °C | Has already given up most of its heat to the raw meal, but not all |
| **Clinker cooler exhaust** | 250–320 °C | Cooling air that took heat *out of* the clinker |

Both are pure waste. Put a **WHRB** in each, raise steam, run a turbine, and you
generate power with **no additional fuel at all**. This is why almost every modern
Indian cement plant has a 6–12 MW WHR set — the 25th sitting's plant has 9 MW.

The calculation chain is Day 6 (waste heat) into Day 4 (turbine):

```
  1.  clinker rate       = feed rate × clinker yield          (t/h)
  2.  heat available     = (kCal/kg of clinker) × clinker rate   (kCal/h)
  3.  heat recovered     = heat available × WHRB effectiveness
  4.  steam raised       = heat recovered / (h_steam − h_feedwater)   (kg/h)
  5.  power              = steam × Δh × η_cycle × η_gearbox × η_alt / 860   (kW)
```

Step 5 is the Day 4 formula with the extra mechanical efficiencies stacked on.
`/860` converts kCal/h to kW because **1 kWh = 860 kCal**.

**Worked, 24th sitting N-4(C).** 7200 TPD raw meal, clinker 62% of feed:

```
  clinker  = 7200 × 0.62 / 24                     = 186 t/h
  preheater heat = 152 × 186 000                  = 28 272 000 kCal/h
  cooler heat    = 120 × 186 000                  = 22 320 000 kCal/h
  steam (PH)     = 28 272 000 × 0.75 / (815 − 95) = 29 450 kg/h
  steam (cooler) = 22 320 000 × 0.75 / (815 − 95) = 23 250 kg/h
  total steam                                     = 52.7 t/h
  power = 52 700 × 720 × 0.36 × 0.95 × 0.96 / 860 / 1000 = 14.49 MW
```

Sanity: 14.5 MW from a 7200 TPD kiln — about 2 MW per 1000 TPD, which is the
industry rule of thumb. It checks.

---

## Worked example — 23rd sitting N-4(C), ordinary vs low-heat clinker

**Do this one with me, then redo it cold tomorrow.** It is the cleanest heat-of-
formation-into-heat-balance question BEE has set.

Given (loss-free basis, %):

| | SiO₂ | Fe₂O₃ | Al₂O₃ | CaO | MgO |
|---|---|---|---|---|---|
| Ordinary | 20 | 7 | 7 | 65 | 1 |
| Low heat | 44 | 15 | 1 | 39 | 1 |

Heat output **excluding** formation: ordinary `360 + 6.7·m_fuel`, low heat
`400 + 7.1·m_fuel`. Total heat input for both: `27 + 6000·m_fuel`. Coal ₹6200/t.

**Step 1 — heat of formation.** Five signed terms each:

```
  Ordinary:  2.22(7) + 6.48(1) + 7.646(65) − 5.116(20) − 0.59(7)
           =  15.54  +  6.48   + 496.99    − 102.32    −  4.13   = 412.56
  Low heat:  2.22(1) + 6.48(1) + 7.646(39) − 5.116(44) − 0.59(15)
           =   2.22  +  6.48   + 298.19    − 225.10    −  8.85   =  72.94
```

Already the physics reads: the low-heat clinker has **one-fifth** the formation
heat, because it swapped lime for silica — a positive term for a negative one.

**Step 2 — total heat output.** Formation is an OUT term (Rung 137), so add it:

```
  Ordinary:  772.56 + 6.7·m_fuel        Low heat:  472.94 + 7.1·m_fuel
```

**Step 3 — balance.** Set OUT = IN and solve the single unknown:

```
  Ordinary:   772.56 + 6.7 m = 27 + 6000 m
              745.56 = 5993.3 m       →  m = 0.1244 kg coal / kg clinker
  Low heat:   472.94 + 7.1 m = 27 + 6000 m
              445.94 = 5992.9 m       →  m = 0.0744 kg coal / kg clinker
```

*(The `6.7 m` term is the sensible heat the fuel's own ash and gas carry away —
tiny beside 6000 m, but keep it; the marks are for the balance, not the size.)*

**Step 4 — which consumes more?** Ordinary, 0.1244 against 0.0744 kg/kg.

**Step 5 — cost difference per tonne.** 0.1244 kg/kg = 0.1244 t/t, so:

```
  Ordinary:  0.1244 × 6200 = ₹771.28 per tonne of clinker
  Low heat:  0.0744 × 6200 = ₹461.28 per tonne of clinker
  Difference                = ₹310 per tonne of clinker
```

**State the answer the question asked for:** the *difference* is **₹310 per tonne
of clinker**, favouring low-heat clinker. Not two costs — the difference.

---

# Part 2 — Steel

## Rung 141 — Two routes, and why the paper only asks about one

| Route | How iron is made | Energy character |
|---|---|---|
| **Integrated (BF-BOF)** | Blast furnace: coke reduces iron ore, everything molten | Huge, coal-dominated, ~6 Gcal/t crude steel |
| **DRI / sponge iron (EAF or IF)** | Coal or gas reduces ore in the **solid** state, then melted electrically | Smaller units, **electricity-dominated melting** |

India has more DRI capacity than anywhere else, DRI plants are the size an energy
auditor actually audits, and their energy splits cleanly into a coal half and an
electricity half. **So the papers ask about DRI.** The 24th sitting's N-4(D) is a
DRI plant; the 25th sitting's True/False is about integrated plants (statement:
"all the rolling mills consume more energy than iron making" → **False** — iron
making is by far the largest block).

The DRI chain, and it matters that it is a chain:

```
   iron ore + coal  ──► DRI KILN ──► SPONGE IRON ──► SMS (induction/arc furnace) ──► INGOTS
                       coal + power                    power                          product
                                                          │
                                              CAPTIVE POWER PLANT ──► coal
```

---

## Rung 142 — Putting coal and electricity on one scale

A DRI plant spends coal in the kiln and electricity in the melting shop. To report
one number you must convert electricity into heat — and **not with 860**.

860 kCal/kWh is the heat *content* of a kWh. But the plant did not receive a kWh
for 860 kCal; its captive power station burnt coal at maybe 26% efficiency to make
it. The honest conversion is the **plant heat rate** from Day 12:

```
    HR = 860 / η_CPP
```

At η = 26.06%: `HR = 860/0.2606 = 3300 kCal/kWh`. Nearly **four times** 860. Use
860 here and you will understate the plant's energy by a factor of four.

> **When 860 and when 860/η?** 860 is a *unit conversion* — use it whenever you
> are converting an energy quantity between kWh and kCal (turbine output, WHR
> potential). `860/η` is a *sourcing* question — use it whenever you are asking
> "what primary fuel did this kWh cost?". SEC and PAT calculations are always the
> second kind.

So the specific energy of the DRI stage, per tonne of sponge iron:

```
    SEC_DRI = (specific coal, kg/t × GCV, kCal/kg)  +  (specific power, kWh/t × HR)
```

---

## Rung 143 — The yield chain: why you cannot just add the SECs

Here is the idea that carries the marks, and it is not about steel.

The plant's **finished product is ingots**, not sponge iron. And the melting shop
has a **yield** — 85% means 100 t of sponge iron becomes 85 t of ingots; the other
15% is slag, scale and losses.

So all the energy spent making 100 t of sponge iron has to be carried by only 85 t
of ingots. **The denominator shrinks, so specific energy grows.**

```
                 (energy for ALL the sponge iron)  +  (energy to melt it)
    SEC_plant  = ────────────────────────────────────────────────────────
                              tonnes of INGOTS produced
```

Never `SEC_DRI + SEC_SMS`. That would silently assume 100% yield.

The mechanics, in the order that keeps you out of trouble:

```
  1.  daily sponge iron   = capacity × utilisation
  2.  daily ingots        = sponge iron × yield
  3.  energy for DRI/day  = sponge iron tonnes × SEC_DRI          (Mcal)
  4.  energy for SMS/day  = ingot tonnes × SEC_SMS_kWh × HR       (Mcal)
  5.  SEC_plant           = (3 + 4) ÷ ingot tonnes                (Mcal/t)
```

**Improving yield is an energy saving**, even if not one gram less coal is burnt —
because the same energy now carries more product. That is worth a sentence in any
answer; it is the kind of interpretation mark BEE hands out.

---

## Rung 144 — Timed question preview: what the DRI question wants

The 24th N-4(D) gives a base year and an assessment year and asks for the plant SEC
in **million kCal per tonne of finished product** for each, then the **reduction in
coal per day**.

Part 3 catches people. "Coal consumption considering both DRI and captive power
plant" means **two** coal streams:

```
  coal to DRI  = sponge iron tonnes × specific coal consumption (t/t)
  coal to CPP  = total kWh × HR ÷ GCV        ← the electricity became coal too
  total coal   = the sum
```

and the total kWh is the DRI kiln's *plus* the melting shop's.

You will work this one under time in Block C. Do not read the model answer first.

---

# Part 3 — Textile

## Rung 145 — Where a textile mill spends energy

Spinning is electrical (motors, humidification). **Wet processing is thermal**, and
it is the wet processing the paper asks about, because that is where an auditor
finds savings.

```
   grey fabric ─► SCOURING/BLEACHING ─► DYEING ─► WASHING ─► DRYING (stenter) ─► finished
                   hot water, steam     steam    hot water   hot air from thermic fluid
```

Three assessment topics, three rungs: **liquor ratio**, **thermic fluid heaters**,
**stenter drying efficiency**.

---

## Rung 146 — Liquor ratio: the mass of water you heat per kg of cloth

Dyeing happens in a bath. **Liquor ratio** is how many kilograms of liquid are in
the bath per kilogram of fabric — quoted as `1 : L`.

It matters because **you heat the whole bath, not the cloth.** At a liquor ratio of
1:10 you heat ten times the mass of water you have fabric. Halve the liquor ratio
and you halve the heating energy, the chemicals, and the effluent. It is the single
biggest lever in wet processing.

The energy statement is just sensible heat, the Day 5 workhorse:

```
    Q = m_liquor × Cp × ΔT = (m_fabric × L) × 1 × (T_final − T_initial)
```

with Cp = 1 kCal/kg°C because the liquor is essentially water.

If the bath is heated by steam, that same Q came from condensing steam:

```
    Q = m_steam × h_steam
```

Set the two equal and **L is the only unknown** — that is the whole question.

**Worked, 23rd sitting N-4(D)(A).** 150 kg fabric, specific steam consumption
0.65 kg/kg, steam enthalpy 660 kCal/kg, 25 → 90 °C, 15% margin for losses:

```
  steam per batch = 150 × 0.65               = 97.5 kg
  heat supplied   = 97.5 × 660               = 64 350 kCal

  heat used       = 150 × L × 1.15 × (90 − 25) = 64 350
                    150 × L × 1.15 × 65        = 64 350
                            11 212.5 × L       = 64 350
  L = 5.74
```

**State it the way the industry does: the liquor ratio is 1 : 5.74.**

> **Where the 1.15 goes.** "Allowing 15% margin for losses" means the steam had to
> deliver 15% more than the bath strictly needs, so 1.15 sits on the *demand* side
> — in the denominator when you solve for L. Put it in the numerator and you get
> 7.6, which is a plausible-looking wrong answer. Ask yourself: do losses make the
> computed bath *bigger* or *smaller*? Smaller — some of that steam was wasted.

---

## Rung 147 — Thermic fluid heaters: heat without pressure

To hold a process at 280 °C with steam you would need saturated steam at ~65 bar —
a pressure vessel, a boiler licence, an attendant. Instead, textile and chemical
plants circulate a **thermic fluid** (a synthetic oil) in a closed loop, heated in a
fired heater. It reaches 300 °C at **near atmospheric pressure**, because you never
boil it.

That single design choice defines the arithmetic. **There is no phase change**, so
there is no latent heat and no enthalpy table. The heat carried is purely sensible:

```
    Q = m × Cp × (T_supply − T_return)
```

and since circulation is measured as a volume flow:

```
    Q = V × ρ × Cp × ΔT           V in m³/h, ρ in kg/m³
```

Two derived quantities the papers ask for:

```
    Heat duty      = rated capacity × % loading
    Efficiency     = heat duty  /  (fuel rate × GCV)
```

Note the efficiency is a **direct method** — output over input, exactly Day 1.

**Worked, 23rd N-4(D)(B).** 20 lakh kCal/h heater at 45% loading, 280 → 260 °C,
Cp 0.55, ρ 840, coal 400 kg/h at 4100 kCal/kg:

```
  1.  duty          = 2 000 000 × 0.45                = 900 000 kCal/h
  2.  900 000       = V × 840 × 0.55 × (280 − 260)
                    = V × 9240
      circulation V = 97.4 m³/h
  3.  efficiency    = 900 000 / (400 × 4100) = 900 000/1 640 000 = 54.87 %
  4.  at 62 %, same duty:  new coal = 0.5487 × 400 / 0.62 = 354 kg/h
      saving = (400 − 354) × 6000 / 1000 = 276 tonnes per year
```

> **Step 4 is a reciprocal.** Same heat duty, better efficiency → **less** fuel, so
> the efficiency ratio goes `old/new` on the fuel. If your new coal figure came out
> above 400, you inverted it. This is the seventh member of the reciprocal family
> in `reference/reciprocal-traps.md` — add it.

---

## Rung 148 — Stenter drying: work on the bone-dry basis

A stenter is a hot-air dryer that also holds the fabric to width. Assessing it is a
**moisture balance**, and there is exactly one trick: **percentages at inlet and
outlet are taken on different totals**, so you cannot subtract them.

The fixed quantity through the machine is the **bone-dry cloth**. Anchor on that.

```
  1.  bone-dry cloth   = wet feed × (1 − inlet moisture fraction)
  2.  outlet cloth     = bone-dry / (1 − outlet moisture fraction)
  3.  moisture out     = outlet cloth − bone-dry
  4.  moisture in      = wet feed − bone-dry
  5.  water evaporated = moisture in − moisture out
```

Step 2 is the one that gets skipped. Outlet cloth at "5% moisture" means moisture
is 5% *of the outlet cloth*, so bone-dry is 95% of it — divide, do not multiply.

Then the heat: the water must be **warmed to the exit temperature and then boiled**.

```
    Q = m_evap × Cp × (T_out − T_in)  +  m_evap × latent heat
      = m_evap × [1 × ΔT + 540]
```

540 kCal/kg is the latent heat of vaporisation of water — the same 540 you used in
the boiler heat balance on Day 3 and the cooling tower on Day 10.

Finally, drying efficiency is output over input, direct method again:

```
    η = heat that actually evaporated water / heat supplied by the fuel
```

**Worked, 23rd N-4(D)(C).** 1000 kg/h wet cloth at 60% moisture in, 5% out, cloth
30 → 80 °C, firewood 320 kg/h at 3500 kCal/kg through a 65% efficient heater:

```
  bone dry      = 1000 × 0.40                = 400 kg/h
  outlet cloth  = 400 / 0.95                 = 421 kg/h
  moisture out  = 421 − 400                  = 21 kg/h
  moisture in   = 1000 − 400                 = 600 kg/h
  evaporated    = 600 − 21                   = 579 kg/h

  heat needed   = 579 × [1 × (80 − 30) + 540]
                = 579 × 590                  = 341 610 kCal/h
  heat supplied = 320 × 3500 × 0.65          = 728 000 kCal/h

  drying efficiency = 341 610 / 728 000      = 46.9 %
```

Sanity: stenters are 45–55% efficient — most of the loss is hot exhaust air that
gets dumped. Which is why **stenter exhaust heat recovery** is the standard
recommendation, and worth writing as your interpretation line.

---

# Part 4 — Sugar

## Rung 149 — Why a sugar mill is a cogeneration question in disguise

A sugar mill crushes cane, and cane is roughly one-third **bagasse** — the fibrous
residue left after the juice is squeezed out. Burn the bagasse and you get more
steam than the process needs. So every sugar mill is a **back-pressure
cogeneration plant** that happens to also make sugar, and in season it exports
power to the grid.

Everything you need is Day 4. Only the vocabulary is new:

| Term | Meaning |
|---|---|
| **TCD** | Tonnes of Cane crushed per Day. Divide by 24 for TPH. |
| **Bagasse GCV** | ~2270 kCal/kg — low, because it is wet (~50% moisture) |
| Specific power | ~29 kW per tonne of cane crushed per hour |
| Crushing season | ~150–180 days; the plant only exports during it |

The chain, all Day 4 formulas:

```
  plant power demand = (TCD/24) × kW per tonne
  turbine output     = steam × (h_in − h_out) / 860 × η_turbine × η_alt
  export             = gross × (1 − auxiliary %) − plant demand
  bagasse needed     = steam × (h_steam − h_feedwater) / (GCV × η_boiler)
  steam rate         = kg steam / kW           EUF = (power + process heat)/fuel
```

**Worked headline, 24th sitting N-2** (4000 TCD, 72 TPH through the turbine):

```
  plant demand   = (4000/24) × 29                        = 4833 kW
  present gross  = 72 000 × (812 − 676)/860 × 0.9 × 0.96 = 9838 kW
  present export = 0.94 × 9838 − 4833                    = 4414 kW
  proposed gross = 72 000 × (823 − 676)/860 × 0.92 × 0.96 = 10 870 kW
  proposed export= 0.94 × 10 870 − 4833                  = 5384 kW

  bagasse present = 77 000 × (815 − 95)/(2270 × 0.67)/1000 = 36.45 TPH
  bagasse proposed= 77 000 × (823 − 105)/(2270 × 0.74)/1000 = 32.91 TPH
  bagasse saving                                            =  3.54 TPH
```

**Read what happened.** Going from 42 bar to 85 bar raised export by **970 kW**
*and* cut bagasse by **3.5 TPH**. More power from less fuel, because a higher
inlet pressure gives a bigger enthalpy drop across the same back-pressure exhaust
— which is precisely the Day 4 point about topping cycles. The saved bagasse is
then sold or burnt in the off-season.

> **Boiler steam vs turbine steam.** Note 77 TPH in the bagasse line but 72 TPH in
> the turbine line — the difference is the 5 TPH going to PRDS and gland sealing.
> **Fuel is fired for what the boiler makes; power comes from what the turbine
> takes.** Using 72 in the bagasse calculation is a standard 2-mark loss.

---

# Part 5 — Financial analysis

## Rung 150 — Simple payback, and the one thing it cannot see

```
    Simple payback (years) = initial investment / annual saving
```

That is all of it, and it is what BEE asks for in nine cases out of ten — always
embedded at the end of a bigger question (23rd N-1(E), 23rd N-3(B)).

Two habits:

**Units.** If the answer comes out below one year, BEE's model answers quote
**months**. `120 000 / 345 333 = 0.347 years = 4.17 months`. Give both.

**Consistency.** Annual saving means the saving over a *year* — the number of
operating hours in a year is nearly always supplied for exactly this reason. Miss
it and your payback is out by a factor of thousands.

**What payback cannot see:** anything after the payback date, and the fact that a
rupee next year is worth less than a rupee today. A 3-year-payback project lasting
4 years and a 3-year-payback project lasting 15 years look identical to it. That
blindness is why the next three rungs exist.

---

## Rung 151 — Discounting, derived rather than asserted

Money has a time value for a concrete reason: ₹100 today can be invested. At 12%
it becomes ₹112 in a year. So ₹112 a year from now is *worth* exactly ₹100 today.

Run it forwards, then invert it:

```
    future value  F = P (1 + r)ⁿ

                       F
    present value  P = ────────
                     (1 + r)ⁿ
```

`1/(1+r)ⁿ` is the **discount factor**. That is the whole of financial analysis; the
rest is bookkeeping.

| n | Discount factor at 12% | ₹1 lakh received in year n is worth |
|---|---|---|
| 1 | 0.893 | ₹89 300 |
| 3 | 0.712 | ₹71 200 |
| 5 | 0.567 | ₹56 700 |
| 10 | 0.322 | ₹32 200 |

Read the last row: at 12%, money a decade out is worth a third of its face value.
**That is why long-payback energy projects struggle for approval** — and the
argument you make as an auditor is either that the discount rate is too high, or
that the saving grows with tariff escalation.

---

## Rung 152 — NPV, PI and IRR: three readings of the same table

Discount every cash flow to today and add them up, investment negative:

```
                  n     S_t
    NPV  =  −I + Σ   ─────────
                 t=1  (1 + r)ᵗ
```

- **NPV > 0** → the project earns more than the discount rate. **Accept.**
- **NPV = 0** → it earns exactly the discount rate.
- **NPV < 0** → reject; the money does better elsewhere.

**Profitability Index** scales NPV to the investment, so you can rank projects of
different sizes when capital is short:

```
    PI = present value of inflows / initial investment      (the standard definition)
```

> ⚠️ **BEE uses the other convention.** The 16th sitting's S-1 gives NPV ₹38 784
> and investment ₹1 50 000, and the model answer is `38 784/1 50 000 = 0.258`.
> That is **NPV/I**, not PV/I. The two differ by exactly 1:
> `PI(standard) = PI(BEE) + 1`.
>
> **In the exam, follow BEE**, and write the formula you used on the line above the
> number. The 25th sitting's True/False — "PI will be greater than 1 for projects
> with positive NPV, but its value varies with cash flow patterns" → **True** —
> is stated on the *standard* convention. Both appear in the same exam. Reading
> which one is being asked for is the skill; guessing is not.

**IRR** is the discount rate at which NPV = 0 — the return the project itself
earns. There is no closed form; you find it by trial. In an exam you will only ever
be asked to *interpret* it, or to test two given rates:

```
    Accept if IRR > the company's hurdle rate.
```

---

## Rung 153 — One financial example, all four measures

Investment ₹12,00,000. Annual saving ₹4,00,000. Life 6 years. Discount rate 12%.

**Simple payback:**
```
    12 00 000 / 4 00 000 = 3.0 years
```

**NPV.** Discount each year's ₹4 lakh and total:

| Year | Factor @12% | Present value ₹ | Cumulative PV ₹ |
|---|---|---|---|
| 1 | 0.8929 | 3 57 143 | 3 57 143 |
| 2 | 0.7972 | 3 18 878 | 6 76 020 |
| 3 | 0.7118 | 2 84 713 | 9 60 733 |
| 4 | 0.6355 | 2 54 207 | 12 14 940 |
| 5 | 0.5674 | 2 26 971 | 14 41 910 |
| 6 | 0.5066 | 2 02 653 | 16 44 563 |

```
    PV of inflows = ₹16 44 563
    NPV = 16 44 563 − 12 00 000 = ₹4 44 563     → positive, accept
```

**PI:**
```
    standard:  16 44 563 / 12 00 000 = 1.37
    BEE style:  4 44 563 / 12 00 000 = 0.37     (differ by exactly 1)
```

**Discounted payback.** Read the cumulative column: it passes ₹12 00 000 during
year 4.
```
    3 + (12 00 000 − 9 60 733)/2 54 207 = 3.94 years
```
**Simple payback said 3.0 years; discounting says 3.9.** That gap is the entire
point of the exercise, and it is the sentence to write if asked to comment.

**IRR:** by trial, NPV is +₹8 189 at 24% and −₹19 430 at 25%, so **IRR ≈ 24.3%**.
Comfortably above any normal hurdle rate — accept.

---

# Block C — Timed question (35 minutes)

**24th sitting, N-4(D)** — `papers/24-1.pdf`. Full 20 marks. Closed notes except
your guidebook. **Start the clock and record start and finish times.**

> Prerequisite check passed at data-item level: every parameter in the table has a
> taught use — specific consumptions (Rung 142), yield (Rung 143), captive plant
> efficiency (Day 12 Rung 123), GCV (Day 2).

A DRI plant, 500 t/day sponge iron capacity, running at 60%. Sponge iron goes to a
Steel Melting Shop and becomes ingots — the finished product. A captive power
station meets the electricity.

| Parameter | Unit | Base year (2022) | Assessment year (2023) |
|---|---|---|---|
| Sponge iron full capacity | t/day | 500 | 500 |
| Plant operating capacity | % | 60 | 60 |
| Specific coal consumption of DRI | t/t | 1.3 | 1.15 |
| Specific power consumption of DRI | kWh/t | 110 | 95 |
| Yield of Steel Melting Shop | % | 85 | 88 |
| SEC of Steel Melting Shop | kWh/t | 850 | 830 |
| Captive Power Station efficiency | % | 26.06 | 27.74 |
| GCV of coal | kCal/kg | 6000 | 6200 |

1. Plant Specific Energy Consumption in **million kCal per tonne of finished
   product** for the **base year**. *(8 marks)*
2. The same for the **assessment year**. *(8 marks)*
3. **Reduction in coal consumption**, considering both the DRI kiln and the captive
   power plant, in **tonnes per day** for the assessment year. *(4 marks)*

**Before you start**, write these three lines at the top of your sheet:

```
    HR = 860 / η_CPP
    finished product = INGOTS, not sponge iron
    SEC_plant = (all DRI energy + all SMS energy) ÷ ingot tonnes
```

<details><summary>Model answer — open only after you have finished and timed yourself</summary>

**Base year**

```
  HR = 860/0.2606 = 3300 kCal/kWh

  SEC of sponge iron = 1.3 × 1000 × 6000  +  110 × 3300
                     = 7 800 000 + 363 000  = 8.163 million kCal/t of SI

  sponge iron/day    = 500 × 0.60          = 300 t
  DRI energy/day     = 300 × 8.163         = 2448.9 million kCal
  ingots/day         = 300 × 0.85          = 255 t
  SEC of ingot stage = 850 × 3300          = 2.805 million kCal/t
  SMS energy/day     = 2.805 × 255         = 715.28 million kCal

  SEC_plant = (2448.9 + 715.28)/255        = 12.41 million kCal/tonne
```

**Assessment year**

```
  HR = 860/0.2774 = 3100 kCal/kWh

  SEC of sponge iron = 1.15 × 1000 × 6200 + 95 × 3100
                     = 7 130 000 + 294 500  = 7.425 million kCal/t of SI

  sponge iron/day    = 300 t               ingots/day = 300 × 0.88 = 264 t
  DRI energy/day     = 300 × 7.425         = 2227.5 million kCal
  SEC of ingot stage = 830 × 3100          = 2.573 million kCal/t
  SMS energy/day     = 2.573 × 264         = 679.27 million kCal

  SEC_plant = (2227.5 + 679.27)/264        = 11.01 million kCal/tonne
```

**Reduction in coal**

```
  Base year
    coal to DRI  = 300 × 1.3                            = 390.0 t/day
    kWh/day      = 300 × 110 + 255 × 850   = 33 000 + 216 750 = 249 750 kWh
    coal to CPP  = 249 750 × 3300 / 6000 / 1000         = 137.36 t/day
    total                                                = 527.36 t/day

  Assessment year
    coal to DRI  = 300 × 1.15                           = 345.0 t/day
    kWh/day      = 300 × 95 + 264 × 830    = 28 500 + 219 120 = 247 620 kWh
    coal to CPP  = 247 620 × 3100 / 6200 / 1000         = 123.81 t/day
    total                                                = 468.81 t/day

  REDUCTION = 527.36 − 468.81  ≈  58.6 tonnes per day
```

**Interpretation line to write:** plant SEC fell 12.41 → 11.01 Mcal/t, an **11.3%
improvement**, and note that part of it came from *yield* (85 → 88%) rather than
from burning less — the same energy now carries more finished product.

</details>

---

# Drills

Do these in this order. Times are budgets, not targets.

| # | Question | Paper | Marks | Budget |
|---|---|---|---|---|
| 67 | Cement SEEC / STEC / coal blending | 25th N-4(A) | 20 | 30 min |
| 68 | Cement WHRB power + heat of formation | 24th N-4(C) | 20 | 30 min |
| 69 | Textile — liquor ratio, thermic fluid, stenter | 23rd N-4(D) | 20 | 30 min |
| 70 | Sugar bagasse cogeneration, parts (a)–(d) only | 24th N-2 | ~12 | 20 min |
| 71 | Ordinary vs low-heat clinker, **cold redo** | 23rd N-4(C) | 20 | 25 min |

Answers for Drill 67: **SEEC 73.46 kWh/t cement, STEC 920.78 kCal/kg clinker,
blend 44:56.** Drill 68: **14.49 MW, 382 kCal/kg.** Drill 69: **1:5.74, 97.4 m³/h,
54.87%, 276 t/yr, 46.9%.** Drill 70: **4414 kW and 5384 kW export, 36.45 and 32.91
TPH bagasse, saving 3.54 TPH.**

> STEC of 920 in Drill 67 is well above the 700–800 band. That is the PAT
> convention at work — the captive plant's coal is in the numerator. **Say so in
> your answer.** An examiner wants to see that you noticed.

## Log

Record start and finish times for Block C and each drill. **Add the interpretation
sentence** on every one — Day 13's questions are all "and what does that mean"
questions, and Trend 2 in the phase-2 checkpoint says that closing sentence is
where your marks are currently leaking.

---

## Day 13 checklist

**Cement**
- [ ] Can draw the plant chain and say where heat goes and where electricity goes
- [ ] **Know that thermal is per kg CLINKER and electrical is per tonne CEMENT**
- [ ] Can explain calcination and why ~758 kCal/kg of CaO is unavoidable
- [ ] **Can read the heat-of-formation formula as chemistry**, signs and all
- [ ] Can place heat of formation on the OUT side of a kiln heat balance
- [ ] Can solve a kiln balance for specific fuel consumption
- [ ] **Can correct a pitot reading for hot-duct density**, and know the static
      pressure in a kiln duct is a **draft** (negative)
- [ ] Know every kiln balance term must be reduced to **per kg of clinker**
- [ ] Can compute SEEC with the right deductions and the right denominator
- [ ] Can do a linear GCV blend and state the answer as a ratio
- [ ] Know the preheater gas, not the clinker, is the biggest kiln loss

**Steel**
- [ ] Know the DRI chain and why the papers ask about it
- [ ] **Know when to use 860 and when to use 860/η**
- [ ] **Can run the yield chain** and never add two SECs together
- [ ] Can total coal across both the kiln and the captive plant

**Textile**
- [ ] Can compute liquor ratio from a steam balance, margin on the right side
- [ ] Know why thermic fluid exists and that its heat is purely sensible
- [ ] **Can do a stenter moisture balance on the bone-dry basis** (divide by 0.95)
- [ ] Know the 540 kCal/kg latent heat is the same one from Days 3 and 10

**Sugar**
- [ ] Know TCD → TPH and the ~29 kW/tonne figure
- [ ] **Know boiler steam ≠ turbine steam** when computing bagasse

**Financial**
- [ ] Simple payback, in months when under a year
- [ ] **Can derive the discount factor** from `F = P(1+r)ⁿ`
- [ ] Can build an NPV table and read discounted payback off the cumulative column
- [ ] **Know both PI conventions and that BEE uses NPV/I**
- [ ] Can state the accept/reject rule for NPV and IRR

**Next (Day 13B):** the sector & systems diagnostic — 40 marks, 2 long questions,
60 minutes, covering Days 11–13. Then Day 14 is Full Mock 1 under exam conditions.
