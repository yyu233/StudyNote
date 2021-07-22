In short, they're both crypto key generation tools, but keytool has the additional feature of manipulating Java's preferred key storage file format, the KeyStore.

Java strongly prefers to work with keys and certificates that are stored in a KeyStore (also called a TrustStore when it's only got certificates in it). It is possible, but not trivial, to get Java to work with straightforward PEM/CER/CRT/PKCS/etc files, so for all intents and purposes if you're coding crypto in Java you're going to use a KeyStore.

Keytool is a tool that comes with Java that works with KeyStores - it can create KeyStores and manipulate keys and certificates inside them. It can also create keys and sign certificates. So it is both a key generation and a KeyStore-file-administration tool.

OpenSSL works with standard formats (PEM/CER/CRT/PKCS/etc) but does not manipulate KeyStore files. It is possible to generate a key and/or certificate with OpenSSL, and then import that key/cert into a KeyStore using keytool, but you can't put the key/cert into the KeyStore directly using OpenSSL.

(OpenSSL also has a wider array of functionality than keytool - performing symmetric encryption, acting as an SSL network client and server, handling more formats. It just doesn't happen to speak KeyStore.)
