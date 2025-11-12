# A Complete Example: New York to London

Let's use our formula to calculate the actual distance between New York City and London!

## Given Information

From our examples in Step 2:
- **New York City**: 40.7°N, -74.0°W
- **London**: 51.5°N, -0.1°W
- **Earth's radius**: R = 6,371 km

## Step 1: Convert Degrees to Radians

Remember, our formula requires angles in radians! To convert from degrees to radians:
```
radians = degrees × (π/180)
```

**New York:**
- φ₁ = 40.7° × (π/180) = 40.7 × 0.017453 = 0.7101 radians
- λ₁ = -74.0° × (π/180) = -74.0 × 0.017453 = -1.2915 radians

**London:**
- φ₂ = 51.5° × (π/180) = 51.5 × 0.017453 = 0.8989 radians
- λ₂ = -0.1° × (π/180) = -0.1 × 0.017453 = -0.0017 radians

**Longitude difference:**
```
Δλ = λ₁ - λ₂ = -1.2915 - (-0.0017) = -1.2898 radians
```

## Step 2: Calculate the Trigonometric Values

```
sin(φ₁) = sin(0.7101) = 0.6521
sin(φ₂) = sin(0.8989) = 0.7808
cos(φ₁) = cos(0.7101) = 0.7581
cos(φ₂) = cos(0.8989) = 0.6249
cos(Δλ) = cos(-1.2898) = 0.2756
```

(Note: cos(-x) = cos(x), so the negative sign doesn't matter)

## Step 3: Apply the Spherical Law of Cosines

```
cos(θ) = sin(φ₁) × sin(φ₂) + cos(φ₁) × cos(φ₂) × cos(Δλ)
cos(θ) = (0.6521 × 0.7808) + (0.7581 × 0.6249 × 0.2756)
cos(θ) = 0.5091 + 0.1305
cos(θ) = 0.6396
```

## Step 4: Find the Angle

```
θ = arccos(0.6396) = 0.8762 radians
```

## Step 5: Calculate the Distance

```
d = R × θ
d = 6,371 km × 0.8762
d = 5,583 km (or about 3,469 miles)
```

## Result

**The distance from New York City to London is approximately 5,583 kilometers (3,469 miles).**

For comparison, the actual great circle distance is about 5,585 km - our calculation is extremely close! The small difference comes from rounding in our intermediate steps and the fact that Earth isn't a perfect sphere.

---

**Try it yourself!** Pick any two cities from our list in Step 2 and calculate the distance between them. You'll need a calculator with sin, cos, and arccos functions (most scientific calculators or smartphone calculator apps have these).
