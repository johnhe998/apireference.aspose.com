---
title: ListLevel.DeletePictureBullet
second_title: Aspose.Words for .NET API Referansı
description: ListLevel yöntem. Geçerli liste düzeyi için resim madde işaretini siler.
type: docs
weight: 160
url: /tr/net/aspose.words.lists/listlevel/deletepicturebullet/
---
## ListLevel.DeletePictureBullet method

Geçerli liste düzeyi için resim madde işaretini siler.

```csharp
public void DeletePictureBullet()
```

### Notlar

Silindikten sonra varsayılan madde işareti gösterilecektir.

### Örnekler

Liste öğesi etiketleri için özel bir görüntü simgesinin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();

List list = doc.Lists.Add(ListTemplate.BulletCircle);

// Geçerli liste düzeyi için bir resim madde işareti oluşturun ve yerel bir dosya sisteminden bir resim ayarlayın
// bu liste düzeyi için madde işaretlerinin görüntüleneceği simge olarak.
list.ListLevels[0].CreatePictureBullet();
list.ListLevels[0].ImageData.SetImage(ImageDir + "Logo icon.ico");

Assert.IsTrue(list.ListLevels[0].ImageData.HasImage);

DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.List = list;
builder.Writeln("Hello world!");
builder.Write("Hello again!");

doc.Save(ArtifactsDir + "Lists.CreatePictureBullet.docx");

list.ListLevels[0].DeletePictureBullet();

Assert.IsNull(list.ListLevels[0].ImageData);
```

### Ayrıca bakınız

* class [ListLevel](../)
* ad alanı [Aspose.Words.Lists](../../listlevel/)
* toplantı [Aspose.Words](../../../)


