# Inverse Problems — When the Question Runs Backwards

Every worked example in this curriculum has run **forwards**: fuel composition →
air → flue gas → losses → efficiency. Real papers sometimes reverse the arrow, and
a forward-only habit stops dead at those questions.

Mock A's N-1 was one. Every needed tool was recalled correctly, and the setup
still started from the fuel composition — which was the *answer*.

## The recognition trigger

> **Before writing anything, identify what is given and what is asked. If the
> thing you would normally start from is the thing being asked for, the problem
> runs backwards.**

Ten seconds, and it changes the entire approach.

## The four inverse types that appear in Paper 4

### 1. Flue gas analysis → fuel composition

**Given** the dry flue gas composition. **Asked** for the fuel's carbon and
hydrogen.

The key question: *what can each flue gas component only have come from?*

| Flue gas component | Can only have come from |
|---|---|
| CO₂ | carbon in the fuel |
| N₂ | the combustion air (nitrogen in fuel is tiny) |
| O₂ | air supplied but not consumed |
| H₂O | hydrogen in the fuel, plus fuel moisture |

Work **per 100 kg of dry flue gas** — it makes the percentages into kilograms:

```
    Carbon      = %CO₂ × 12/44
    Air         = %N₂ / 0.77
    O₂ supplied = 0.23 × air
    O₂ consumed = O₂ supplied − %O₂ in flue gas
    O₂ for C    = carbon × 32/12
    O₂ for H₂   = O₂ consumed − O₂ for C
    Hydrogen    = O₂ for H₂ / 8
```

Every constant is one you already use forwards. Only the direction changes.

*Worked in full: Mock A N-1, `papers/25-1.pdf` question N-2.*

### 2. Performance → sizing

**Given** duty and temperatures. **Asked** for area, or the change in area.

Forward: `Q = U·A·LMTD`. Backward: `A = Q/(U·LMTD)`. Straightforward, and already
routine.

The harder version compares two cases: **the ratio eliminates U**, which is often
not given at all:

```
    A₂/A₁ = (Q₂/LMTD₂) / (Q₁/LMTD₁)
```

*Worked: Mock A N-2, `papers/17.pdf`.*

### 3. Output → input

**Given** what a machine delivers. **Asked** what it consumes.

The trap is direction: **input = output ÷ efficiency**, never × efficiency. The
inverse family from `reciprocal-traps.md`:

```
    fuel     = useful heat / (η × GCV)
    motor kW = hydraulic kW / (η_pump × η_motor)
    heat rate = 860 / η
```

### 4. Efficiency → losses, or losses → efficiency

`η = 100 − Σ losses` runs either way. Given efficiency and all-but-one loss, the
missing loss is whatever balances. Worth spotting — it can save recomputing a hard
term.

## The general method

1. **List what is given.** Literally write it down.
2. **List what is asked.**
3. **Ask whether the normal starting point is in the given list.** If not, reverse.
4. **Find the anchor** — the one quantity that can be computed directly from the
   data with no unknowns. In type 1 that is carbon from CO₂. Start there.
5. **Chain outward** from the anchor, one conserved quantity at a time.

## Why this matters more than it looks

Recognising a familiar *pattern* is not the same as understanding the *physics*.
Mass balance, energy balance and the combustion reactions do not care which
direction you read them. A forward-only habit means every tool is in place and the
question is still unanswerable.

Paper 4 sets these deliberately — the prospectus says its difficulty is
"comparatively much higher", and this is one of the ways.
