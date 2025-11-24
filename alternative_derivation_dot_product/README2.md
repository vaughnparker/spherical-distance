# Alternative Derivation: Dot Product Approach

This folder contains an earlier version of Steps 3 and 4 that derives the spherical distance formula using vectors and the dot product.

## Why We Moved Away From This Approach

While mathematically elegant, the dot product derivation has some pedagogical challenges for a "first principles" explanation:

1. **Abstract concept**: The dot product is less intuitive than basic geometric shapes like triangles
2. **Requires accepting a theorem**: The relationship between dot product and angle (`P₁ · P₂ = |P₁| × |P₂| × cos(θ)`) needs to be taken as given, which somewhat violates the "from first principles" goal
3. **Less visual**: Harder to draw/visualize compared to "here's a triangle with three sides"

## The Current Approach (Chord Method)

The main derivation now uses:
- The 3D Pythagorean theorem to find the straight-line "chord" distance between two points
- This trades the abstract dot product for more concrete geometric reasoning

## Why Keep This Version?

The dot product approach is still valuable because:
- It's more commonly seen in textbooks and online resources
- It's more elegant once you understand vectors
- Some readers may find it clearer if they're already comfortable with linear algebra

If you're familiar with dot products, this derivation might actually feel more natural!

## Contents

- `Step3_dot_product.md` - Introduces vectors and the dot product, derives the angle relationship
- `Step4_dot_product.md` - Substitutes coordinate formulas and derives the final distance equation