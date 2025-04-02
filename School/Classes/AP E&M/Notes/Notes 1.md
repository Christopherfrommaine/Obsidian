
From this video: https://www.youtube.com/watch?v=DqYl42JtaQg
# Electricity
## Coulomb's Law 

Just like gravity: proportional to the values and inversely proportional to distance. Fundamental equation for *electric* force.
$$F_e = \frac{kq_1q_2}{r^2}$$
### Positive and Negative
Because multiplication can cancel out negatives, the strength of the force can be positive, indicating that the two charged objects attract, or negative, indicating that they repel.

### Example
For example, let's find the force between a particle with charge 2 and a particle with charge -5 which is two units away. Plugging in numbers, we get that the total force is:
$$-k\frac{10}{4}$$
Because it is negative, it means that the two particles will attract each other (which matches our intuition: opposites attract).

## Electric Field

An electric field is just a vector field showing the force on a unit charge.

For a particle at (a, b), it's electric field is given by
$$\overrightarrow{E}(x, y) = (\langle x, y \rangle - \langle a, b \rangle) \frac{kq}{|\langle x, y \rangle - \langle a, b \rangle| ^ 3} $$
Note that the power of three is used instead of squaring to also normalize the vector in the front.
This takes Coulomb's law, and directs it using the normalized difference.

If you look up some diagrams online, a positive charge will be a bunch of arrows pointing away, and a negative charge will make a bunch of arrows point toward it.

### More Particles
Electric fields add. If you want to find the total electric field of anything but a point particle, you can just split it up into charges and add those up.

