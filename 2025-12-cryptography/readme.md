# Cryptography

Means "Secret Writing" in Greek, is one of the fundamental technology of Ethereum. It is a derivative of mathematics and is heavily used in computer science.

The ethereum protocol iteself does not uses any form of encryption since data is public and nodes can verify the correctness of data and come to a consensus. Ethereum still uses various forms of cryptographic encryptions.

### Keys and Addresses

Ethereum does not store any private keys onchain, nor broadcasts it in any way. Since private key is linked to an address and the one who has that secret has the control over funds/assets, so it is essential to not make it a public secret.

Identity on ethereum is proven by digital `signatures` generated using the private key, with these signatures you get the access to an address and hence the funds. A valid digital signature is required to submit transactions on blockchain. The ownership of an address is proven using these digital signatures generated using a private key.

### PKC and Cryptocurrency

Ethereum used PKC (asymmetric cryptography) to create public-private key pair, it is called a pair because the public key is derived from the private key. Together they represent an Ethereum account and the private key controls the access by being the unique price of information needed to create digital signatures.

Example:

```It is easier to multiply 2 prime numbers and getting their result. (15 * 5 = 75)

But given the product of two large prime numbers, it is much difficult to find its prime factors: Given a number - 8,018,009

Since we have very limited information it is very hard to estimate that factor. But if we are given one piece of factor, in our case 2,003 - we can find the another factor with simple division (8,018,009 ÷ 2,003 = 4,003). Such functions are often called trapdoor functions because they are very difficult to invert unless you are given a piece of secret information that can be used as a shortcut to reverse the function.


```

### Private Keys

A simple number picked at random. Ownership and control of private key is root of user control of all funds associated witht he corrosponding Ethereum address as well as access to smart contracts authorized to that address. It must be kept a secret at all times since if it is not your keys then it is not your funds.

The process of generating private keys is offline and does not require connection to Ethereum network or any communication at all.

### Public Keys

An Ethereum public key is a point on an elliptic curve, meaning it is a set of x and y coordinates that satisfy the elliptic curve equation.

Meaning, an Ethereum public key is two numbers, joined together. In case of Ethereum, it is generated using private key.

**MATH**

The public key is calculated from private key using elliptic curve manipulation, which is practically irreversible: `K = k * G`

Where `k` is privatye key, `G` is the constant point called generator point, and `K` is resulting public key, and `*` is the special slliptic curve "multiplication" operator. This elliptic curve multiplication is not like normal multiplication.
