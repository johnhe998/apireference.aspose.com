---
title: Footnote.Footnote
second_title: Aspose.Words for .NET API Referansı
description: Footnote inşaatçı. Şunun bir örneğini başlatır Dipnot sınıf.
type: docs
weight: 10
url: /tr/net/aspose.words.notes/footnote/footnote/
---
## Footnote constructor

Şunun bir örneğini başlatır: **Dipnot** sınıf.

```csharp
public Footnote(DocumentBase doc, FootnoteType footnoteType)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| doc | DocumentBase | Sahip belgesi. |
| footnoteType | FootnoteType | A[`FootnoteType`](../footnotetype/) Bunun bir dipnot mu yoksa son not mu olduğunu belirten value . |

### Notlar

Ne zaman **Dipnot** oluşturulur, belirtilen belgeye aittir, ancak henüz belgenin bir parçası değil ve **Üst Düğüm** boş.

Eklemek **Dipnot** belgeye, dipnotun eklenmesini istediğiniz paragrafta InsertAfter veya InsertBefore kullanın.

### Örnekler

Dipnotların nasıl ekleneceğini ve özelleştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Metin ekleyin ve bir dipnotla referans verin. Bu dipnot küçük bir üst simge referansı yerleştirecektir
// referans verdiği metinden sonra işaretleyin ve sayfanın altındaki ana gövde metninin altında bir giriş oluşturun.
// Bu giriş, dipnotun referans işaretini ve referans metnini içerecektir,
// belge oluşturucunun "InsertFootnote" yöntemine geçeceğiz.
builder.Write("Main body text.");
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// Bu özellik "true" olarak ayarlanırsa dipnotumuzun referans işareti
// tüm bölümün dipnotları arasında indeksi olacaktır.
// Bu ilk dipnottur, dolayısıyla referans işareti "1" olacaktır.
Assert.True(footnote.IsAuto);

// Referans metnini düzenlemek için belge oluşturucuyu dipnotun içine taşıyabiliriz. 
builder.MoveTo(footnote.FirstParagraph);
builder.Write(" More text added by a DocumentBuilder.");
builder.MoveToDocumentEnd();

Assert.AreEqual("\u0002 Footnote text. More text added by a DocumentBuilder.", footnote.GetText().Trim());

builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// Dipnotun indeks numarası yerine kullanacağı özel bir referans işareti belirleyebiliriz.
footnote.ReferenceMark = "RefMark";

Assert.False(footnote.IsAuto);

// "IsAuto" bayrağı true olarak ayarlanmış bir yer imi gerçek dizinini göstermeye devam edecek
// önceki yer imleri özel referans işaretleri gösterse bile, bu nedenle bu yer iminin referans işareti "3" olacaktır.
builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

Assert.True(footnote.IsAuto);

doc.Save(ArtifactsDir + "InlineStory.AddFootnote.docx");
```

### Ayrıca bakınız

* class [DocumentBase](../../../aspose.words/documentbase/)
* enum [FootnoteType](../../footnotetype/)
* class [Footnote](../)
* ad alanı [Aspose.Words.Notes](../../footnote/)
* toplantı [Aspose.Words](../../../)


