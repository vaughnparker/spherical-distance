# spherical-distance
An attempt to derive the formula for distance between two points on the surface of a sphere. This derivation is intended to be "from first principles" - using only early high school level math.

## Overview

This project walks through a complete derivation of the spherical distance formula (related to the Haversine formula) starting from basic concepts. The approach uses:
- Basic trigonometry (sine, cosine)
- The Pythagorean theorem (extended to 3D)
- Simple algebra
- Geometric reasoning about triangles

**What makes this different:** Rather than starting with advanced concepts like dot products or accepting complex formulas without proof, we build everything up from intuitive geometric ideas.

## Structure

The derivation is split into several steps:

### Main Derivation

1. **[Step 1: Understanding Radians and Arc Length](Step1.md)**
   - Why we measure angles in radians
   - The relationship between angles and distances on a circle
   - Setting up the fundamental formula: distance = radius × angle

2. **[Step 2: Converting Latitude/Longitude to 3D Coordinates](Step2.md)**
   - Setting up a 3D coordinate system for Earth
   - Deriving the conversion formulas from spherical to Cartesian coordinates
   - Understanding how latitude and longitude map to x, y, z positions

3. **[Step 3: Finding the Angle Using a Triangle](Step3.md)**
   - Drawing a triangle between two points and Earth's center
   - Using basic geometry to relate the straight-line "chord" distance to the central angle
   - Applying simple trigonometry (sine = opposite/hypotenuse)

4. **[Step 4: The Algebra (Final Formula)](Step4.md)**
   - Substituting the coordinate conversion formulas
   - Expanding and simplifying the resulting expressions
   - Arriving at the final distance formula

5. **[Step 5: A Worked Example](Step5_example.md)**
   - Calculating the distance from New York to London
   - Verifying the formula produces accurate results

### Appendices

- **[Appendix A: Latitude/Longitude Guessing Game](AppendixA_coordinate_guessing_game.md)**
  - Interactive exercises to build intuition for coordinate systems

- **[Appendix B: The Dot Product Derivation](alternative_derivation_dot_product/AppendixB_dot_product_derivation.md)**
  - An alternative derivation using vectors and dot products
  - More abstract but more elegant for those familiar with linear algebra

- **[Appendix C: The Cosine Difference Formula](AppendixC_cosine_difference.md)**
  - Derivation of the trigonometric identity used in the optional simplification

- **[Appendix D: The 3D Distance Formula](AppendixD_3d_distance.md)**
  - Proof of the Pythagorean theorem extended to three dimensions

## Prerequisites

To follow this derivation, you should be comfortable with:
- Basic trigonometry (sine, cosine, and their inverses)
- The Pythagorean theorem
- Basic algebra (expanding expressions, factoring)
- Reading mathematical notation

No calculus, linear algebra, or advanced mathematics required!

## The Result

By the end, you'll have derived:
```
d = 2R × arcsin(√[(1/2) × {1 - cos(φ₁) × cos(φ₂) × [cos(λ₁) × cos(λ₂) + sin(λ₁) × sin(λ₂)]
                            - sin(φ₁) × sin(φ₂)}])
```

Where φ represents latitude, λ represents longitude, R is Earth's radius, and d is the distance along the surface.

This formula (and its simplified form, the Haversine formula) is used in navigation systems, mapping applications, and anywhere distances on a sphere need to be calculated.