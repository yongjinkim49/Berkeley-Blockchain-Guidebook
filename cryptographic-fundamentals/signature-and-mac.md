# Signature and HMAC

### Digital Signature

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption><p>how do digital signatures work <a href="https://blog.mailfence.com/how-do-digital-signatures-work/">[1]</a></p></figcaption></figure>

Similar to signing a paper contract to confirm its contents and prove identity, a digital signature can both confirm the integrity of a digital content and its origin (i.e., Non-Repudiation).&#x20;

A typical scenario is that Alice sends a file (a message) to Bob via a channel, how does Bob know that the received file is the original version sent by Alice? Bob receives the file and signature, decrypts the signature with Alice's public key, gets the digital digest, and compares it with the result of digesting the file. If the result is consistent, the file is indeed sent by Alice (because no one else can have Alice's private key), and the content of the file has not been modified (the digest result is consistent).&#x20;

In theory, all asymmetric encryption algorithms can be used to implement digital signatures, but in practice, the commonly used algorithms include DSA (Digital Signature Algorithm, based on ElGamal algorithm) proposed by NIST in August 1991, and ECDSA (Elliptic Curve Digital Signature Algorithm, based on Elliptic Curve Digital Algorithm) with higher security. (based on the Elliptic Curve Digital Signature Algorithm), etc.&#x20;

In addition to the general digital signature application scenarios, some special digital signature techniques have been generated for some specific security needs, including blind signature, multiple signature, group signature, ring signature, etc.

### Message Authentication Code&#x20;

<figure><img src="../.gitbook/assets/image (42).png" alt=""><figcaption><p>Message Authentication Algorithm <a href="https://alexander.holbreich.org/message-authentication/">[2]</a></p></figcaption></figure>

Hash-based Message Authentication Code (HMAC) protects the integrity of a message using symmetric encryption.&#x20;

The basic process is to obtain a HMAC value for a message using a symmetric key shared in advance and a Hash algorithm. The holder of the HMAC value can prove to the other party that it has a symmetric key and that the contents of the transmitted message have not been tampered with.&#x20;

A typical HMAC generation algorithm consists of three parameters, K, H, and M. K is the symmetric key shared in advance, H is the agreed upon Hash algorithm (e.g., SHA-256), and M is the content of the message to be transmitted. If any of the three parameters is missing, the correct HMAC value cannot be obtained.&#x20;

Message authentication codes can be used in scenarios where simple proof of identity is required. For example, Alice and Bob share K and H in advance, Alice needs to know whether the other party is Bob, so she can send a message M to Bob, Bob calculates the HMAC value after receiving M and returns it to Alice, Alice checks the correctness of the received HMAC value to verify whether the other party is really Bob.&#x20;

Note: The example does not consider the case of man-in-the-middle attack and assumes that the channel is secure.&#x20;

The main problem with message authentication codes is the need to share the key in advance and the inability to trace the true source of the message when the key may be owned (or even leaked) by multiple parties at the same time. This problem can be effectively solved if an asymmetric encryption algorithm is used, i.e., a digital signature.
