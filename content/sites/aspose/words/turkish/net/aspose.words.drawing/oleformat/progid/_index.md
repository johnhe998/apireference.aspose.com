---
title: OleFormat.ProgId
second_title: Aspose.Words for .NET API Referansı
description: OleFormat mülk. OLE nesnesinin ProgIDsini alır veya ayarlar.
type: docs
weight: 90
url: /tr/net/aspose.words.drawing/oleformat/progid/
---
## OleFormat.ProgId property

OLE nesnesinin ProgID'sini alır veya ayarlar.

```csharp
public string ProgId { get; set; }
```

### Notlar

ProgID özelliği, Microsoft Word belgelerinde her zaman bulunmaz ve güvenilemez.

Boş olamaz.

Varsayılan değer boş bir dizedir.

### Örnekler

Gömülü OLE nesnelerinin dosyalara nasıl ayıklanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "OLE spreadsheet.docm");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

// İlk şekildeki OLE nesnesi bir Microsoft Excel elektronik tablosudur.
OleFormat oleFormat = shape.OleFormat;

Assert.AreEqual("Excel.Sheet.12", oleFormat.ProgId);

// Nesnemiz ne otomatik güncelleme yapıyor ne de güncellemelere kilitleniyor.
Assert.False(oleFormat.AutoUpdate);
Assert.AreEqual(false, oleFormat.IsLocked);

// OLE nesnesini yerel dosya sistemindeki bir dosyaya kaydetmeyi planlıyorsak,
// Dosyaya hangi dosya uzantısının uygulanacağını belirlemek için "Önerilen Uzantı" özelliğini kullanabiliriz.
Assert.AreEqual(".xlsx", oleFormat.SuggestedExtension);

// Aşağıda, bir OLE nesnesini yerel dosya sistemindeki bir dosyaya kaydetmenin iki yolu bulunmaktadır.
// 1 - Akış yoluyla kaydedin:
using (FileStream fs = new FileStream(ArtifactsDir + "OLE spreadsheet extracted via stream" + oleFormat.SuggestedExtension, FileMode.Create))
{
    oleFormat.Save(fs);
}

// 2 - Doğrudan bir dosya adına kaydedin:
oleFormat.Save(ArtifactsDir + "OLE spreadsheet saved directly" + oleFormat.SuggestedExtension);
```

### Ayrıca bakınız

* class [OleFormat](../)
* ad alanı [Aspose.Words.Drawing](../../oleformat/)
* toplantı [Aspose.Words](../../../)


