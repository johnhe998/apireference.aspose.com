---
title: MailMerge.GetFieldNamesForRegion
second_title: Aspose.Words for .NET API Referansı
description: MailMerge yöntem. Bölgede kullanılabilen adres mektup birleştirme alan adlarının bir koleksiyonunu döndürür.
type: docs
weight: 230
url: /tr/net/aspose.words.mailmerging/mailmerge/getfieldnamesforregion/
---
## GetFieldNamesForRegion(string) {#getfieldnamesforregion}

Bölgede kullanılabilen adres mektup birleştirme alan adlarının bir koleksiyonunu döndürür.

```csharp
public string[] GetFieldNamesForRegion(string regionName)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| regionName | String | Bölge adı (büyük/küçük harfe duyarsız). |

### Notlar

İsteğe bağlı önek dahil tam birleştirme alan adlarını döndürür. Yinelenen alan adlarını ortadan kaldırmaz.

Belge aynı ada sahip birden fazla bölge içeriyorsa, ilk bölge işlenir.

Her çağrıda yeni bir dize dizisi oluşturulur.

### Örnekler

Adres mektup birleştirme bölgelerinin nasıl oluşturulacağını, listeleneceğini ve okunacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// MERGEFIELD'lerin içine giren "TableStart" ve "TableEnd" etiketleri,
// adres mektup birleştirme bölgelerinin başlangıç ve bitişlerini belirten dizeleri belirtin.
Assert.AreEqual("TableStart", doc.MailMerge.RegionStartTag);
Assert.AreEqual("TableEnd", doc.MailMerge.RegionEndTag);

// "MailMergeRegion1" adlı adres mektup birleştirme bölgesini başlatmak ve bitirmek için bu etiketleri kullanın,
// iki sütun için MERGEFIELD'leri içerecek.
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.InsertField(" MERGEFIELD Column1");
builder.Write(", ");
builder.InsertField(" MERGEFIELD Column2");
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// Bu koleksiyonlara bakarak birleştirme bölgelerini ve sütunlarını takip edebiliriz.
IList<MailMergeRegionInfo> regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(1, regions.Count);
Assert.AreEqual("MailMergeRegion1", regions[0].Name);

string[] mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1");

Assert.AreEqual("Column1", mergeFieldNames[0]);
Assert.AreEqual("Column2", mergeFieldNames[1]);

// Mevcut bölgenin içine aynı ada sahip bir bölge ekleyin, bu onu bir ebeveyn yapacak.
// Şimdi bir "Column2" alanı yeni bir bölgenin içinde olacak.
builder.MoveToField(regions[0].Fields[1], false); 
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.MoveToField(regions[0].Fields[1], true);
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// "GetRegionsByName" yöntemini kullanarak yinelenen bölgelerin adını ararsak,
// bir koleksiyondaki tüm bu bölgeleri döndürür.
regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(2, regions.Count);
// İkinci bölgenin artık bir üst bölge olup olmadığını kontrol edin.
Assert.AreEqual("MailMergeRegion1", regions[1].ParentRegion.Name);

mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1", 1);

Assert.AreEqual("Column2", mergeFieldNames[0]);
```

### Ayrıca bakınız

* class [MailMerge](../)
* ad alanı [Aspose.Words.MailMerging](../../mailmerge/)
* toplantı [Aspose.Words](../../../)

---

## GetFieldNamesForRegion(string, int) {#getfieldnamesforregion_1}

Bölgede kullanılabilen adres mektup birleştirme alan adlarının bir koleksiyonunu döndürür.

```csharp
public string[] GetFieldNamesForRegion(string regionName, int regionIndex)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| regionName | String | Bölge adı (büyük/küçük harfe duyarsız). |
| regionIndex | Int32 | Bölge dizini (sıfır tabanlı). |

### Notlar

İsteğe bağlı önek dahil tam birleştirme alan adlarını döndürür. Yinelenen alan adlarını ortadan kaldırmaz.

Belge aynı ada sahip birden fazla bölge içeriyorsa, N. bölge (sıfır tabanlı) işlenir.

Her çağrıda yeni bir dize dizisi oluşturulur.

### Örnekler

Adres mektup birleştirme bölgelerinin nasıl oluşturulacağını, listeleneceğini ve okunacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// MERGEFIELD'lerin içine giren "TableStart" ve "TableEnd" etiketleri,
// adres mektup birleştirme bölgelerinin başlangıç ve bitişlerini belirten dizeleri belirtin.
Assert.AreEqual("TableStart", doc.MailMerge.RegionStartTag);
Assert.AreEqual("TableEnd", doc.MailMerge.RegionEndTag);

// "MailMergeRegion1" adlı adres mektup birleştirme bölgesini başlatmak ve bitirmek için bu etiketleri kullanın,
// iki sütun için MERGEFIELD'leri içerecek.
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.InsertField(" MERGEFIELD Column1");
builder.Write(", ");
builder.InsertField(" MERGEFIELD Column2");
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// Bu koleksiyonlara bakarak birleştirme bölgelerini ve sütunlarını takip edebiliriz.
IList<MailMergeRegionInfo> regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(1, regions.Count);
Assert.AreEqual("MailMergeRegion1", regions[0].Name);

string[] mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1");

Assert.AreEqual("Column1", mergeFieldNames[0]);
Assert.AreEqual("Column2", mergeFieldNames[1]);

// Mevcut bölgenin içine aynı ada sahip bir bölge ekleyin, bu onu bir ebeveyn yapacak.
// Şimdi bir "Column2" alanı yeni bir bölgenin içinde olacak.
builder.MoveToField(regions[0].Fields[1], false); 
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.MoveToField(regions[0].Fields[1], true);
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// "GetRegionsByName" yöntemini kullanarak yinelenen bölgelerin adını ararsak,
// bir koleksiyondaki tüm bu bölgeleri döndürür.
regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(2, regions.Count);
// İkinci bölgenin artık bir üst bölge olup olmadığını kontrol edin.
Assert.AreEqual("MailMergeRegion1", regions[1].ParentRegion.Name);

mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1", 1);

Assert.AreEqual("Column2", mergeFieldNames[0]);
```

### Ayrıca bakınız

* class [MailMerge](../)
* ad alanı [Aspose.Words.MailMerging](../../mailmerge/)
* toplantı [Aspose.Words](../../../)


