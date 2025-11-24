# Step 3: Finding the Angle Using a Triangle

## The Triangle Setup

Let's think about the geometry here. We have three points:
- **Point 1 (A):** New York City (on the sphere's surface)
- **Point 2 (B):** London (on the sphere's surface)  
- **Point C:** The center of the Earth

These three points form a **triangle**! 

If we draw lines connecting them:
- **Side AC:** From center to Point 1 (length = R, the radius)
- **Side BC:** From center to Point 2 (length = R, the radius)
- **Side AB:** Direct line from Point 1 to Point 2 (length = chord)

The chord is the straight-line distance cutting through the Earth, not the curved distance along the surface. Think of it like tunneling through the Earth instead of flying over it.

Notice something special: **This is an isosceles triangle!** Two of its sides (AC and BC) are both equal to R.

## Splitting the Triangle in Half

Here's where it gets clever. Let's create a new point:

- **Point D:** The midpoint of line AB (halfway between Point 1 and Point 2)

Now draw a line from C (center of Earth) to D (the midpoint). This line **CD splits our isosceles triangle into two identical right triangles**.

Why is it a right triangle? In any isosceles triangle, the line from the apex to the midpoint of the base is perpendicular to the base. So angle ADC = 90°.

Let's focus on one of these right triangles: triangle ACD.

## Examining Triangle ACD

This right triangle has:

**Vertices:**
- **A:** Point 1 (on the surface)
- **C:** Center of Earth
- **D:** Midpoint between Point 1 and Point 2 (inside the Earth)

**Sides:**
- **AC = R** (the radius—this is our hypotenuse)
- **AD = chord/2** (half the straight-line distance between our two points)
- **CD = ?** (we don't actually need this!)

**Angles:**
- **Angle ADC = 90°** (right angle)
- **Angle ACD = θ/2** (half of the central angle we're looking for)
- **Angle DAC = ?** (we don't need this either!)

## Using Basic Trigonometry

Now we can use the most basic trig formula: sine = opposite/hypotenuse.

In our right triangle ACD:
```
sin(angle ACD) = opposite side / hypotenuse
sin(θ/2) = AD / AC
sin(θ/2) = (chord/2) / R
```

Simplifying:
```
sin(θ/2) = chord / (2R)
```

To solve for θ/2, we use the inverse sine function (arcsin):
```
θ/2 = arcsin(chord / (2R))
```

Therefore:
```
θ = 2 × arcsin(chord / (2R))
```

**This is beautiful!** We've related the central angle θ to the chord length using just basic right-triangle trigonometry.

## From Angle to Distance

Remember from Step 1, the distance along the surface of a sphere equals the radius times the angle (in radians):

```
d = R × θ
```

Substituting our expression for θ:
```
d = R × 2 × arcsin(chord / (2R))
d = 2R × arcsin(chord / (2R))
```

## Calculating the Chord Length

We need to find the chord—the straight-line distance between Point 1 at (x₁, y₁, z₁) and Point 2 at (x₂, y₂, z₂).

The straight-line distance between two points in 3D space uses the **3D distance formula** (an extension of the Pythagorean theorem to three dimensions):

```
chord = √[(x₂ - x₁)² + (y₂ - y₁)² + (z₂ - z₁)²]
```

This formula says: square the difference in each coordinate, add them up, and take the square root. It's the direct distance "as the crow flies" through 3D space.

*If you're curious where this formula comes from, see [Appendix D: The 3D Distance Formula](AppendixD_3d_distance.md).*

## Connecting to Latitude and Longitude

Now here's the key: we already know from Step 2 how to convert latitude and longitude into x, y, z coordinates:

```
x = R × cos(φ) × cos(λ)
y = R × cos(φ) × sin(λ)
z = R × sin(φ)
```

So for our two points:
- **Point 1:** x₁ = R × cos(φ₁) × cos(λ₁), y₁ = R × cos(φ₁) × sin(λ₁), z₁ = R × sin(φ₁)
- **Point 2:** x₂ = R × cos(φ₂) × cos(λ₂), y₂ = R × cos(φ₂) × sin(λ₂), z₂ = R × sin(φ₂)

## The Plan for Step 4

In the next step, we'll:
1. **Substitute** these coordinate formulas into the chord distance formula
2. **Expand** the squared differences: (x₂ - x₁)², (y₂ - y₁)², (z₂ - z₁)²
3. **Simplify** using algebra and a trigonometric identity
4. **Combine** everything to get our final distance formula purely in terms of φ₁, λ₁, φ₂, and λ₂

The geometric insight is complete—now we just need to work through the algebra!