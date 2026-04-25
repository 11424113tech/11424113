# Problem 3: Thermal Engineering Case – CPU Cooling System

## Problem
How can we predict the cooling behavior of an electronic component (CPU)?

---

## Modeling: Newton's Law of Cooling

Let:

- T(t): temperature of the CPU at time t  
- T_s: ambient (surrounding) temperature  
- k > 0: cooling constant  

According to Newton's Law of Cooling:

dT/dt = -k (T - T_s)

---

## Step 1: Separate Variables

dT / (T - T_s) = -k dt

---

## Step 2: Integrate Both Sides

∫ 1/(T - T_s) dT = ∫ -k dt

ln|T - T_s| = -kt + C

---

## Step 3: Solve for T(t)

T - T_s = C e^{-kt}

T(t) = T_s + C e^{-kt}

---

## Step 4: Apply Initial Condition

Let T(0) = T_0

T_0 = T_s + C

C = T_0 - T_s

---

## Final Answer

T(t) = T_s + (T_0 - T_s)e^{-kt}

---

## Engineering Interpretation

As time increases:

e^{-kt} → 0

Thus:

T(t) → T_s

The CPU temperature will gradually decrease and approach the ambient temperature.
