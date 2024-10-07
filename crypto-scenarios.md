# Crypto-scenarios assignment
Liam Keane

## Simple communication scenarios
1. Alice and Bob agree on a shared secret K. Encrypt Alice's message M using AES(K, M) which yields the cipher C. Bob then decrypts the original message using AES_D(K, C). Eve cannot perform the same operation because she does not have access to the shared secret K.
2. Alice sends C = E(S_A, M) to Bob who is able to decrypt it using Alice's public key where M = E(P_A, C). Mal is not able to interfere with the message without Bob knowing because it was signed with Alice's private key.
3. Alice and Bob agree on a shared secret K. Alice sends C = AES(K, E(S_A, M)) to Bob. Bob then decrypts the message into C' using AES_D(K, C), then decrypts C' into the original message M using E(P_A, C'). Eve cannot read the messages because they have been encrypted using a shared secret and Bob can be confident that Alice sent the message since it was signed with her private key.

## Questions about breaking security
4. Alice can claim that the message C had been tampered with by an AITM. If (C) != E(P_A, Sig), then that would be great evidence for a jury. If not, Alice could claim an AITM computed the secret shared value, which should not be very convincing for the jury given the computing time required. Perhaps Alice could also show that her private key had been exposed somehow, which should instill some doubt in a jury, but it would not be as convincing as the first possibility.
5. Sig_CA = Bob's metadata || E(S_CA, H(Bob's metadata))
6. Bob could sign his message and certification with his private key.
7. The certificate system itself could become compromised, allowing Mal to claim to be Bob. There could also be an AITM between Bob and the certificate system, allowing Mal to gain possession of Bob's certificate.




