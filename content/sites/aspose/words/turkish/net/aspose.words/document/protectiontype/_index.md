---
title: Document.ProtectionType
second_title: Aspose.Words for .NET API Referansı
description: Document mülk. Şu anda etkin olan belge koruma türünü alır.
type: docs
weight: 310
url: /tr/net/aspose.words/document/protectiontype/
---
## Document.ProtectionType property

Şu anda etkin olan belge koruma türünü alır.

```csharp
public ProtectionType ProtectionType { get; }
```

### Notlar

Bu özellik, geçerli olarak ayarlanmış belge koruma türünün alınmasını sağlar. Belge koruma türünü değiştirmek için[`Protect`](../protect/) ve[`Unprotect`](../unprotect/)yöntemler.

Bir belge korunduğunda, kullanıcı yalnızca sınırlı değişiklikler yapabilir, , örneğin ek açıklamalar ekleme, düzeltmeler yapma veya bir formu doldurma gibi.

Belge korumasının yazma korumasından farklı olduğunu unutmayın. Yazma koruması,[`WriteProtection`](../writeprotection/)

### Örnekler

Bir belgenin nasıl korunacağını ve korumasının nasıl kaldırılacağını gösterir.

```csharp
Document doc = new Document();
doc.Protect(ProtectionType.ReadOnly, "password");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// Bu belgeyi düzenlemek için Microsoft Word ile açarsak,
// Korumadan geçmek için şifreyi uygulamamız gerekecek.
doc.Save(ArtifactsDir + "Document.Protect.docx");

// Korumanın yalnızca belgemizi açan Microsoft Word kullanıcıları için geçerli olduğunu unutmayın.
// Belgeyi hiçbir şekilde şifrelemedik ve programlı olarak açıp düzenlemek için şifreye ihtiyacımız yok.
Document protectedDoc = new Document(ArtifactsDir + "Document.Protect.docx");

Assert.AreEqual(ProtectionType.ReadOnly, protectedDoc.ProtectionType);

DocumentBuilder builder = new DocumentBuilder(protectedDoc);
builder.Writeln("Text added to a protected document.");
// Bir belgeden korumayı kaldırmanın iki yolu vardır.
// 1 - Şifresiz:
doc.Unprotect();

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);

doc.Protect(ProtectionType.ReadOnly, "NewPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

doc.Unprotect("WrongPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// 2 - Doğru şifre ile:
doc.Unprotect("NewPassword");

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);
```

### Ayrıca bakınız

* enum [ProtectionType](../../protectiontype/)
* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


