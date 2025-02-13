---
title: CertificateHolder.Certificate
second_title: Aspose.Words لمراجع .NET API
description: CertificateHolder ملكية. إرجاع مثيل X509 شهادة 2 الذي يحمل المفاتيح الخاصة والعامة وسلسلة الشهادات.
type: docs
weight: 20
url: /ar/net/aspose.words.digitalsignatures/certificateholder/certificate/
---
## CertificateHolder.Certificate property

إرجاع مثيل **X509 شهادة 2** الذي يحمل المفاتيح الخاصة والعامة وسلسلة الشهادات.

```csharp
public X509Certificate2 Certificate { get; }
```

### قيمة الإرجاع

X509Certificate2 نموذج

### أمثلة

يوضح كيفية التحقق من صحة المعلومات وعرضها حول كل توقيع في مستند.

```csharp
Document doc = new Document(MyDir + "Digitally signed.docx");

foreach (DigitalSignature signature in doc.DigitalSignatures)
{
    Console.WriteLine($"{(signature.IsValid ? "Valid" : "Invalid")} signature: ");
    Console.WriteLine($"\tReason:\t{signature.Comments}"); 
    Console.WriteLine($"\tType:\t{signature.SignatureType}");
    Console.WriteLine($"\tSign time:\t{signature.SignTime}");
    Console.WriteLine($"\tSubject name:\t{signature.CertificateHolder.Certificate.SubjectName}");
    Console.WriteLine($"\tIssuer name:\t{signature.CertificateHolder.Certificate.IssuerName.Name}");
    Console.WriteLine();
}
```

### أنظر أيضا

* class [CertificateHolder](../)
* مساحة الاسم [Aspose.Words.DigitalSignatures](../../certificateholder/)
* المجسم [Aspose.Words](../../../)


