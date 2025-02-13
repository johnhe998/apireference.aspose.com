---
title: Document.Protect
second_title: Aspose.Words for .NET API Referansı
description: Document yöntem. Mevcut parolayı değiştirmeden veya rastgele bir parola atamadan belgeyi değişikliklerden korur.
type: docs
weight: 630
url: /tr/net/aspose.words/document/protect/
---
## Protect(ProtectionType) {#protect}

Mevcut parolayı değiştirmeden veya rastgele bir parola atamadan belgeyi değişikliklerden korur.

```csharp
public void Protect(ProtectionType type)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| type | ProtectionType | Belge için koruma türünü belirtir. |

### Notlar

Bir belge korunduğunda, kullanıcı yalnızca sınırlı değişiklikler yapabilir, , örneğin ek açıklamalar ekleme, düzeltmeler yapma veya bir formu doldurma gibi.

Bir belgeyi koruduğunuzda ve belgenin zaten bir koruma parolası olduğunda, mevcut koruma parolası değiştirilmez.

Bir belgeyi koruduğunuzda ve belgenin koruma parolası yoksa, bu yöntem, Microsoft Word'de belge korumasını kaldırmayı imkansız kılan rastgele bir parola atar, ancak yine de Aspose.Words'de belgenin korumasını kaldırabilirsiniz, çünkü yoktur. korumayı kaldırırken bir parola gerektirir.

### Örnekler

Bir bölüm için korumanın nasıl kapatılacağını gösterir.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Section 1. Hello world!");
builder.InsertBreak(BreakType.SectionBreakNewPage);

builder.Writeln("Section 2. Hello again!");
builder.Write("Please enter text here: ");
builder.InsertTextInput("TextInput1", TextFormFieldType.Regular, "", "Placeholder text", 0);

// Belgedeki her bölüme yazma koruması uygulayın.
doc.Protect(ProtectionType.AllowOnlyFormFields);

// İlk bölüm için yazma korumasını kapatın.
doc.Sections[0].ProtectedForForms = false;

// Bu çıktı belgesinde ilk bölümü özgürce düzenleyebileceğiz,
// ve sadece ikinci bölümde form alanının içeriğini düzenleyebileceğiz.
doc.Save(ArtifactsDir + "Section.Protect.docx");
```

### Ayrıca bakınız

* enum [ProtectionType](../../protectiontype/)
* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)

---

## Protect(ProtectionType, string) {#protect_1}

Belgeyi değişikliklerden korur ve isteğe bağlı olarak bir koruma parolası ayarlar.

```csharp
public void Protect(ProtectionType type, string password)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| type | ProtectionType | Belge için koruma türünü belirtir. |
| password | String | Belgeyi korumak için parola. Belgeyi parola olmadan korumak istiyorsanız boş veya boş dize belirtin. |

### Notlar

Bir belge korunduğunda, kullanıcı yalnızca sınırlı değişiklikler yapabilir, , örneğin ek açıklamalar ekleme, düzeltmeler yapma veya bir formu doldurma gibi.

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

* enum [ProtectionType](../../protectiontype/)
* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


