# Step 4: The Algebra (Deriving the Final Formula)

## Where We Are

From Step 3, we have:

```
d = 2R × arcsin(chord / (2R))
```

Where the chord is:
```
chord = √[(x₂ - x₁)² + (y₂ - y₁)² + (z₂ - z₁)²]
```

And from Step 2, we know how to convert latitude/longitude to coordinates:
```
x = R × cos(φ) × cos(λ)
y = R × cos(φ) × sin(λ)
z = R × sin(φ)
```

**Our goal:** Combine these to get a formula that uses only φ₁, λ₁, φ₂, λ₂, and R.

## Step 1: Substitute the Coordinate Formulas

Let's write out all six coordinates:

**Point 1:**
```
x₁ = R × cos(φ₁) × cos(λ₁)
y₁ = R × cos(φ₁) × sin(λ₁)
z₁ = R × sin(φ₁)
```

**Point 2:**
```
x₂ = R × cos(φ₂) × cos(λ₂)
y₂ = R × cos(φ₂) × sin(λ₂)
z₂ = R × sin(φ₂)
```

Now we need to calculate (x₂ - x₁)², (y₂ - y₁)², and (z₂ - z₁)².

### Calculating (x₂ - x₁)²

```
x₂ - x₁ = R × cos(φ₂) × cos(λ₂) - R × cos(φ₁) × cos(λ₁)
        = R × [cos(φ₂) × cos(λ₂) - cos(φ₁) × cos(λ₁)]
```

Squaring:
```
(x₂ - x₁)² = R² × [cos(φ₂) × cos(λ₂) - cos(φ₁) × cos(λ₁)]²
```

### Calculating (y₂ - y₁)²

```
y₂ - y₁ = R × cos(φ₂) × sin(λ₂) - R × cos(φ₁) × sin(λ₁)
        = R × [cos(φ₂) × sin(λ₂) - cos(φ₁) × sin(λ₁)]
```

Squaring:
```
(y₂ - y₁)² = R² × [cos(φ₂) × sin(λ₂) - cos(φ₁) × sin(λ₁)]²
```

### Calculating (z₂ - z₁)²

```
z₂ - z₁ = R × sin(φ₂) - R × sin(φ₁)
        = R × [sin(φ₂) - sin(φ₁)]
```

Squaring:
```
(z₂ - z₁)² = R² × [sin(φ₂) - sin(φ₁)]²
```

## Step 2: Add Them Together

The chord squared is:
```
chord² = (x₂ - x₁)² + (y₂ - y₁)² + (z₂ - z₁)²
       = R² × [cos(φ₂) × cos(λ₂) - cos(φ₁) × cos(λ₁)]²
       + R² × [cos(φ₂) × sin(λ₂) - cos(φ₁) × sin(λ₁)]²
       + R² × [sin(φ₂) - sin(φ₁)]²
```

Factor out R²:
```
chord² = R² × {[cos(φ₂) × cos(λ₂) - cos(φ₁) × cos(λ₁)]²
             + [cos(φ₂) × sin(λ₂) - cos(φ₁) × sin(λ₁)]²
             + [sin(φ₂) - sin(φ₁)]²}
```

## Step 3: Expand the Squared Terms

This is going to get messy before it gets clean! Let's expand each squared bracket using (a - b)² = a² - 2ab + b².

**First bracket:**
```
[cos(φ₂) × cos(λ₂) - cos(φ₁) × cos(λ₁)]²
= cos²(φ₂) × cos²(λ₂) - 2cos(φ₂) × cos(λ₂) × cos(φ₁) × cos(λ₁) + cos²(φ₁) × cos²(λ₁)
```

**Second bracket:**
```
[cos(φ₂) × sin(λ₂) - cos(φ₁) × sin(λ₁)]²
= cos²(φ₂) × sin²(λ₂) - 2cos(φ₂) × sin(λ₂) × cos(φ₁) × sin(λ₁) + cos²(φ₁) × sin²(λ₁)
```

**Third bracket:**
```
[sin(φ₂) - sin(φ₁)]²
= sin²(φ₂) - 2sin(φ₂) × sin(φ₁) + sin²(φ₁)
```

## Step 4: Combine and Simplify

Adding all three expanded terms together (in the order they appear):

```
chord² = R² × {
    cos²(φ₂) × cos²(λ₂) 
  - 2cos(φ₂) × cos(λ₂) × cos(φ₁) × cos(λ₁) 
  + cos²(φ₁) × cos²(λ₁)
  + cos²(φ₂) × sin²(λ₂) 
  - 2cos(φ₂) × sin(λ₂) × cos(φ₁) × sin(λ₁) 
  + cos²(φ₁) × sin²(λ₁)
  + sin²(φ₂) 
  - 2sin(φ₂) × sin(φ₁) 
  + sin²(φ₁)
}
```

Now let's regroup these terms to make patterns more visible. We'll collect all the Point 2 terms, all the Point 1 terms, and all the negative cross-terms:

```
chord² = R² × {
    cos²(φ₂) × cos²(λ₂) + cos²(φ₂) × sin²(λ₂) + sin²(φ₂)
  + cos²(φ₁) × cos²(λ₁) + cos²(φ₁) × sin²(λ₁) + sin²(φ₁)
  - 2cos(φ₂) × cos(φ₁) × cos(λ₂) × cos(λ₁) 
  - 2cos(φ₂) × cos(φ₁) × sin(λ₂) × sin(λ₁)
  - 2sin(φ₂) × sin(φ₁)
}
```

We can factor the fourth and fifth lines:

