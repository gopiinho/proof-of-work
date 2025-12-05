# Cryptography

Means "Secret Writing" in Greek, is one of the fundamental technology of Ethereum. It is a derivative of mathematics and is heavily used in computer science.

The ethereum protocol iteself does not uses any form of encryption since data is public and nodes can verify the correctness of data and come to a consensus. Ethereum still uses various forms of cryptographic encryptions.

### Keys and Addresses

Ethereum does not store any private keys onchain, nor broadcasts it in any way. Since private key is linked to an address and the one who has that secret has the control over funds/assets, so it is essential to not make it a public secret.

Identity on ethereum is proven by digital `signatures` generated using the private key, with these signatures you get the access to an address and hence the funds. A valid digital signature is required to submit transactions on blockchain. The ownership of an address is proven using these digital signatures generated using a private key.
