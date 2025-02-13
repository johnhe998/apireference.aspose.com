---
title: Interface IStructuredDocumentTag
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Markup.IStructuredDocumentTag arayüz. için ortak bir veri tanımlamak için arayüzStructuredDocumentTag veStructuredDocumentTagRangeStart .
type: docs
weight: 3730
url: /tr/net/aspose.words.markup/istructureddocumenttag/
---
## IStructuredDocumentTag interface

için ortak bir veri tanımlamak için arayüz[`StructuredDocumentTag`](../structureddocumenttag/) ve[`StructuredDocumentTagRangeStart`](../structureddocumenttagrangestart/) .

```csharp
public interface IStructuredDocumentTag
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Color](../../aspose.words.markup/istructureddocumenttag/color/) { get; set; } | Yapılandırılmış belge etiketinin rengini alır veya ayarlar. |
| [Id](../../aspose.words.markup/istructureddocumenttag/id/) { get; } | Bunun için benzersiz bir salt okunur kalıcı sayısal kimlik belirtir **SDT**. |
| [IsShowingPlaceholderText](../../aspose.words.markup/istructureddocumenttag/isshowingplaceholdertext/) { get; set; } | Bunun içeriğinin olup olmadığını belirtir. **SDT** yer tutucu text içerecek şekilde yorumlanmalıdır (SDT içindeki normal metin içeriklerinin aksine). |
| [Level](../../aspose.words.markup/istructureddocumenttag/level/) { get; } | Bunun hangi düzeyde olduğunu alır **SDT** belge ağacında gerçekleşir. |
| [LockContentControl](../../aspose.words.markup/istructureddocumenttag/lockcontentcontrol/) { get; set; } | true olarak ayarlandığında, bu özellik bir kullanıcının bunu silmesini engeller. **SDT** . |
| [LockContents](../../aspose.words.markup/istructureddocumenttag/lockcontents/) { get; set; } | true olarak ayarlandığında, bu özellik bir kullanıcının bunun içeriğini düzenlemesini engeller. **SDT** . |
| [Placeholder](../../aspose.words.markup/istructureddocumenttag/placeholder/) { get; } | [`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/) bu SDT çalıştırma içeriği boş olduğunda görüntülenmesi gereken yer tutucu metni içeren, ilişkili eşlenen XML öğesi,[`XmlMapping`](./xmlmapping/) element veya[`IsShowingPlaceholderText`](./isshowingplaceholdertext/) eleman doğrudur. |
| [PlaceholderName](../../aspose.words.markup/istructureddocumenttag/placeholdername/) { get; set; } | Adını alır veya ayarlar[`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/) yer tutucu metni içeren. |
| [SdtType](../../aspose.words.markup/istructureddocumenttag/sdttype/) { get; } | Bunun türünü alır **Yapılandırılmış belge etiketi** . |
| [Tag](../../aspose.words.markup/istructureddocumenttag/tag/) { get; set; } | Geçerli SDT düğümüyle ilişkili bir etiketi belirtir. Boş olamaz. |
| [Title](../../aspose.words.markup/istructureddocumenttag/title/) { get; set; } | Bununla ilişkili kolay adı belirtir **SDT** . Boş olamaz. |
| [WordOpenXML](../../aspose.words.markup/istructureddocumenttag/wordopenxml/) { get; } | Dizindeki düğümde bulunan XML'i temsil eden bir dize alır.FlatOpc biçim. |
| [XmlMapping](../../aspose.words.markup/istructureddocumenttag/xmlmapping/) { get; } | Bu yapılandırılmış belge etiketinin geçerli belgenin özel bir XML bölümünde XML data ile eşlenmesini temsil eden bir nesne alır. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [IsRanged](../../aspose.words.markup/istructureddocumenttag/isranged/)() | Bu örnek bir aralıklı yapılandırılmış belge etiketiyse true değerini döndürür. |
| [StructuredDocumentTagNode](../../aspose.words.markup/istructureddocumenttag/structureddocumenttagnode/)() | Bu arabirimi uygulayan Düğüm nesnesini döndürür. |

### Ayrıca bakınız

* ad alanı [Aspose.Words.Markup](../../aspose.words.markup/)
* toplantı [Aspose.Words](../../)


