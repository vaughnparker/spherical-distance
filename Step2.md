# Step 2: Putting Points in 3D Space

## From Latitude/Longitude to X, Y, Z

When you describe a point on Earth, you use:
- **Latitude (φ)**: how far north/south (0° at equator, 90° at north pole, -90° at south pole)
- **Longitude (λ)**: how far east/west (0° at prime meridian, ranges from -180° to 180°)

**Note:** I'm using the Greek letters φ (phi) for latitude and λ (lambda) for longitude because it's the standard mathematical convention. This makes our formulas match what you'll see in textbooks and code.

### Examples of Real-World Locations

To build intuition for how latitude and longitude work, here are a few examples:

- **New York City, USA**: (40.7°, -74.0°)
- **Tokyo, Japan**: (35.7°, 139.7°)
- **Sydney, Australia**: (-33.9°, 151.2°)

Notice how the signs tell you the hemisphere: positive latitude = north, negative = south, positive longitude = east, negative = west.

**Note:** You might see coordinates written as "33.9°S, 151.2°E" instead of "(-33.9°, 151.2°)". These mean the same thing! The letters (N/S/E/W) are just another way to indicate the sign. In our mathematical formulas, we'll use the positive/negative number convention.

Want to test your intuition? Try the [latitude/longitude guessing game](AppendixA_coordinate_guessing_game.md) before continuing!

---

Now, to calculate distances between points on a sphere, we need to work with angles. The easiest way to do this is to convert our latitude/longitude coordinates into **3D space** using x, y, z coordinates.

## The Conversion

We need to set up a 3D coordinate system. Imagine the sphere centered at the origin (the point 0, 0, 0) with radius R:

**Our coordinate system:**
- The **z-axis** points straight up through the North Pole
- The **x-axis** points out through the intersection of the equator and the prime meridian (0° longitude)
  - This point is in the Atlantic Ocean off the coast of West Africa in the Gulf of Guinea, south of Ghana
- The **y-axis** points out through the intersection of the equator and 90°E longitude
  - This point is in the Indian Ocean, west of Sumatra, Indonesia
- The center of the sphere is at the origin (0, 0, 0)

![Earth_Centered_Inertial_Coordinate_System.png](Earth_Centered_Inertial_Coordinate_System.png)

In this coordinate system, any point on Earth's surface can be described by three numbers (x, y, z), where each represents the distance along that axis from the origin.

**Our goal:** Convert from the familiar latitude/longitude system to this x, y, z system.

## The Conversion Formulas

For a point at latitude φ and longitude λ:

```
x = R × cos(φ) × cos(λ)
y = R × cos(φ) × sin(λ)
z = R × sin(φ)
```

These formulas might look intimidating, but we can understand exactly where they come from by breaking them down piece by piece.

### What Are Sine and Cosine?

From basic trigonometry, when you have a right triangle with an angle θ:

```
sin(θ) = opposite side / hypotenuse
cos(θ) = adjacent side / hypotenuse
```

Or rearranged:
```
opposite side = hypotenuse × sin(θ)
adjacent side = hypotenuse × cos(θ)
```

### Finding the z-coordinate (Height)

Let's start with the easiest one: **z = R × sin(φ)**

Imagine looking at the sphere from the side. You have:
- A point on the sphere at latitude φ
- A line from the center to that point (length R, the radius)
- The equatorial plane (where z = 0)

This creates a right triangle where:
- The **hypotenuse** is R (the line from center to the point)
- The **angle** from the equatorial plane is φ (the latitude)
- The **opposite side** (vertical height) is z

Using our sine formula:
```
sin(θ) = opposite side / hypotenuse
opposite side = hypotenuse × sin(θ)
z = R × sin(φ)
```

**Check:** At the equator (φ = 0°), sin(0°) = 0, so z = 0 ✓  
**Check:** At the north pole (φ = 90°), sin(90°) = 1, so z = R ✓

### Finding the x and y coordinates (The Tricky Part)

Now we need to find where the point is in the x-y plane (the equatorial plane).

**Step 1: Find the radius of the latitude circle**

When you're at latitude φ, you're not at the equator anymore. You're on a smaller circle that's "sliced" at that height. What's the radius of this circle?

Looking at the same side view:
- The **hypotenuse** is still R (the line from center to the point)
- The **angle** from the equatorial plane is still φ
- The **adjacent side** (horizontal distance from the z-axis) is this radius we're looking for

Let's call this radius **r**. Using our cosine formula:
```
cos(θ) = adjacent side / hypotenuse
adjacent side = hypotenuse × cos(θ)
r = R × cos(φ)
```

**Check:** At the equator (φ = 0°), cos(0°) = 1, so r = R (full radius) ✓  
**Check:** At the north pole (φ = 90°), cos(90°) = 0, so r = 0 (just a point) ✓

**Step 2: Use longitude to split r into x and y**

Now we have a circle of radius r in the x-y plane, and we need to find where on this circle our point is. That's what longitude λ tells us!

If we look down at the sphere from above (from the north pole), we see this circle of radius r. The longitude λ is the angle measured counterclockwise from the x-axis (which points toward 0° longitude).

Let's set up a right triangle to find the x and y coordinates:
- Draw a line from the origin to our point on the circle (length r)
- Drop a perpendicular line from the point down to the x-axis
- This creates a right triangle where:
  - The **hypotenuse** is r (the radius of our latitude circle)
  - The **angle** from the x-axis is λ (the longitude)
  - The **horizontal leg** (along the x-axis) is the x-coordinate
  - The **vertical leg** (parallel to the y-axis) is the y-coordinate

Using our trigonometry formulas:

For the **x-coordinate**:
```
cos(θ) = adjacent side / hypotenuse
```
In our triangle: θ = λ, adjacent side = x, hypotenuse = r

Substituting:
```
cos(λ) = x / r
x = r × cos(λ)
```

For the **y-coordinate**:
```
sin(θ) = opposite side / hypotenuse
```
In our triangle: θ = λ, opposite side = y, hypotenuse = r

Substituting:
```
sin(λ) = y / r
y = r × sin(λ)
```

**Check:** At λ = 0° (prime meridian), cos(0°) = 1 and sin(0°) = 0, so the point is on the x-axis ✓  
**Check:** At λ = 90°, cos(90°) = 0 and sin(90°) = 1, so the point is on the y-axis ✓

**Step 3: Substitute r = R × cos(φ)**

Remember, we found that r = R × cos(φ). Let's substitute this into our x and y formulas:
```
x = r × cos(λ) = [R × cos(φ)] × cos(λ) = R × cos(φ) × cos(λ)
y = r × sin(λ) = [R × cos(φ)] × sin(λ) = R × cos(φ) × sin(λ)
```

And there we have it! We've derived all three coordinates in terms of the sphere's radius R, latitude φ, and longitude λ.

### Summary

The conversion works in two stages:
1. **Latitude (φ) determines your height z and your distance r from the z-axis**
   - Height: z = R × sin(φ)
   - Distance from z-axis: r = R × cos(φ)
2. **Longitude (λ) determines how to split that distance r into x and y components**
   - x = r × cos(λ) = R × cos(φ) × cos(λ)
   - y = r × sin(λ) = R × cos(φ) × sin(λ)

**The complete conversion formulas:**
```
x = R × cos(φ) × cos(λ)
y = R × cos(φ) × sin(λ)
z = R × sin(φ)
```

---

**So now we have:**
- Point 1 at position (x₁, y₁, z₁)
- Point 2 at position (x₂, y₂, z₂)