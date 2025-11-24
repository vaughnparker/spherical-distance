# Appendix C: The Cosine Difference Formula

## The Identity

The cosine difference formula states:

```
cos(A - B) = cos(A) × cos(B) + sin(A) × sin(B)
```

This identity appears in Step 4 when we simplify the expression `[cos(λ₁) × cos(λ₂) + sin(λ₁) × sin(λ₂)]` into `cos(λ₁ - λ₂)`.

While we accept this identity in the main derivation to keep things moving, here we'll prove where it comes from.

## Geometric Proof Using the Unit Circle

The cleanest way to understand this formula is through geometry on the unit circle (a circle with radius 1).

### Setup

Imagine a unit circle centered at the origin. We'll place two points on this circle:
- **Point P** at angle A from the positive x-axis
- **Point Q** at angle B from the positive x-axis

From our coordinate conversion formulas (Step 2), these points have coordinates:
- **Point P:** (cos(A), sin(A))
- **Point Q:** (cos(B), sin(B))

The angle between these two points (measured from Q to P going counterclockwise) is **(A - B)**.

### Finding the Distance Between P and Q

We can find the straight-line distance between P and Q in two different ways, and setting them equal will give us our formula.

**Method 1: Using the 2D distance formula**

The distance between P = (cos(A), sin(A)) and Q = (cos(B), sin(B)) is:

```
distance² = [cos(A) - cos(B)]² + [sin(A) - sin(B)]²
```

Expanding:
```
distance² = cos²(A) - 2cos(A)cos(B) + cos²(B) + sin²(A) - 2sin(A)sin(B) + sin²(B)
```

Group the terms:
```
distance² = [cos²(A) + sin²(A)] + [cos²(B) + sin²(B)] - 2cos(A)cos(B) - 2sin(A)sin(B)
```

Using the Pythagorean identity cos²(θ) + sin²(θ) = 1:
```
distance² = 1 + 1 - 2cos(A)cos(B) - 2sin(A)sin(B)
distance² = 2 - 2[cos(A)cos(B) + sin(A)sin(B)]
```

**Method 2: Using the Law of Cosines**

Now let's find this same distance using the Law of Cosines. We have a triangle with:
- Two sides of length 1 (from origin to P and from origin to Q)
- The angle between them is (A - B)
- The third side is the distance we're looking for

The Law of Cosines states:
```
c² = a² + b² - 2ab × cos(C)
```

In our case:
```
distance² = 1² + 1² - 2(1)(1) × cos(A - B)
distance² = 2 - 2cos(A - B)
```

### Setting Them Equal

Both methods give us the distance², so they must be equal:

```
2 - 2[cos(A)cos(B) + sin(A)sin(B)] = 2 - 2cos(A - B)
```

Subtract 2 from both sides:
```
-2[cos(A)cos(B) + sin(A)sin(B)] = -2cos(A - B)
```

Divide by -2:
```
cos(A)cos(B) + sin(A)sin(B) = cos(A - B)
```

**That's our formula!** ✓

## Alternative: Geometric Visualization

Here's an intuitive way to think about why this works:

When you have two unit vectors (arrows of length 1) at angles A and B:
- The "horizontal overlap" between them is cos(A) × cos(B)
- The "vertical overlap" between them is sin(A) × sin(B)
- Their total alignment (how much they point in the same direction) is the sum of these overlaps
- This total alignment equals cos(angle between them) = cos(A - B)

## Related Formulas

Once you have the cosine difference formula, you can derive several related identities:

**Cosine sum formula:**
```
cos(A + B) = cos(A - (-B)) = cos(A)cos(-B) + sin(A)sin(-B)
```

Since cos(-B) = cos(B) and sin(-B) = -sin(B):
```
cos(A + B) = cos(A)cos(B) - sin(A)sin(B)
```

**Sine formulas:**
Using the identity sin(θ) = cos(90° - θ), you can derive:
```
sin(A + B) = sin(A)cos(B) + cos(A)sin(B)
sin(A - B) = sin(A)cos(B) - cos(A)sin(B)
```

These angle addition formulas are fundamental tools in trigonometry!

---

[← Back to Step 4](Step4.md)