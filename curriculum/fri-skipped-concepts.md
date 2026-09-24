# The parts you skipped — one idea, four applications

**Every back half you left last night is the same idea wearing different clothes.**

> ## The idea
>
> **Whatever energy goes into a machine must come out of it.**
> **The "waste" streams are not waste — they are the answer to the question.**
>
> ```
>         ┌───────────────────────────────┐
>   IN ──►│           MACHINE             │──► the useful output
>         └───────────┬───────────────────┘
>                     │
>                     ▼
>          everything else — and it always
>          adds up to (IN − useful output)
> ```

**Opening parts ask for the useful output.** You can already do those — nine of ten
last night. **The back halves ask where the rest went**, and that is one skill, not
four.

---

# 1 · HEAT REJECTION — the part you stopped one line short of

## 21st N-2 (d) · the concept that has cost you marks three times

**A chiller does not destroy heat. It moves it.** And it must also get rid of the
energy it spent moving it.

```
        room/process                                    cooling tower
             │                                                ▲
             │  Q_cooling                         Q_rejected  │
             ▼                                                │
        ┌─────────────────────────────────────────────────────┴──┐
        │  EVAPORATOR  ──►  COMPRESSOR or GENERATOR  ──►  CONDENSER │
        └──────────────────────▲─────────────────────────────────┘
                               │  the energy you SPENT
                               │  (electricity, or steam)

        Q_rejected  =  Q_cooling  +  the energy you spent
```

**That is the whole thing.** The condenser must dump both, because both entered the
refrigerant.

### Turning it into a formula

**COP tells you what you spent:** `COP = cooling / spent`, so `spent = cooling/COP`.

```
    Q_rejected  =  Q_cooling  +  Q_cooling/COP
                =  Q_cooling × (1 + 1/COP)

    In BEE's units:   condenser duty = TR × 3024 × (1 + 1/COP)
```

### Why a VAM needs a bigger cooling tower — the 21st N-2 (d) answer

```
    2400 TR, centrifugal at COP 4.4:
        2400 × 3024 × (1 + 1/4.4) = 2400 × 3024 × 1.227 =    89,07,055 kCal/h
    2400 TR, absorption at COP 1.2:
        2400 × 3024 × (1 + 1/1.2) = 2400 × 3024 × 1.833 =  1,33,05,600 kCal/h

    ADDITIONAL heat to reject                            =    43,98,545 kCal/h
    Cooling water = 43,98,545/(1000 × 1 × (42 − 34))     =       549.82 m³/hr
```

> **Same cooling. 50% more heat out the back.** A low-COP machine is not "less
> efficient" in a vague way — **it literally pushes more heat into the cooling
> tower**, because the steam that drove it has to leave too.
>
> **The two multipliers to know cold:** `×1.227` at COP 4.4 · `×1.833` at COP 1.2.

### ⚠️ One nuance BEE tests — shaft work, not motor input

**18th N-2 uses `1.52 kW/TR`, not the `1.728` it calculated two lines earlier.**

```
    1.728 kW/TR  =  what the MOTOR draws from the grid
    1.52  kW/TR  =  1.728 × 0.88  =  what the SHAFT delivers to the refrigerant
```

**Motor losses heat the motor room, not the refrigerant.** The condenser only sees
what crossed into the gas. **When a motor efficiency is given, use shaft power in
the rejection sum.**

```
    Q_condenser = TR × 3024  +  TR × (kW/TR)_shaft × 860
                = 25.92 × 3024 + 25.92 × 1.52 × 860 = 1,12,266 kCal/h
```

### 18th N-2 (f) — and the shortcut hiding in it

Pre-cooling the inlet water from 30 °C to 12 °C in a separate chiller takes load off
the ice plant chiller:

```
    Pre-cool duty = 16500 × 1 × (30 − 12)/(24 × 3024)   =  4.09 TR
    Ice chiller now  25.92 − 4.09                       = 21.83 TR
    New condenser = 21.83 × 3024 + 21.83 × 1.52 × 860   = 94,550 kCal/h
    Reduction = (1,12,266 − 94,550)/1,12,266            =  15.8 %
```

> **Notice: both terms scale with TR**, so the percentage reduction is just
> `1 − 21.83/25.92 = 15.8%`. **You never needed the kCal figures at all.** When a
> question asks for a *% change* and every term is proportional to one quantity,
> **take the ratio and stop.**

---

# 2 · THE ENGINE HEAT SPLIT — 20th N-4(D) parts 2 and 3

## A gas engine makes three products, and you are paid for all three

```
                              ┌──────────────┐
      fuel 100 % ────────────►│  GAS ENGINE  │
                              └───┬───┬───┬──┘
                                  │   │   │
           shaft power 28 % ◄─────┘   │   └─────► exhaust gas 43 %
                                      │           (hot, ~450 °C)
              jacket cooling 29 % ◄───┘
                (hot water, ~90 °C)
```

**The percentages are given, and they must total 100.** *(28 + 29 = 57, so exhaust
is 43% — the paper does not say so; **you subtract**.)*

### Step 1 — get the fuel heat, and check it against the shaft

```
    Heat rate     = 860/0.28                    = 3071 kCal/kWh
    Gas           = 625 × 3071/9000             = 213.3 Sm³/hr      ← you did this
    FUEL HEAT     = 213.3 × 9000                = 19,19,646 kCal/hr

    CHECK:  28 % of 19,19,646 = 5,37,501  and  625 kW × 860 = 5,37,500  ✓
```
**That agreement is free and it proves the whole base.**

