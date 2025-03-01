p1 and p2 have v1 and v2. Total energy = T, desired energy = D

T = (1/2)m1|v1|^2 + (1/2)m2|v2|^2 
T = (1/2)m1(vx1^2 + vy^2) + (1/2)m2(vx^2 + vy^2)

how to adjust vx1, vy1, vx2, vy2 to make T' = D

Conserve momentum:
Px = m1vx1 + m2vx2
Py = m1vy1 + m2vy2

m1vx1 + m2vx2 = m1vx1' + m2vx2'
Which is easy to solve:

let vx1' = vx1 + a
m1vx1 + m2vx2 = m1vx1 + m1a + m2vx2
vx2' = vx2 + (m1 a / m2)

Ditto for y, so

vy1' = vy1 + b
vy2' = vy2 + (m1 b / m2)

Solve for a and b

T' = (1/2)m1(vx1'^2 + vy1'^2) + (1/2)m2(vx2'^2 + vy2'^2)
T' = (1/2)m1((vx1 + a)^2 + (vy1 + b)^2) + (1/2)m2((vx2 + (m1 a / m2))^2 + (vy2 + (m1 b / m2))^2)
T' = (1/2)m1(vx1^2 + 2vx1a + a^2 + vy1^2 + 2vy1b + b^2) + (1/2)m2(vx2^2 + 2vx2m1a/m2 + m1^2a^2/m2^2 + vy2^2 + 2vy2m1b/m2 + m1^2b^2/m2^2)
T' = (1/2)(m1vx1^2 + m12vx1a + m1a^2 + m1vy1^2 + m12vy1b + m1b^2 + m2vx2^2 + 2vx2m1a + m1^2a^2/m2 + m2vy2^2 + 2vy2m1b + m1^2b^2/m2)
```
2*D = m1*vx1^2 + m1*2*vx1*a + m1*a^2 + m1*vy1^2 + m1*2*vy1*b + m1*b^2 + m2*vx2^2 + 2*vx2*m1*a + m1^2*a^2/m2 + m2*vy2^2 + 2vy*2*m1*b + m1^2*b^2/m2
```
