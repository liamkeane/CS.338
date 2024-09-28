# Being Eve : Liam Keane

### What we know:
- Alice and Bob agree on $g = 7$ and $p = 97$.

- Alice sent Bob the number $53$.

- Bob sent Alice the number $82$.

### Figure out the shared secret agreed upon by Alice and Bob. This will be an integer. Show your work and show where in the process you would have failed if the integers were much larger.

Alice sent Bob $53$, meaning she calculated some random a such that there exists some $a$ where $$53 = 7^a \bmod 97$$ and Bob sent Alice $82$,
meaning there exists some $b$ where $$82 = 7^b \bmod 97$$

If we run the following script to calculate $a$ and $b$,

```python
for i in range(97):
	print(7**i % 97)
```
we see that the $22^{nd}$ and $41^{st}$ iterations result in $53$ and $82$ respectively, meaning the correspond to our $a$ and $b$ values.

From there we can calulate the shared $K$ value using the following two equations
$$82^{22} \bmod 97 = 65 = 53^{41} \bmod 97$$
Therefore $K = 65$. It would not have been feasible to compute the values of $a$ and $b$ if $g$ and $p$ were signifigantly larger numbers. In this case it only takes $97$ iterations to calculate $a$ and $b$, so
it is quite easy to crack.

---

### What we know:
- Bob's public key: $e = 13$ and $n = 162991$
- Alice's encrypted message: $[17645, 100861, ... , 128221]$

### Figure out the encrypted message sent from Alice to Bob. how the message from Alice to Bob encoded? Why is this not secure by itself? Where would you have failed if the integers were much larger?

Plugging our $n$ into this factoring calculator, the only two numbers not $1$ and $162991$ were $389$ and $419$, which means they must be our $p$ and $q$ values.

With that we can brute force the integer for $d$ using the following script

```python
count = 0
e = 388 * 418 # Our p and q
while(1):
    print("checking...", count)
    if (13 * count) % e == 1:
        print("d is", count)
        break
    count += 1
```

which yield our $d$ value of $124757$. Note that if $p$ and $q$ were much larger, it would have been infeasible to compute $d$ using this brute force method.

From there we can use $d$ to decrypt Alice's message to Bob using the following formula
$$C^{124757} \bmod 162991 = M$$
which we apply to each integer in Alice's cipher using the following script

```python
decrypted = []

for integer in encrypted:
    decrypted.append(hex(integer**124757 % 162991))
```
this yields a sequence of four digit hex numbers, meaning each 'token' corresponds to two ASCII values concatenated together, which is not a secure encoding without Bob's encryption layered on top of it.

With that I concatenated all of the hex numbers together, and I converted that string into ASCII plaintext using the following script

```python
bytes.fromhex("4465617220426f622c20636865636b2074686973206f75742e2068747470733a2f2f7777772e7375727665696c6c616e636577617463682e696f2f20536565207
9612c20416c6963652e").decode('ascii')
```
which when printed reveals the following message: 'Dear Bob, check this out. https://www.surveillancewatch.io/ See ya, Alice.' The website itself is actually quite cool.