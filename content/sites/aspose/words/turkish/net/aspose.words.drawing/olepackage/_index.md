---
title: Class OlePackage
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.OlePackage sınıf. OLE Paket özelliklerine erişime izin verir.
type: docs
weight: 1030
url: /tr/net/aspose.words.drawing/olepackage/
---
## OlePackage class

OLE Paket özelliklerine erişime izin verir.

```csharp
public class OlePackage
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [DisplayName](../../aspose.words.drawing/olepackage/displayname/) { get; set; } | OLE Paketi görünen adını alır veya ayarlar. |
| [FileName](../../aspose.words.drawing/olepackage/filename/) { get; set; } | OLE Paket dosya adını alır veya ayarlar. |

### Notlar

OLE paketi, OLE işleyicisi bilinmiyorsa katıştırılmış nesneyi depolamanın eski ve "belgelenmemiş" bir yoludur. Windows 3.1, 95 ve 98 gibi erken Windows sürümlerinde her tür veriyi belgeye gömmek için kullanılabilecek Packager.exe uygulaması vardı. . Artık bu uygulama Windows'tan hariç tutulmuştur, ancak MS Word ve diğer uygulamalar, OLE işleyicisi eksik veya bilinmiyorsa, verileri gömmek için hala onu kullanır.

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

* ad alanı [Aspose.Words.Drawing](../../aspose.words.drawing/)
* toplantı [Aspose.Words](../../)


