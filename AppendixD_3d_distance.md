# Appendix D: The 3D Distance Formula

## The Formula

The 3D distance formula states that the distance between two points in 3D space is:

```
distance = √[(x₂ - x₁)² + (y₂ - y₁)² + (z₂ - z₁)²]
```

This appears in Step 3 when we calculate the chord length between two points on the sphere. Here we'll derive where this formula comes from.

## Starting with 2D: The Pythagorean Theorem

In 2D, if you have two points P₁ = (x₁, y₁) and P₂ = (x₂, y₂), you can find the distance between them using the Pythagorean theorem.

For some proofs of the Pythagorean Theorem, see:
* https://brilliant.org/wiki/proofs-of-the-pythagorean-theorem/
* https://www.mathsisfun.com/geometry/pythagorean-theorem-proof.html

Imagine drawing a right triangle:
- The horizontal leg has length |x₂ - x₁|
- The vertical leg has length |y₂ - y₁|
- The hypotenuse is the direct distance between the points

By the Pythagorean theorem (a² + b² = c²):

```
distance² = (x₂ - x₁)² + (y₂ - y₁)²
distance = √[(x₂ - x₁)² + (y₂ - y₁)²]
```

This is the familiar 2D distance formula.

## Extending to 3D: Apply the Pythagorean Theorem Twice

Now let's add a third dimension (z). We have:
- Point P₁ = (x₁, y₁, z₁)
- Point P₂ = (x₂, y₂, z₂)

Here's the key insight: **we can apply the Pythagorean theorem twice** - once in the x-y plane, then once more to include the z-direction.

### Step 1: Find the distance in the x-y plane

First, ignore the z-coordinates and find the distance between (x₁, y₁) and (x₂, y₂) in the x-y plane:

```
d_xy = √[(x₂ - x₁)² + (y₂ - y₁)²]
```

### Step 2: Now include the z-direction

Now imagine a new right triangle:
- One leg lies in the x-y plane with length d_xy (the distance we just found)
- The other leg is vertical with length |z₂ - z₁|
- The hypotenuse is the true 3D distance between P₁ and P₂

Apply the Pythagorean theorem again:

```
distance² = d_xy² + (z₂ - z₁)²
```

Substitute our expression for d_xy²:

```
distance² = [(x₂ - x₁)² + (y₂ - y₁)²] + (z₂ - z₁)²
distance² = (x₂ - x₁)² + (y₂ - y₁)² + (z₂ - z₁)²
```

Taking the square root:

```
distance = √[(x₂ - x₁)² + (y₂ - y₁)² + (z₂ - z₁)²]
```

**That's the 3D distance formula!** ✓

## Visualizing It

Think of it this way:
1. To get from P₁ to P₂, you could travel:
   - (x₂ - x₁) units in the x-direction
   - (y₂ - y₁) units in the y-direction
   - (z₂ - z₁) units in the z-direction

2. These three movements form the edges of a rectangular box (a "3D right triangle")

3. The direct distance is the diagonal through this box

4. The formula gives you that diagonal length

## A Concrete Example

Let's verify with a simple example:
- P₁ = (0, 0, 0) (the origin)
- P₂ = (3, 4, 12)

Using our formula:
```
distance = √[(3-0)² + (4-0)² + (12-0)²]
         = √[9 + 16 + 144]
         = √169
         = 13
```

We can verify this makes sense:
- In the x-y plane: √(3² + 4²) = √(9 + 16) = √25 = 5
- Then including z: √(5² + 12²) = √(25 + 144) = √169 = 13 ✓

## Generalization to Higher Dimensions

This pattern continues! In 4D, you'd have:
```
distance = √[(x₂ - x₁)² + (y₂ - y₁)² + (z₂ - z₁)² + (w₂ - w₁)²]
```

And so on for any number of dimensions. This is called the **Euclidean distance** and it's a fundamental concept in geometry and mathematics.

---

[← Back to Step 3](Step3.md)
