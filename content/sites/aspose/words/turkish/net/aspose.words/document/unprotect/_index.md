---
title: Document.Unprotect
second_title: Aspose.Words for .NET API Referansı
description: Document yöntem. Paroladan bağımsız olarak belgedeki korumayı kaldırır.
type: docs
weight: 720
url: /tr/net/aspose.words/document/unprotect/
---
## Unprotect() {#unprotect_1}

Paroladan bağımsız olarak belgedeki korumayı kaldırır.

```csharp
public void Unprotect()
```

### Notlar

Bu yöntem, bir koruma parolası olsa bile belgenin korumasını kaldırır.

Belge korumasının yazma korumasından farklı olduğunu unutmayın. Yazma koruması,[`WriteProtection`](../writeprotection/).

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

* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)

---

## Unprotect(string) {#unprotect}

Doğru parola belirtilirse belgedeki korumayı kaldırır.

```csharp
public bool Unprotect(string password)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| password | String | Belgenin korumasının kaldırılacağı parola. |

### Geri dönüş değeri

Doğru parola belirtilmişse ve belge korumasızsa doğrudur.

### Notlar

Bu yöntem, yalnızca doğru bir parola belirtilmişse belgenin korumasını kaldırır.

Belge korumasının yazma korumasından farklı olduğunu unutmayın. Yazma koruması,[`WriteProtection`](../writeprotection/).

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

* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


