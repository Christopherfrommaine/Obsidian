Use arbitrary-length integers


```
step(uint) -> uint
lifetime(uint, max) -> uint

for i in integers:
	e.g. i = 0b100110

	// transform into ith state integer
	0b100110011001  == i.rev() >> i.leading_zeros() | i << (1 + ilog2(i))
	0b10011011001   == i.rev() >> i.leading_zeros() | i << ilog2(i)

	// filtering
	if lifetime()

```