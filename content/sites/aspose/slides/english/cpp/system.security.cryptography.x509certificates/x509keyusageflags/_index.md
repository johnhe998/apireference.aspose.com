---
title: X509KeyUsageFlags
second_title: Aspose.Slides for C++ API Reference
description: Defines how the certificate key can be used.
type: docs
weight: 274
url: /cpp/system.security.cryptography.x509certificates/x509keyusageflags/
---
## X509KeyUsageFlags enum


Defines how the certificate key can be used.

```cpp
enum class X509KeyUsageFlags : int32_t
```

### Values

| Name | Value | Description |
| --- | --- | --- |
| None | 0 | No key usage parameters. |
| EncipherOnly | 1 | Key can be used only for encryption. |
| CrlSign | 2 | Key can be used to sign a certificate revocation list. |
| KeyCertSign | 4 | Key can be used to sign certificates. |
| KeyAgreement | 8 | Key can be used to determine key agreement. |
| DataEncipherment | 16 | Key can be used for data encryption. |
| KeyEncipherment | 32 | Key can be used for key encryption. |
| NonRepudiation | 64 | Key can be used for authentication. |
| DigitalSignature | 128 | Key can be used as a digital signature. |
| DecipherOnly | 32768 | Key can be used only for decryption. |

## See Also

* Namespace [System::Security::Cryptography::X509Certificates](../)
* Library [Aspose.Slides](../../)