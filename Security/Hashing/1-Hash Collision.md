A hash collision is when two different inputs give the same output. Hash functions are designed to avoid collisions as best as possible. Furthermore, hash functions are designed to prevent an attacker from being able to create, i.e., engineer, a collision intentionally.

However, because the number of inputs is practically unlimited and the number of possible outputs is limited, this leads to a pigeonhole effect.

As a numeric example, if a hash function produces a 4-bit hash value, we only have 16 different hash values. The total number of possible hash values is 2^number_of_bits_ = 2^4 = 16. 
The probability of a collision is relatively very high.

The **pigeonhole effect** states that the number of items (_pigeons_) is more than the number of containers (_pigeonholes_); 

some containers must hold more than one item. In other words, in this context, there are a fixed number of different output values for the hash function, but you can give it any size input. 

As there are more inputs than outputs, some inputs must inevitably give the same output. 

If you have 21 pigeons and 16 pigeonholes, some of the pigeons are going to share the pigeonholes. 

Consequently, collisions are unavoidable. However, a good hash function ensures that the probability of a collision is negligible.

MD5 and SHA1 have been attacked and are now considered insecure due to the ability to engineer hash collisions. 

However, no attack has yet given a collision in both algorithms simultaneously, so if you compare the MD5 and SHA1 hash, you will see that they’re different. 

You can view the MD5 collision example on the [MD5 Collision Demo](https://www.mscs.dal.ca/~selinger/md5collision/) page; furthermore, you can read the details of the SHA1 collision attack at [Shattered](https://shattered.io/). Due to these, you shouldn’t trust either algorithm for hashing passwords or data.