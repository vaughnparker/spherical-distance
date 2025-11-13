# Appendix 1: Proof of dot product formula

In Step 3, we make the claim that:

```
P₁ · P₂ = |P₁| × |P₂| × cos(θ)
```

Where:
- |P₁| = length of vector P₁ (distance from origin to Point 1)
- |P₂| = length of vector P₂ (distance from origin to Point 2)
- θ = the angle between the two vectors
- cos(θ) = cosine of that angle

In Step 3, we take this as a given. But there is a way to prove this from first principles. I found an excellent proof over at [math.stackexchange.com](https://math.stackexchange.com/questions/3784740/proof-of-dot-product-formula). I will go over it here.

This proof has two stages. First, we will prove the **Law of Cosines**. Then, we will use the law of cosines to show the claim that P₁ · P₂ = |P₁| × |P₂| × cos(θ). If you are not interested in proving the Law of Cosines, then skip to section 1.2

## Section 1.1: Proof of Law of Cosines

Suppose we have the following triangle:

![Triangle graphic](stackoverflow_proof_2.png)

The law of cosines states:

```
c² = a² + b² − 2ab cos C
```

Where **a**, **b**, and **c** are the lengths of the sides of a triangle, and **C** represents the angle opposite side **c**.

There are three relationships we can derive from the above diagram.

First, we can use the **Pythagorean theorem**, which states that the squares of the two legs of a right triangle sum to the square of the hypotenuse. In other words:

```
a² + b² = c²
```

Using this, we can see that we have two right triangles in the diagram. The left one has legs **x** and **h** and hypotenuse **a**. The right one has legs **(b − x)** and **h** and hypotenuse **c**. From the Pythagorean theorem, we get the first two relationships:

```
# Equation 1
c² = (b − x)² + h²

# Equation 2
a² = x² + h²
```

The third relationship comes from the definition of cosine. You may remember from Step 2 that:

```
cos(θ) = adjacent side / hypotenuse
adjacent side = hypotenuse × cos(θ)
```

Similarly, in this case we have:

```
# Equation 3
x = a cos(C)
```

We may observe that the left-hand side of the Law of Cosines has this **c²** term. Let’s start by trying to find what the square of one side of a general triangle, **c²**, is equal to. We can begin with Equation 1:

```
c² = (b − x)² + h²
c² = b² − 2bx + x² + h²
```

We can observe that the expression **x² + h²** appears here. As we know from Equation 2 above, this is equal to **a²**. Substituting, we then have:

```
c² = b² − 2bx + a²
```

Using Equation 3, we also know what **x** is equal to in terms of **a** and **C**. Substituting **a cos (C)** for **x**, we get:

```
c² = a² + b² − 2b(a cos C)
c² = a² + b² − 2ab cos C
```

And that’s the **Law of Cosines**.


## Section 1.2 Proof of the Dot Product Formula

Now that we are equipped with the **Law of Cosines**, we can move on to deriving the **dot product formula**.

Let’s go back to the triangle, but now suppose its three sides are represented by the vectors **w**, **v**, and **w − v**.

![Vector graphic](stackoverflow_proof_1.png)

If we plug the side lengths into the Law of Cosines and let the included angle **θ** correspond to angle **C**, we get:

```
c² = a² + b² − 2ab cos C
|w − v|² = |v|² + |w|² − 2|v||w| cos θ
```

We know that the **magnitude** of a vector can be found by taking the distance from the origin to the point described by the vector:

```
|v| = √(vₓ² + vᵧ²)
|v|² = vₓ² + vᵧ²
```

We also know that the vector **w − v** can be represented as **(wₓ − vₓ, wᵧ − vᵧ)**.

This gives us:

```
|w − v|² = |v|² + |w|² − 2|v||w| cos θ
(wₓ − vₓ)² + (wᵧ − vᵧ)² = vₓ² + vᵧ² + wₓ² + wᵧ² − 2|v||w| cos θ
wₓ² − 2wₓvₓ + vₓ² + wᵧ² − 2wᵧvᵧ + vᵧ² = vₓ² + vᵧ² + wₓ² + wᵧ² − 2|v||w| cos θ
−2wₓvₓ − 2wᵧvᵧ = −2|v||w| cos θ
wₓvₓ + wᵧvᵧ = |v||w| cos θ
v ⋅ w = |v||w| cos θ
```

And there we have it — a clean derivation of the **dot product formula** directly from the **Law of Cosines**.