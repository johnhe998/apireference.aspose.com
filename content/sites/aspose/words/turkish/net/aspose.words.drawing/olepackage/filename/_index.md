---
title: OlePackage.FileName
second_title: Aspose.Words for .NET API Referansı
description: OlePackage mülk. OLE Paket dosya adını alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.drawing/olepackage/filename/
---
## OlePackage.FileName property

OLE Paket dosya adını alır veya ayarlar.

```csharp
public string FileName { get; set; }
```

### Örnekler

Bir OLE nesnesinin bir belgeye nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// OLE nesneleri, başka bir yüklü uygulamayı kullanarak yerel dosya sistemindeki diğer dosyaları açmamıza izin verir
// işletim sistemimizde, belge gövdesinde OLE nesnesini içeren şekle çift tıklayarak.
// Bu durumda harici dosyamız bir ZIP arşivi olacaktır.
byte[] zipFileBytes = File.ReadAllBytes(DatabaseDir + "cat001.zip");

using (MemoryStream stream = new MemoryStream(zipFileBytes))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);

    shape.OleFormat.OlePackage.FileName = "Package file name.zip";
    shape.OleFormat.OlePackage.DisplayName = "Package display name.zip";
}

doc.Save(ArtifactsDir + "Shape.InsertOlePackage.docx");
```

### Ayrıca bakınız

* class [OlePackage](../)
* ad alanı [Aspose.Words.Drawing](../../olepackage/)
* toplantı [Aspose.Words](../../../)


