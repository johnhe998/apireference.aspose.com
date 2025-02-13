---
title: StructuredDocumentTagRangeStart.Id
second_title: Aspose.Words for .NET API Referansı
description: StructuredDocumentTagRangeStart mülk. Bu yapılandırılmış belge etiketi için benzersiz bir salt okunur kalıcı sayısal kimlik belirtir.
type: docs
weight: 40
url: /tr/net/aspose.words.markup/structureddocumenttagrangestart/id/
---
## StructuredDocumentTagRangeStart.Id property

Bu yapılandırılmış belge etiketi için benzersiz bir salt okunur kalıcı sayısal kimlik belirtir.

```csharp
public int Id { get; }
```

### Notlar

Kimlik özelliği şu kurallara uyacaktır:

* Belge, yapılandırılmış belge etiketi kimliklerini yalnızca tüm belge klonlanmışsa tutacaktır.[`Clone`](../../../aspose.words/document/clone/).
* Sırasında[`ImportNode`](../../../aspose.words/documentbase/importnode/) Id, içe aktarma, hedef belgedeki içindeki diğer yapılandırılmış belge etiketi kimlikleriyle çakışmaya neden olmazsa saklanacaktır.
* Birden çok yapılandırılmış belge etiketi düğümü, Id özelliği için aynı ondalık sayı değerini belirtirse, , o zaman belgedeki ilk yapılandırılmış belge etiketi bu orijinal Kimliği, 'yi koruyacak ve sonraki tüm yapılandırılmış belge etiketi düğümleri, aşağıdaki durumlarda kendilerine atanan yeni tanımlayıcılara sahip olacaktır. belge yüklenir.
* Bağımsız yapılandırılmış belge etiketi sırasındaINodeCloningListener) işlemin yeni benzersiz kimliği, klonlanmış yapılandırılmış belge etiketi düğümü için oluşturulacak olacaktır.
* Kaynak belgede kimlik belirtilmemişse, yapılandırılmış belge etiket düğümü, belge yüklendiğinde kendisine atanan yeni bir benzersiz tanımlayıcıya sahip olacaktır .

### Örnekler

Çok bölümlü yapılandırılmış belge etiketlerinin özelliklerinin nasıl alınacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Multi-section structured document tags.docx");

StructuredDocumentTagRangeStart rangeStartTag =
    doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true)[0] as StructuredDocumentTagRangeStart;
StructuredDocumentTagRangeEnd rangeEndTag =
    doc.GetChildNodes(NodeType.StructuredDocumentTagRangeEnd, true)[0] as StructuredDocumentTagRangeEnd;

Console.WriteLine("StructuredDocumentTagRangeStart values:");
Console.WriteLine($"\t|Id: {rangeStartTag.Id}");
Console.WriteLine($"\t|Title: {rangeStartTag.Title}");
Console.WriteLine($"\t|PlaceholderName: {rangeStartTag.PlaceholderName}");
Console.WriteLine($"\t|IsShowingPlaceholderText: {rangeStartTag.IsShowingPlaceholderText}");
Console.WriteLine($"\t|LockContentControl: {rangeStartTag.LockContentControl}");
Console.WriteLine($"\t|LockContents: {rangeStartTag.LockContents}");
Console.WriteLine($"\t|Level: {rangeStartTag.Level}");
Console.WriteLine($"\t|NodeType: {rangeStartTag.NodeType}");
Console.WriteLine($"\t|RangeEnd: {rangeStartTag.RangeEnd}");
Console.WriteLine($"\t|Color: {rangeStartTag.Color.ToArgb()}");
Console.WriteLine($"\t|SdtType: {rangeStartTag.SdtType}");
Console.WriteLine($"\t|FlatOpcContent: {rangeStartTag.WordOpenXML}");
Console.WriteLine($"\t|Tag: {rangeStartTag.Tag}\n");

Console.WriteLine("StructuredDocumentTagRangeEnd values:");
Console.WriteLine($"\t|Id: {rangeEndTag.Id}");
Console.WriteLine($"\t|NodeType: {rangeEndTag.NodeType}");
```

### Ayrıca bakınız

* class [StructuredDocumentTagRangeStart](../)
* ad alanı [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* toplantı [Aspose.Words](../../../)


