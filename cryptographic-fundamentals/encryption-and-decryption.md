# Encryption and Decryption

Encryption and decryption algorithms are the core technology of modern cryptography, which can be divided into two basic types in terms of design concepts and application scenarios: symmetric encryption and asymmetric encryption, as shown in the following table:

| Type                              | Characteristic                                   | Pros                                                       | Cons                                                                       | Algorithms                                |
| --------------------------------- | ------------------------------------------------ | ---------------------------------------------------------- | -------------------------------------------------------------------------- | ----------------------------------------- |
| Symmetric                         | The encryption and decryption keys are the same  | High computational efficiency and high encryption strength | Need to share the key in advance                                           | DES、3DES、AES、IDEA ...                     |
| Asymmetric (public & private key) | The encryption and decryption keys are different | No need to share keys in advance                           | Low computational efficiency, the possibility of man-in-the-middle attacks | <p>RSA, ElGamal, DSA, ECDSA</p><p>...</p> |
|                                   |                                                  |                                                            |                                                                            |                                           |