```
chord² = R² × {
    cos²(φ₂) × cos²(λ₂) + cos²(φ₂) × sin²(λ₂) + sin²(φ₂)
  + cos²(φ₁) × cos²(λ₁) + cos²(φ₁) × sin²(λ₁) + sin²(φ₁)
  - 2cos(φ₂) × cos(φ₁) × [cos(λ₂) × cos(λ₁) + sin(λ₂) × sin(λ₁)]
  - 2sin(φ₂) × sin(φ₁)
}
```

Now let's simplify the first line. Notice:
```
cos²(φ₂) × cos²(λ₂) + cos²(φ₂) × sin²(λ₂) = cos²(φ₂) × [cos²(λ₂) + sin²(λ₂)]
```

Using the Pythagorean identity **cos²(λ) + sin²(λ) = 1**:
```
= cos²(φ₂) × 1 = cos²(φ₂)
```

So the first line becomes:
```
cos²(φ₂) + sin²(φ₂) = 1
```

Similarly, the second line:
```
cos²(φ₁) × cos²(λ₁) + cos²(φ₁) × sin²(λ₁) + sin²(φ₁) = 1
```

Our expression simplifies to:
```
chord² = R² × {
    1 + 1
  - 2cos(φ₂) × cos(φ₁) × [cos(λ₂) × cos(λ₁) + sin(λ₂) × sin(λ₁)]
  - 2sin(φ₂) × sin(φ₁)
}
```

```
chord² = R² × {2 - 2cos(φ₂) × cos(φ₁) × [cos(λ₂) × cos(λ₁) + sin(λ₂) × sin(λ₁)]
               - 2sin(φ₂) × sin(φ₁)}
```

Factor out the 2:
```
chord² = 2R² × {1 - cos(φ₂) × cos(φ₁) × [cos(λ₂) × cos(λ₁) + sin(λ₂) × sin(λ₁)]
                - sin(φ₂) × sin(φ₁)}
```

## Step 5: Getting to the Final Formula

From Step 4, we have:

```
chord² = 2R² × {1 - cos(φ₁) × cos(φ₂) × [cos(λ₁) × cos(λ₂) + sin(λ₁) × sin(λ₂)]
                - sin(φ₁) × sin(φ₂)}
```

From Step 3, we know that:
```
d = 2R × arcsin(chord / (2R))
```

So we need to find `chord / (2R)`. Dividing our chord² equation by 4R²:

```
chord² / (4R²) = (2R²/4R²) × {1 - cos(φ₁) × cos(φ₂) × [cos(λ₁) × cos(λ₂) + sin(λ₁) × sin(λ₂)]
                               - sin(φ₁) × sin(φ₂)}
                
                = (1/2) × {1 - cos(φ₁) × cos(φ₂) × [cos(λ₁) × cos(λ₂) + sin(λ₁) × sin(λ₂)]
                           - sin(φ₁) × sin(φ₂)}
```

Taking the square root of both sides:

```
chord / (2R) = √[(1/2) × {1 - cos(φ₁) × cos(φ₂) × [cos(λ₁) × cos(λ₂) + sin(λ₁) × sin(λ₂)]
                           - sin(φ₁) × sin(φ₂)}]
```

Substituting into our distance formula:

---

## **The Final Formula**

**Distance between two points on a sphere:**

```
d = 2R × arcsin(√[(1/2) × {1 - cos(φ₁) × cos(φ₂) × [cos(λ₁) × cos(λ₂) + sin(λ₁) × sin(λ₂)]
                            - sin(φ₁) × sin(φ₂)}])
```

Where:
- φ₁, φ₂ = latitudes of the two points (in radians)
- λ₁, λ₂ = longitudes of the two points (in radians)
- R = radius of the sphere
- d = distance along the surface

This is it! We've derived the complete formula from first principles.

---

## Optional: Further Simplification (The Haversine Formula)

The formula above works perfectly, but with some trigonometric identities, we can make it even more compact.

**Using the cosine difference formula:**

The expression `[cos(λ₁) × cos(λ₂) + sin(λ₁) × sin(λ₂)]` equals `cos(λ₁ - λ₂)` or `cos(Δλ)`.

*For a derivation, see [Appendix C: The Cosine Difference Formula](AppendixC_cosine_difference.md).*

This simplifies our formula to:
```
d = 2R × arcsin(√[(1/2) × {1 - cos(φ₁) × cos(φ₂) × cos(Δλ) - sin(φ₁) × sin(φ₂)}])
```

**Using half-angle identities:**

With further trigonometric manipulation (half-angle formulas), this can be rewritten as the famous **Haversine formula**:

Let:
```
a = sin²((φ₂ - φ₁)/2) + cos(φ₁) × cos(φ₂) × sin²(Δλ/2)
```

Then:
```
d = 2R × arcsin(√a)
```

Where Δλ = |λ₁ - λ₂|.

The Haversine formula is particularly popular in navigation and programming because it's numerically stable and compact. But remember—it's just a simplified version of the formula we derived above!

---

**Congratulations!** 🎉 You've just derived one of the most important formulas in navigation and geography, starting from first principles!

You built this by:
1. Understanding how arc length relates to angles (Step 1)
2. Converting latitude/longitude to 3D coordinates (Step 2)
3. Using basic geometry to relate the chord distance to the central angle (Step 3)
4. Working through the algebra to combine everything (Step 4)

---

## Want to See It in Action?

We've derived the formula from first principles—now let's verify it works! In [Step 5: A Worked Example](Step5_example.md), we'll calculate the actual distance from New York to London and see how close we get to the real distance.