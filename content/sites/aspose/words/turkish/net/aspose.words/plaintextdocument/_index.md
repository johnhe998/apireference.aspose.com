---
title: Class PlainTextDocument
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.PlainTextDocument sınıf. Belge içeriğinin düz metin gösterimini çıkarmaya izin verir.
type: docs
weight: 4190
url: /tr/net/aspose.words/plaintextdocument/
---
## PlainTextDocument class

Belge içeriğinin düz metin gösterimini çıkarmaya izin verir.

```csharp
public class PlainTextDocument
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [PlainTextDocument](plaintextdocument/#constructor)(Stream) | Bir akıştan düz metin belgesi oluşturur. Dosya biçimini otomatik olarak algılar. |
| [PlainTextDocument](plaintextdocument/#constructor_2)(string) | Bir dosyadan düz metin belgesi oluşturur. Dosya biçimini otomatik olarak algılar. |
| [PlainTextDocument](plaintextdocument/#constructor_1)(Stream, LoadOptions) | Bir akıştan düz metin belgesi oluşturur. Şifreleme parolası gibi ek seçeneklerin belirlenmesine izin verir. |
| [PlainTextDocument](plaintextdocument/#constructor_3)(string, LoadOptions) | Bir dosyadan düz metin belgesi oluşturur. Şifreleme parolası gibi ek seçeneklerin belirlenmesine izin verir. |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [BuiltInDocumentProperties](../../aspose.words/plaintextdocument/builtindocumentproperties/) { get; } | Alır[`BuiltInDocumentProperties`](./builtindocumentproperties/) belgenin. |
| [CustomDocumentProperties](../../aspose.words/plaintextdocument/customdocumentproperties/) { get; } | Alır[`CustomDocumentProperties`](./customdocumentproperties/) belgenin. |
| [Text](../../aspose.words/plaintextdocument/text/) { get; } | Dize olarak birleştirilmiş belgenin metin içeriğini alır. |

### Örnekler

Bir Microsoft Word belgesinin içeriğinin düz metin olarak nasıl yükleneceğini gösterir.

```csharp
Document doc = new Document(); 
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "PlainTextDocument.Load.docx");

PlainTextDocument plaintext = new PlainTextDocument(ArtifactsDir + "PlainTextDocument.Load.docx");

Assert.AreEqual("Hello world!", plaintext.Text.Trim());
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


