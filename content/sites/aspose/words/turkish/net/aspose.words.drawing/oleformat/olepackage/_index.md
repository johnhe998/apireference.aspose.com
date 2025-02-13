---
title: OleFormat.OlePackage
second_title: Aspose.Words for .NET API Referansı
description: OleFormat mülk. Erişim sağlayınOlePackage OLE nesnesi bir OLE Paketi ise. Aksi takdirde null döndürür.
type: docs
weight: 80
url: /tr/net/aspose.words.drawing/oleformat/olepackage/
---
## OleFormat.OlePackage property

Erişim sağlayın[`OlePackage`](../../olepackage/) OLE nesnesi bir OLE Paketi ise. Aksi takdirde null döndürür.

```csharp
public OlePackage OlePackage { get; }
```

### Notlar

OLE Paketi, bir Windows sisteminin OLE kayıt defterinde bulunmayan herhangi bir dosya biçimini, neredeyse her şeyi bir belgeye gömmeye izin veren genel bir pakete sarmaya izin veren eski bir teknolojidir. Bkz.[`OlePackage`](../../olepackage/)daha fazla bilgi için yazın.

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

* class [OlePackage](../../olepackage/)
* class [OleFormat](../)
* ad alanı [Aspose.Words.Drawing](../../oleformat/)
* toplantı [Aspose.Words](../../../)


