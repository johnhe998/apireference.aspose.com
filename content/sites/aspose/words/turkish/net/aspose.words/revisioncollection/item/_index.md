---
title: RevisionCollection.Item
second_title: Aspose.Words for .NET API Referansı
description: RevisionCollection mülk. Belirtilen dizinde bir Düzeltme döndürür.
type: docs
weight: 30
url: /tr/net/aspose.words/revisioncollection/item/
---
## RevisionCollection indexer

Belirtilen dizinde bir Düzeltme döndürür.

```csharp
public Revision this[int index] { get; }
```

| Parametre | Tanım |
| --- | --- |
| index | Koleksiyona bir dizin. |

### Notlar

Endeks sıfır tabanlıdır.

Negatif dizinlere izin verilir ve koleksiyonun arkasından erişimi gösterir. Örneğin -1 son öğe anlamına gelir, -2 sondan önceki saniye anlamına gelir vb.

Dizin, listedeki öğe sayısından büyük veya ona eşitse, bu, boş bir başvuru döndürür.

İndeks negatifse ve mutlak değeri listedeki öğe sayısından büyükse, bu bir boş başvuru döndürür.

### Örnekler

Bir belgedeki revizyonlarla nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Belgenin normal düzenlenmesi revizyon sayılmaz.
builder.Write("This does not count as a revision. ");

Assert.IsFalse(doc.HasRevisions);

// Düzenlemelerimizi revizyon olarak kaydetmek için bir yazar bildirmemiz ve ardından onları izlemeye başlamamız gerekiyor.
doc.StartTrackRevisions("John Doe", DateTime.Now);

builder.Write("This is revision #1. ");

Assert.IsTrue(doc.HasRevisions);
Assert.AreEqual(1, doc.Revisions.Count);

// Bu bayrak "İnceleme" -> "İzleme" -> Microsoft Word'de "Değişiklikleri İzle" seçeneği.
// "StartTrackRevisions" yöntemi değerini etkilemez,
// ve belge, "yanlış" değerine sahip olmasına rağmen, revizyonları programlı olarak izliyor.
// Bu belgeyi Microsoft Word kullanarak açarsak, revizyonları izlemeyecektir.
Assert.IsFalse(doc.TrackRevisions);

// Belge oluşturucuyu kullanarak metin ekledik, bu nedenle ilk revizyon ekleme tipi bir revizyondur.
Revision revision = doc.Revisions[0];
Assert.AreEqual("John Doe", revision.Author);
Assert.AreEqual("This is revision #1. ", revision.ParentNode.GetText());
Assert.AreEqual(RevisionType.Insertion, revision.RevisionType);
Assert.AreEqual(revision.DateTime.Date, DateTime.Now.Date);
Assert.AreEqual(doc.Revisions.Groups[0], revision.Group);

// Silme tipi bir revizyon oluşturmak için bir çalıştırmayı kaldırın.
doc.FirstSection.Body.FirstParagraph.Runs[0].Remove();

// Yeni bir revizyon eklemek, onu revizyon koleksiyonunun başına yerleştirir.
Assert.AreEqual(RevisionType.Deletion, doc.Revisions[0].RevisionType);
Assert.AreEqual(2, doc.Revisions.Count);

// Revizyonları, biz revizyonu kabul etmeden/reddetmeden önce bile belge gövdesinde görünüyor.
// Revizyonu reddetmek, düğümlerini gövdeden kaldırır. Tersine, silme revizyonlarını oluşturan düğümler
// ayrıca revizyonu kabul edene kadar belgede oyalanır.
Assert.AreEqual("This does not count as a revision. This is revision #1.", doc.GetText().Trim());

// Silme revizyonunu kabul etmek, üst düğümünü paragraf metninden kaldıracak
// ve ardından koleksiyonun revizyonunun kendisini kaldırın.
doc.Revisions[0].Accept();

Assert.AreEqual(1, doc.Revisions.Count);
Assert.AreEqual("This is revision #1.", doc.GetText().Trim());

builder.Writeln("");
builder.Write("This is revision #2.");

// Şimdi hareketli bir revizyon tipi oluşturmak için düğümü hareket ettirin.
Node node = doc.FirstSection.Body.Paragraphs[1];
Node endNode = doc.FirstSection.Body.Paragraphs[1].NextSibling;
Node referenceNode = doc.FirstSection.Body.Paragraphs[0];

while (node != endNode)
{
    Node nextNode = node.NextSibling;
    doc.FirstSection.Body.InsertBefore(node, referenceNode);
    node = nextNode;
}

Assert.AreEqual(RevisionType.Moving, doc.Revisions[0].RevisionType);
Assert.AreEqual(8, doc.Revisions.Count);
Assert.AreEqual("This is revision #2.\rThis is revision #1. \rThis is revision #2.", doc.GetText().Trim());

// Hareketli revizyon şimdi 1. indekste. İçeriğini atmak için revizyonu reddet.
doc.Revisions[1].Reject();

Assert.AreEqual(6, doc.Revisions.Count);
Assert.AreEqual("This is revision #1. \rThis is revision #2.", doc.GetText().Trim());
```

### Ayrıca bakınız

* class [Revision](../../revision/)
* class [RevisionCollection](../)
* ad alanı [Aspose.Words](../../revisioncollection/)
* toplantı [Aspose.Words](../../../)


