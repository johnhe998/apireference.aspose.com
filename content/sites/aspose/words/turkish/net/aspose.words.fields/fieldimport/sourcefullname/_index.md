---
title: FieldImport.SourceFullName
second_title: Aspose.Words for .NET API Referansı
description: FieldImport mülk. Resmin konumunu alır veya ayarlar.
type: docs
weight: 40
url: /tr/net/aspose.words.fields/fieldimport/sourcefullname/
---
## FieldImport.SourceFullName property

Resmin konumunu alır veya ayarlar.

```csharp
public string SourceFullName { get; set; }
```

### Örnekler

IMPORT ve INCLUDEPICTURE alanlarını kullanarak resimlerin nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aşağıda, yerel dosya sisteminden bağlantılı görüntüleri görüntülemek için kullanabileceğimiz iki benzer alan türü bulunmaktadır.
// 1 - INCLUDEPICTURE alanı:
FieldIncludePicture fieldIncludePicture = (FieldIncludePicture)builder.InsertField(FieldType.FieldIncludePicture, true);
fieldIncludePicture.SourceFullName = ImageDir + "Transparent background logo.png";

Assert.True(Regex.Match(fieldIncludePicture.GetFieldCode(), " INCLUDEPICTURE  .*").Success);

// PNG32.FLT filtresini uygulayın.
fieldIncludePicture.GraphicFilter = "PNG32";
fieldIncludePicture.IsLinked = true;
fieldIncludePicture.ResizeHorizontally = true;
fieldIncludePicture.ResizeVertically = true;

// 2 - İTHALAT alanı:
FieldImport fieldImport = (FieldImport)builder.InsertField(FieldType.FieldImport, true);
fieldImport.SourceFullName = ImageDir + "Transparent background logo.png";
fieldImport.GraphicFilter = "PNG32";
fieldImport.IsLinked = true;

Assert.True(Regex.Match(fieldImport.GetFieldCode(), " IMPORT  .* \\\\c PNG32 \\\\d").Success);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.IMPORT.INCLUDEPICTURE.docx");
```

### Ayrıca bakınız

* class [FieldImport](../)
* ad alanı [Aspose.Words.Fields](../../fieldimport/)
* toplantı [Aspose.Words](../../../)


