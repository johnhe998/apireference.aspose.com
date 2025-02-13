---
title: OleFormat.AutoUpdate
second_title: Aspose.Words for .NET API Referansı
description: OleFormat mülk. OLE nesnesine olan bağlantının Microsoft Wordde otomatik olarak güncellenip güncellenmediğini belirtir.
type: docs
weight: 10
url: /tr/net/aspose.words.drawing/oleformat/autoupdate/
---
## OleFormat.AutoUpdate property

OLE nesnesine olan bağlantının Microsoft Word'de otomatik olarak güncellenip güncellenmediğini belirtir.

```csharp
public bool AutoUpdate { get; set; }
```

### Notlar

Varsayılan değer **yanlış**.

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


