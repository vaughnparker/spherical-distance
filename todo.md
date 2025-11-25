## Section 1

- why is full circle = 360 degrees?
- get image for radians
- note that the diagram shows an angle of delta sigma, not theta
- maybe explain why we are using theta... DEFINITELY explain why we are using lambda + phi for longitude / latitude
- "surfaace"
	- this whole example kind of sucks, please replace

overall, whole section is a bit repetitive. Maybe let's derive radians from C = 2*pi*r ? not sure


## Section 2
- why longitude/latitude, why greek letters
- fix negatives in "real world location" example
- make seperate page for "real world latitude/longitude guessing game"
- add image for earth x y z axes
- MAYBE consider deriving the formulas first, then listing them out for xyz conversion

cos(θ) = adjacent side / hypotenuse
adjacent side = hypotenuse × cos(θ)
r = R × cos(φ)

- let's rewrite this. 1) we want to start with the formula. 2) we want to substitute in variables. 3) we want to do algebra to isolate the variable we want (in this case r). Let's make this change for the other formulas as well.

---

If we look down at the sphere from above (from the north pole), we see this circle of radius r, and longitude λ is the angle measured from the x-axis.

For a point on a circle of radius r at angle λ:

The x-coordinate is: r × cos(λ)
The y-coordinate is: r × sin(λ)

---

this is a bit too fast. We have a circle of radius r, and we know longitude lambda. Now let's set up a circle/triangle setup to understand why the x coordinate is r x cos(lambda)

## Section 3

- good proof of dot product formula, maybe add appendix: https://math.stackexchange.com/questions/3784740/proof-of-dot-product-formula

## Section 4

- let's put the cosine difference formula as an addendum. "If you look up the formula for spherical distance, you might notice that it looks slightly different. Using the cosine difference formula (a trig identity) we can simplify the formula a bit more."

# 2025-11-24 potential extensions

potential extensions:

## Step 1
* "you can easily look up their coordinates"
  * How could we do this, from first principles?
* "The shortest path between two cities follows the curved surface of the Earth, not a straight line through the planet."
  * clarity of language here - the shortest path geometrically is actually a striaght line through the planet.
* "On a sphere with radius 10 meters:"
  * this example sucks
* "On Earth with radius 6,371 km:"
  * this example is slightly better but still lacks connection to real world examples. Maybe we should use some examples like "two cities a degree apart are __ and __" or "halfway around the world is pi radians and __ km"
* MAYBE consider ending step 1 with a "in step 2 we will..."

## Step 2
* "Now, to calculate distances between points on a sphere, we need to work with angles. The easiest way to do this is to convert our latitude/longitude coordinates into 3D space using x, y, z coordinates."
  * this isn't necessarily obvious. Latitude and longitude are already in angles, why would we convert to rectangular coords?
* "From basic trigonometry, when you have a right triangle with an angle θ:"
  * Rephrase this - "with an angle theta" could be a bit clearer. Maybe invoke a diagram. Instead of relying on the reader's knowledge with basic trig, let's remind them that this is not a fun fact about the sin/cos functions but actaully *how they are defined*.
* MAYBE consider ending step 2 with a "in step 3 we will..."

## Step 3
* get a better variable than "chord". The full word "chord" is descriptive but feels out of place
* in step 1 we say: s = R × θ
	* in step 3 we say: d = R × θ
	* let's standardize this

## Step 4
* we don't want to end with "the haversine formula". we want to end with the spherical distance formula that we actually use in step 5.
	* currently in step 5 we are using: cos(θ) = sin(φ₁) × sin(φ₂) + cos(φ₁) × cos(φ₂) × cos(Δλ)
	* we need to update that in step 5.
