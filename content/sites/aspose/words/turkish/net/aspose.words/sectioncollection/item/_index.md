---
title: SectionCollection.Item
second_title: Aspose.Words for .NET API Referansı
description: SectionCollection mülk. Verilen dizindeki bir bölümü alır.
type: docs
weight: 10
url: /tr/net/aspose.words/sectioncollection/item/
---
## SectionCollection indexer

Verilen dizindeki bir bölümü alır.

```csharp
public Section this[int index] { get; }
```

| Parametre | Tanım |
| --- | --- |
| index | Bölümler listesine bir dizin. |

### Notlar

Endeks sıfır tabanlıdır.

Negatif dizinlere izin verilir ve koleksiyonun arkasından erişimi gösterir. Örneğin -1 son öğe anlamına gelir, -2 sondan önceki saniye anlamına gelir vb.

Dizin, listedeki öğe sayısından büyük veya ona eşitse, bu, boş bir başvuru döndürür.

İndeks negatifse ve mutlak değeri listedeki öğe sayısından büyükse, bu bir boş başvuru döndürür.

### Örnekler

Belgenin sayfa düzeninin ne zaman yeniden hesaplanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Bir belgeyi PDF'ye, bir görüntüye kaydetmek veya ilk kez yazdırmak otomatik olarak
// belgenin düzenini sayfalarında önbelleğe al.
doc.Save(ArtifactsDir + "Document.UpdatePageLayout.1.pdf");

// Belgeyi bir şekilde değiştirin.
doc.Styles["Normal"].Font.Size = 6;
doc.Sections[0].PageSetup.Orientation = Aspose.Words.Orientation.Landscape;

 // Aspose.Words'ün mevcut sürümünde, belgeyi değiştirmek otomatik olarak yeniden oluşturmaz
// önbelleğe alınmış sayfa düzeni. Önbelleğe alınmış düzen için istersek
// güncel kalmak için manuel olarak güncellememiz gerekecek.
doc.UpdatePageLayout();

doc.Save(ArtifactsDir + "Document.UpdatePageLayout.2.pdf");
```

Düzenleme için yeni bir bölüm düğümünün nasıl hazırlanacağını gösterir.

```csharp
Document doc = new Document();

// Boş bir belge, bir paragrafı olan bir gövdesi olan bir bölümle birlikte gelir.
// Bu paragrafa metin dizileri, şekiller veya tablolar gibi öğeler ekleyerek bu belgeye içerik ekleyebiliriz.
Assert.AreEqual(NodeType.Section, doc.GetChild(NodeType.Any, 0, true).NodeType);
Assert.AreEqual(NodeType.Body, doc.Sections[0].GetChild(NodeType.Any, 0, true).NodeType);
Assert.AreEqual(NodeType.Paragraph, doc.Sections[0].Body.GetChild(NodeType.Any, 0, true).NodeType);

// Bunun gibi yeni bir bölüm eklersek, bunun bir gövdesi veya başka herhangi bir alt düğümü olmayacaktır.
doc.Sections.Add(new Section(doc));

Assert.AreEqual(0, doc.Sections[1].GetChildNodes(NodeType.Any, true).Count);

// Düzenlemeye başlamak için bu bölüme bir gövde ve bir paragraf eklemek için "EnsureMinimum" yöntemini çalıştırın.
doc.LastSection.EnsureMinimum();

Assert.AreEqual(NodeType.Body, doc.Sections[1].GetChild(NodeType.Any, 0, true).NodeType);
Assert.AreEqual(NodeType.Paragraph, doc.Sections[1].Body.GetChild(NodeType.Any, 0, true).NodeType);

doc.Sections[0].Body.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Ayrıca bakınız

* class [Section](../../section/)
* class [SectionCollection](../)
* ad alanı [Aspose.Words](../../sectioncollection/)
* toplantı [Aspose.Words](../../../)