### Step 2 — each stream drives something, and the shape is always the same

> ```
>     output  =  heat available  ÷  what ONE unit of output costs
> ```

| Stream | Drives | One unit costs | Result |
|---|---|---|---|
| **jacket** 29 % = 5,56,697 | a VAM at COP 1.65 | `3024/1.65` per TR | **303.8 TR** |
| **exhaust** 43 % = 8,25,448, of which 20 % used | hot water 30 → 60 °C | `1 × 30` per kg | **5503 kg/hr** |

```
    TR    = heat × COP/3024 = 5,56,697 × 1.65/3024      = 303.8 TR
    water = 1,65,090/(1 × (60 − 30))                     = 5503 kg/hr
```

> **Read the COP's direction.** `COP = cooling/heat input`, so **cooling = heat ×
> COP**. Here COP 1.65 is *above* 1, which happens for a hot-water VAM — so the
> cooling delivered is *larger* than the heat supplied. **Multiply, do not divide.**
> *(In the 21st N-2 you wanted steam **for** a given cooling, so you divided:
> `2400 × 3024/1.2`. Same formula, opposite unknown — check which side you are on.)*

---

# 3 · THE ECONOMICS — 20th N-4(D) part 4, 22nd N-2(b), 18th N-2 (e)

## The rule: price the SAME services both ways

**The new system does several jobs at once. The old system needed a separate bill
for each.** List them, price each, total, then compare with the new system's single
bill.

### 20th N-4(D) part 4, in full

```
    THE TRIGENERATION PLANT DELIVERS THREE SERVICES:
        625 kW of power  ·  303.8 TR of cooling  ·  5503 kg/hr of hot water

    WHAT EACH COSTS IN THE EXISTING SYSTEM
        power      625 × 9.25                              = ₹5781.25/hr
        cooling    303.8 × 11.25                            = ₹3417.75/hr
        hot water  5503 × 1 × 30/500 = 330.2 kg steam/hr
                   × 2.85                                   = ₹ 941.00/hr
                                                     TOTAL  = ₹10,140/hr

    WHAT THE NEW SYSTEM COSTS
        gas only   213.3 × 45                               = ₹ 9598/hr

    Saving  = 10,140 − 9598 = ₹542/hr  × 7500 h  = ₹40.6 LAKH/YEAR
```

> ### ⚠️ The error this structure prevents
>
> **If you price only the electricity, the gas engine looks like a disaster** —
> ₹9598 to replace ₹5781. **It only pays because it also delivers the chilling and
> the hot water free.** Miss one service and the answer inverts.
>
> **So before costing anything, write the list of services.** Three lines. The marks
> follow the list.

### 22nd N-2(b) — the same structure, other way up

Here the *benefit* is given (₹450 lakh/yr of process gain) and you must add up what
it costs to get it:

```
    additional chiller   117.6 kW
    additional fan       442   kW
    additional CT         11   kW
                TOTAL    570.6 kW
    Cost = 570.6 × 9 × 8000/10⁵            = ₹410.8 lakh/yr
    Net  = 450 − 410.8                     = ₹39.2 lakh/yr  ⟹ viable, but thin
```

**Every kW the proposal adds must be counted** — the chiller *and* the fan *and* the
cooling tower. **Count only the chiller and it looks twice as good as it is.**

### 18th N-2 (e) — a cost comparison inside one plant

```
    Pre-cool chiller    0.8 kW/TR × 4.09 TR × 24 h     =   78.5 kWh/day
    Ice chiller now     21.83 × 1.728 × 24             =  905.2 kWh/day
    Auxiliaries         unchanged                      =  189.8 kWh/day
                                              TOTAL    = 1173.5 kWh/day
    Was                                                = 1265   kWh/day
    Per tonne of output  1173.5/15 = 78.2  vs  84.33   ⟹ saving 6.1 kWh/T
```

> **The auxiliaries are unchanged and must still appear in the total.** Dropping a
> term because it did not change is the commonest way to lose a comparison —
> **the total must be a total.**

---

# 4 · The four checks to carry in

```
 1.  Q_rejected = Q_cooling + what you spent
     condenser duty = TR × 3024 × (1 + 1/COP)
     ×1.227 at COP 4.4   ·   ×1.833 at COP 1.2
     use SHAFT kW/TR, not motor input, when a motor efficiency is given

 2.  Percentages of fuel heat must total 100.
     The stream the paper does not name is the one you subtract.
     Check: 28 % of fuel heat  ==  kW × 860

 3.  output = heat available ÷ what one unit of output costs
     TR from heat  = heat × COP/3024        (COP > 1 → multiply)
     heat for TR   = TR × 3024/COP          (opposite unknown)
     water         = heat/(Cp × ΔT)
     steam         = heat/(h_steam − h_feed)

 4.  List the SERVICES before costing anything.
     Price every one in the old system; compare against the new system's
     single bill. Count every kW the proposal adds, not just the obvious one.
     A term that did not change still belongs in the total.
```

---

# And the one-line version of everything above

> **The opening parts ask what the machine made. The back halves ask where the rest
> of the energy went — and it always went somewhere you can name.**
>
> **Follow the energy until it has all been accounted for, then price each stream.**
