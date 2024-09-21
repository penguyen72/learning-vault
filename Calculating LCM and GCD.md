### Formula
$$
a \times b = LCM(a, b) \times GCD(a, b)
$$
## Calculating GCD of two numbers
### Example:
$$
\underline{270\text{ and }192}
$$
$$
270 = 1 \times 192 + 78
$$
$$
192 = 2 \times 78 + 36
$$
$$
78 = 2 \times 36 + 6
$$
$$
36 = 6 \times 6 + 0
$$
$$
OR
$$
$$
270 \text{ mod } 192 = 78
$$
$$
192 \text{ mod } 78 = 36
$$
$$
78 \text{ mod } 36 = 6
$$
$$
36 \text{ mod } 6 = 0
$$
```python
def gcd(a, b):
	if b == 0:
		return a
	return gcd(b, a % b)
```

## Calculating LCM of two numbers
We can calculate the LCM using the initial formula modifying it to:
$$
LCM(a, b) = \frac{a \times b}{GCD(a, b)}
$$