# Step 2: Putting Points in 3D Space

## From Latitude/Longitude to X, Y, Z

When you describe a point on Earth, you use:
- **Latitude (φ)**: how far north/south (0° at equator, 90° at north pole, -90° or 90°S at south pole)
- **Longitude (λ)**: how far east/west (0° at prime meridian, ranges from -180° to 180°, or 0° to 360°)

### Examples of Real-World Locations

Here are 10 well-known locations with their approximate coordinates:

1. **New York City, USA**: 40.7°N, -74.0°W (or 40.7°, -74.0°)
2. **London, UK**: 51.5°N, -0.1°W (or 51.5°, -0.1°)
3. **Tokyo, Japan**: 35.7°N, 139.7°E (or 35.7°, 139.7°)
4. **Sydney, Australia**: -33.9°S, 151.2°E (or -33.9°, 151.2°)
5. **Rio de Janeiro, Brazil**: -22.9°S, -43.2°W (or -22.9°, -43.2°)
6. **Cairo, Egypt**: 30.0°N, 31.2°E (or 30.0°, 31.2°)
7. **Mumbai, India**: 19.1°N, 72.9°E (or 19.1°, 72.9°)
8. **Cape Town, South Africa**: -34.0°S, 18.4°E (or -34.0°, 18.4°)
9. **Moscow, Russia**: 55.8°N, 37.6°E (or 55.8°, 37.6°)
10. **Mexico City, Mexico**: 19.4°N, -99.1°W (or 19.4°, -99.1°)

**Note:** In mathematical formulas, we typically use the convention where north latitudes are positive, south latitudes are negative, east longitudes are positive, and west longitudes are negative.

But to find angles, it's easier to describe where the point is in **3D space** using x, y, z coordinates.

## The Conversion

We need to set up a 3D coordinate system. Imagine the sphere centered at the origin (the point 0, 0, 0) with radius R:

**Our coordinate system:**
- The **z-axis** points straight up through the North Pole
- The **x-axis** points out through the intersection of the equator and the prime meridian (0° longitude)
  - This point is in the Atlantic Ocean off the coast of West Africa in the Gulf of Guinea, south of Ghana
- The **y-axis** points out through the intersection of the equator and 90°E longitude
  - This point is in the Indian Ocean, west of Sumatra, Indonesia
- The center of the sphere is at the origin (0, 0, 0)

In this coordinate system, any point on Earth's surface can be described by three numbers (x, y, z), where each represents the distance along that axis from the origin.

**Our goal:** Convert from the familiar latitude/longitude system to this x, y, z system.

For a point at latitude φ and longitude λ, the conversion formulas are:

```
x = R × cos(φ) × cos(λ)
y = R × cos(φ) × sin(λ)
z = R × sin(φ)
```

These formulas might look intimidating, but we can understand exactly where they come from by breaking them down piece by piece.

## The Conversion Formulas

For a point at latitude φ and longitude λ:

```
x = R × cos(φ) × cos(λ)
y = R × cos(φ) × sin(λ)
z = R × sin(φ)
```

Let's break this down very carefully.

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

If we look down at the sphere from above (from the north pole), we see this circle of radius r, and longitude λ is the angle measured from the x-axis.

For a point on a circle of radius r at angle λ:
- The **x-coordinate** is: r × cos(λ)
- The **y-coordinate** is: r × sin(λ)

**Step 3: Substitute r = R × cos(φ)**

```
x = r × cos(λ) = [R × cos(φ)] × cos(λ) = R × cos(φ) × cos(λ)
y = r × sin(λ) = [R × cos(φ)] × sin(λ) = R × cos(φ) × sin(λ)
```

And there we have it!

### Summary

The conversion works in two stages:
1. **Latitude (φ) determines your height z and your distance r from the z-axis**
2. **Longitude (λ) determines how to split that distance r into x and y components**

---

**So now we have:**
- Point 1 at position (x₁, y₁, z₁)
- Point 2 at position (x₂, y₂, z₂)