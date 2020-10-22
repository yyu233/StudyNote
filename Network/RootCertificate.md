```
The root certificate, often called a trusted root, is at the center of the trust model that undergirds Public Key Infrastructure, and by extension SSL/TLS. Let’s start by discussing root programs and work our way out from there.

Every device includes something called a root store. A root store is a collection of pre-downloaded root certificates (and their public keys) that live on the device itself. Generally, the device will use whatever root store is native to its OS, otherwise it might use a third-party root store via an app like a web browser. There are several major root programs of note:

Microsoft
Apple
Google
Mozilla
```