#### Conjecture
(Conjecture is guesses that I'm making. It's always good to try to think ahead, so that's what I'm doing.)
Electric field of a compound object will be an integral over the entire object of the field at that point. I.e.
$$\overrightarrow{E}(x, y) = \iiint_O(\langle x, y \rangle - \langle a, b \rangle) \frac{kq}{|\langle x, y \rangle - \langle a, b \rangle| ^ 3}dxdydz $$
### Flux
How much a vector field "flows" through a given area.
Larger area, larger flux. Pointed directly at the flow, more flux; perpendicular to the flow, no flux.
(We're using a directed area to represent a portion of a plane.)
Flux is represented by Phi. With a vector field W, and directed area A, flux is:
$$\Phi=\overrightarrow{W}.\overrightarrow{A}$$
Again, if you want to compute something other than a plane, use an integral.

### Electric Flux Example

#### Conjecture

Take a particle at the origin with a charge of 5. Compute the flux on the unit sphere around the particle. We need to use an integral over the sphere:
$$\Phi=\int_0^{2 \pi}\int_0^\pi\overrightarrow{E}(x, y, x).(\langle x, y, x \rangle sin(\theta)d\theta d\phi)$$
You see the field strength, and the directed area (the unit vector pointing along a radius, and the integral formula for the surface area of a sphere). Now, plug in
$$x=sin\theta cos\phi, y=sin\theta sin\phi, z=cos\theta$$$$\Phi=\int_0^{2 \pi}\int_0^\pi\overrightarrow{E}(sin\theta cos\phi, sin\theta sin\phi, cos\theta).(\langle sin\theta cos\phi, sin\theta sin\phi, cos\theta \rangle sin(\theta)d\theta d\phi)$$If you plug in for E, you see that the distance remains constant, so it's magnitude remains constant, as well as it's angle to it's dot product, so we can use the dot product formula, take out magnitude, and just multiply the flux density by the surface area of a sphere.

### Contour Integral
Defined as an integral over a parameterized curve in the complex plane:
$$\text{symbol: } \oint_r, \text{where } r: [a, b] \to \mathbb{C}$$
### Correct Method

The magnitude of the field is constant. Thus, you can remove it from the integral. The magnitude is `5k`. Now, multiply that by the surface area of a sphere: `4 pi r^2`. Your final answer is:
$$20 k \pi$$

### Gauss's Law
A generalization of what we just did.
Flux over a sphere is given by:

$$\Phi_E = \frac{kq}{r^2}4\pi r^2=4\pi k q$$
If we let k be equal to a new constant 4 pi/epsilon_0, we get:
$$\Phi = \frac{q}{\epsilon_0}$$
Even better, this equation above applies for ANY CLOSED SURFACE.
Think about what flux is for a second, and this makes sense. It's like the total flow over an area. If a flow is completely surrounded, then it's flux will always be the same, no matter how it is surrounded.

### Properties
Because charges add, given our flux equation, enclosed flux also adds.
Charges outside enter the area, but also then exit the area, cancelling out.

So Gauss's law can be written:
$$\Phi = \frac{q_{enclosed}}{\epsilon_0}$$
### Example
Large sheet of charges with total charge Q and total area A.
Find the flux on a cylinder through it with radius R.

Charge density (sigma):
$$\sigma = \frac{Q}{A}$$
Total cylinder area:
$$\pi R^2$$
Enclosed charge:
$$\pi R^2 \frac{Q}{A}$$
Flux:
$$\Phi = \overrightarrow{E}.\overrightarrow{A}=2\pi R^2\overrightarrow{E}$$
Equation:
$$\Phi = 2\pi R^2\overrightarrow{E}=\frac{\pi R^2 \frac{Q}{A}}{\epsilon_0}$$
$$\overrightarrow{E}=\frac{\pi R^2 \frac{Q}{A}}{\epsilon_0 2\pi R^2}$$
$$\overrightarrow{E}=\frac{\frac{Q}{A}}{2\epsilon_0}$$
Cool, a final result!

## Voltage
Potential energy for charge.

### Work
Recall work:
$$W = \int \overrightarrow{F}(x) \cdot \overrightarrow{dx}$$

Potential energy is "negative work". E.g. a ball being pulled upwards against gravity means that gravity is doing negative work, and thus the ball's potential energy increases.

$$U = - \int \overrightarrow{F}(x) \cdot \overrightarrow{dx}$$
### Work of Coulomb Force

Let rhat be the unit vector in the direction of r. dx becomes r * rhat
$$ U = -\int \frac{k q_1 q_2}{r^2}\hat{r} \cdot dr\hat{r}$$

For absolute potential energy, start infinitely far away and come into a distance R:
$$ U = -\int_\infty^R \frac{k q_1 q_2}{r^2}\hat{r} \cdot dr\hat{r}$$
$$ U = -\int_\infty^R \frac{k q_1 q_2}{r^2} dr$$
$$ U = k q_1 q_2 \big|_\infty^R \frac{1}{r}$$
$$ U = \frac{k q_1 q_2}{R}$$

### Definition of Voltage
Voltage is potential energy per unit charge. Just like the electric field asks about the force on a unit charge at a specific point, the voltage at a specific point is the potential energy of a unit charge. From the above equation:

$$V = \frac{k q}{R}$$

### Fields and Voltage
Alternatively, (by adding a 1/q to the original integral form), we get:
$$V = \int \overrightarrow{E} \cdot \overrightarrow{dx}$$
This means that when you move a charge against an electric field, you get potential energy (just like moving a mass against a gravitational field gives you energy).

When you see a field diagram with lines perpendicular to the field, these are called "equipotential lines" because moving from one point to another is perpendicular to the force, so there is no change in work.

Voltage is relative.

## Overview
![[Pasted image 20250301120405.png]]

# Circuits
## Current
Current is a measure of the "flow". I.e. the amount of electrons moving through a wire.
If you take the amount of charge that has moved through divided by the amount of time passed, you get:
$$I = \frac{\Delta Q}{\Delta t} $$
Alternatively, you can define it in terms of the area of the wire A, the velocity of the electrons v, the number of electrons n, and the charge of each electron:
$$I = n q A v$$

## Resistance
Resistance measures how much of an effect voltage has on current. If you increase the resistance, then you need a greater voltage (potential difference) to achieve the same flow (current). Thus, we get the law:

### Ohm's Law
$$V = I R$$

### Parallel vs Series
If you have two resistors in parallel, they add together. If you have two in series, then you're effectively adding more ways for electrons to path through, so resistance decreases.

$$ R \propto \text{length of the net resistor}$$
$$R \propto 1 / \text{area of the net resistor}$$

### POWAH

Ditto for mechanics, just energy over time.
$$P = \frac{dU}{dt}$$

But we can also write it as current times voltage:
$$P = \frac{dU}{dt} = \frac{dU}{dQ} \frac{dQ}{dt} = V I$$

Replacing with Ohm's law:
$$P = V I = V \frac{V}{R} = \frac{V^2}{R}$$
## Complicated Circuits
If you need to find the current flowing through two resistors, it may be tricky. Recall:
Charge is conserved (I_1 + I_2 = I_total)
Energy is conserved (delta V_1 = delta V_2)

However, you may also need to use these equations:
#### Kirchhoff Equations
##### Junction Rule
When two wires meet, total charge is conserved. If I_1 and I_2 are inputs, and I_3 and I_4 are outputs,
$$I_1 + I_2 = I_3 + I_4$$

##### Loop Rule
If you start and end in the same place, you should have no change in potential energy. In other words, the voltage from a battery minus the total voltage drop from resistance is zero:
$$V - I R = 0$$

## Capacitors

$$C = \frac{Q}{V}$$
where V is the voltage across the capacitor.

Given a circuit with a battery, capacitor, and some resistance:
$$V - \frac{Q}{C} - I R = 0$$
$$V - \frac{Q}{C} - \frac{dQ}{dt} R = 0$$
This is a differential equation, which can be solved.
$$Q(t) = V C (1 - e^\frac{-1}{RC})$$

### Parallel vs Series
For capacitors, it works the OPPOSITE way!

$$ C \propto 1 / \text{seperation of the net capacitor}$$
$$C \propto \text{area of the net capacitor}$$

so in series, they add, and in parallel, the value is the reciprocal of the sum of their reciprocals.

### Energy of a Capacitor
$$U = \frac{1}{2} C V^2$$
## AC Circuits

### Voltage
Instead of real voltage over time (which would always be zero), we square it, then sum, then take the sqrt. Called the Root Mean Squared (RMS) voltage.

### Capacitors
In very low frequency, they act like DC.
In higher frequency, where they don't have enough time to charge up,
$$V_0 = I_0 \frac{1}{\omega C}$$
where omega is the frequency, V_0 is the voltage of the capacitor, etc.
We call this value Reactance:
$$X = \frac{1}{\omega C}$$
### Impedance
$$Z = \sqrt{X^2 + R^2}$$
$$V_\text{rms} = I_\text{rms} Z $$
# Magnetism
A magnetic field describes the force on a north pole.

Magnetic field, where B is a small section of the magnetic field, and dl points along the wire, and r is from that piece of the wire to B:
$$d\overrightarrow{B} = \frac{\mu_0}{4 \pi} \frac{I d\overrightarrow{l} \times \hat{r}}{r^2}$$

### Right Hand Rules
Index is current flow (along the wire), middle is towards the position on the field, thumb is B.

Also,
Thumb is current flow, fingers will twist around along magnetic field lines.

## Magnetic Force
$$\overrightarrow{F}_M = q \overrightarrow{v} \times \overrightarrow{B}$$

Because of this, charges move in a helical path around a constant magnetic field.


### Flux
The magnetic flux for any closed surface is 0

$$ V = -\frac{d \Phi_B}{dt}$$
for a looped path.


### Todo: magnetism needs more understanding

## Overview
![[Pasted image 20250301140757.png]]

# Electromagnetism
