---
title: Enum DocumentSecurity
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Properties.DocumentSecurity Sıralama. için bir değer olarak kullanılırSecurity property. Bir belgenin güvenlik düzeyini sayısal bir değer olarak belirtir.
type: docs
weight: 4240
url: /tr/net/aspose.words.properties/documentsecurity/
---
## DocumentSecurity enumeration

için bir değer olarak kullanılır[`Security`](../builtindocumentproperties/security/) property. Bir belgenin güvenlik düzeyini sayısal bir değer olarak belirtir.

```csharp
[Flags]
public enum DocumentSecurity
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| None | `0` | Özellik tarafından belirtilen güvenlik durumu yok. |
| PasswordProtected | `1` | Belge parola korumalıdır. (Not şimdiye kadar hiçbir belgede görülmedi). |
| ReadOnlyRecommended | `2` | Belge, mümkünse salt okunur olarak açılacak, ancak ayar geçersiz kılınabilir. |
| ReadOnlyEnforced | `4` | Her zaman salt okunur olarak açılacak belge. |
| ReadOnlyExceptAnnotations | `8` | Ek açıklamalar dışında her zaman salt okunur olarak açılacak belge. |

### Örnekler

Bir belgenin güvenlik düzeyini görüntülemek için belge özelliklerinin nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();

Assert.AreEqual(DocumentSecurity.None, doc.BuiltInDocumentProperties.Security);

// Bir belgeyi salt okunur olacak şekilde yapılandırırsak, "Güvenlik" yerleşik özelliğini kullanarak bu durumu görüntüler.
doc.WriteProtection.ReadOnlyRecommended = true;
doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyRecommended.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyRecommended, 
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyRecommended.docx").BuiltInDocumentProperties.Security);

// Bir belgeyi yazmaya karşı koruyun ve ardından güvenlik seviyesini doğrulayın.
doc = new Document();

Assert.False(doc.WriteProtection.IsWriteProtected);

doc.WriteProtection.SetPassword("MyPassword");

Assert.True(doc.WriteProtection.ValidatePassword("MyPassword"));
Assert.True(doc.WriteProtection.IsWriteProtected);

doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyEnforced.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyEnforced,
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyEnforced.docx").BuiltInDocumentProperties.Security);

// "Güvenlik" açıklayıcı bir özelliktir. Değerini manuel olarak düzenleyebiliriz.
doc = new Document();

doc.Protect(ProtectionType.AllowOnlyComments, "MyPassword");
doc.BuiltInDocumentProperties.Security = DocumentSecurity.ReadOnlyExceptAnnotations;
doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyExceptAnnotations.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyExceptAnnotations,
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyExceptAnnotations.docx").BuiltInDocumentProperties.Security);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Properties](../../aspose.words.properties/)
* toplantı [Aspose.Words](../../)


