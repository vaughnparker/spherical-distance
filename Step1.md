# Step 1: What Are We Actually Measuring?

## The Setup

Imagine a sphere (like a basketball or the Earth). 

Note: In the real world, the Earth is not perfectly spherical. The Earth's deviation from a perfect sphere is about 0.3%, making it an oblate spheroid, or slightly flattened at the poles and bulging at the equator. This deviation is approximately 42 km in diameter (about 27 miles), with the equatorial diameter being larger than the polar diameter.

Specifically, the Earth's equatorial radius (the distance from the surface at the equator to the center) is 6,378.1370 km, while the polar radius (the distance from the surface at the poles to the center) is 6,356.7523 km. For the purposes of this example, we will assume that the earth is a sphere with radius 6,371.0087714 km (3,958.7613160 mi).

We want to find the distance between two points **along the curved surface** - like an ant walking on the sphere, not tunneling through it. How might we go about doing this? It seems very difficult at first, but we can take advantage of a key insight.

Before we explore the key insight, let's talk about radians. A great explanation of radians can be found here: https://www.mathsisfun.com/geometry/radians.html

I'll re-hash some basic points here

## A Quick Word About Radians

You're probably used to measuring angles in **degrees** (like 90° for a right angle, 360° for a full circle). But you may remember that there is another way to measure angles called **radians**, and they can be more natural for working with circles and spheres.

### What's a Radian?

**A radian is the angle you get when the arc length equals the radius.** 1 radian is about 57.2958 degrees.

(image)

If you wrap the radius along the circle's edge, the angle it sweeps out is exactly 1 radian!

### Key Facts
- Full circle = 360° = 2π radians (about 6.28 radians)
- Half circle = 180° = π radians
- Right angle = 90° = π/2 radians

### Why Radians Are Perfect For This Problem

Here's where radians become incredibly useful. Let's build up to the key formula step by step.

**Starting with the definition:**

Remember, 1 radian is the angle where the arc length equals the radius. So:
- If the angle is 1 radian, the arc length = 1 × radius
- If the angle is 2 radians, the arc length = 2 × radius
- If the angle is 0.5 radians, the arc length = 0.5 × radius

Do you see the pattern? The arc length is always the angle (in radians) multiplied by the radius!

**The General Formula:**

```
Arc length = Radius × Angle (in radians)
```

Or more concisely:
```
s = R × θ
```

Where s is arc length, R is radius, and θ (theta) is the angle in radians.

**Why does this work?** Because of how radians are defined! A full circle has circumference 2πR, and a full circle is 2π radians. So the arc length for 2π radians is:
```
s = R × 2π = 2πR ✓
```

It checks out! The beauty is that this simple multiplication works for **any** angle, as long as it's measured in radians.

**Examples:**

1. **On a sphere with radius 10 meters:**
   - If the angle is 0.5 radians: distance = 10 × 0.5 = **5 meters**
   - If the angle is π radians (half circle): distance = 10 × 3.14159... = **31.4 meters**
   - If the angle is 0.1 radians: distance = 10 × 0.1 = **1 meter**

2. **On Earth with radius 6,371 km:**
   - If the angle is 0.01 radians: distance = 6,371 × 0.01 = **63.71 km**
   - If the angle is 1 radian: distance = 6,371 × 1 = **6,371 km**

**What if we used degrees instead?**

If you tried to use degrees, you'd need to include conversion factors. A full circle is 360°, and its arc length is 2πR, so:
```
Arc length = R × θ(degrees) × (2π/360) = R × θ(degrees) × (π/180)
```

See how messy that is? You have to remember to multiply by π/180 every single time. With radians, it's just multiplication - no extra factors needed!

**From now on:** When we write θ (theta) for an angle, we mean **radians**. This will make all our formulas cleaner and simpler.

## Key Insight

Here's the trick: **The distance along the surface is directly related to an angle at the center of the sphere.**

If you draw lines from the sphere's center to both points, they form an angle θ (theta). 

![wikipedia_angle.png](wikipedia_angle.png)

In this image, the angle is expressed as delta sigma.

## The Beautiful Relationship

```
Distance along surface = R × θ
```

Where:
- R = radius of the sphere
- θ = angle at the center **(measured in radians!)**

**Example:** If the angle is 1 radian and radius is 10 meters, the surface distance is 10 meters. If the angle between two points is 3 radians, and the radius is 10 meters, the surfaace distance is 30 meters.

---

**So our whole problem reduces to:** How do we find the angle θ between two points when we only know their positions (latitude and longitude)?