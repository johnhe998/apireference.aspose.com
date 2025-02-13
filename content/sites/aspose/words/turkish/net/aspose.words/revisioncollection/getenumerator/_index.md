---
title: RevisionCollection.GetEnumerator
second_title: Aspose.Words for .NET API Referansı
description: RevisionCollection yöntem. Bir numaralandırıcı nesnesi döndürür.
type: docs
weight: 50
url: /tr/net/aspose.words/revisioncollection/getenumerator/
---
## RevisionCollection.GetEnumerator method

Bir numaralandırıcı nesnesi döndürür.

```csharp
public IEnumerator<Revision> GetEnumerator()
```

### Örnekler

Bir belgenin düzeltme koleksiyonuyla nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
RevisionCollection revisions = doc.Revisions;

// Bu koleksiyonun kendisi bir revizyon grupları koleksiyonuna sahiptir.
// Her grup, bitişik revizyonların bir dizisidir.
Console.WriteLine($"{revisions.Groups.Count} revision groups:");

// Grup koleksiyonunu yineleyin ve revizyonun ilgili olduğu metni yazdırın.
using (IEnumerator<RevisionGroup> e = revisions.Groups.GetEnumerator())
{
    while (e.MoveNext())
    {
        Console.WriteLine($"\tGroup type \"{e.Current.RevisionType}\", " +
                          $"author: {e.Current.Author}, contents: [{e.Current.Text.Trim()}]");
    }
}

// Bir revizyonun etkilediği her Çalıştırma, karşılık gelen bir Revizyon nesnesi alır.
// Revizyonların koleksiyonu, yukarıda yazdırdığımız sıkıştırılmış formdan oldukça büyüktür,
// Microsoft Word düzenlemesi sırasında belgeyi kaç Çalıştırmaya ayırdığımıza bağlı olarak.
Console.WriteLine($"\n{revisions.Count} revisions:");

using (IEnumerator<Revision> e = revisions.GetEnumerator())
{
    while (e.MoveNext())
    {
        // StyleDefinitionChange kesinlikle stilleri etkiler, belge düğümlerini etkilemez. Bu "ParentStyle" anlamına gelir
        // özelliği her zaman kullanımda olacak, ParentNode ise her zaman boş olacak.
        // Diğer tüm değişiklikler düğümleri etkilediğinden, ParentNode tersine kullanımda olacak ve ParentStyle boş olacaktır.
        if (e.Current.RevisionType == RevisionType.StyleDefinitionChange)
        {
            Console.WriteLine($"\tRevision type \"{e.Current.RevisionType}\", " +
                              $"author: {e.Current.Author}, style: [{e.Current.ParentStyle.Name}]");
        }
        else
        {
            Console.WriteLine($"\tRevision type \"{e.Current.RevisionType}\", " +
                              $"author: {e.Current.Author}, contents: [{e.Current.ParentNode.GetText().Trim()}]");
        }
    }
}

// Koleksiyon aracılığıyla tüm revizyonları reddet, belgeyi orijinal formuna geri döndür.
revisions.RejectAll();

Assert.AreEqual(0, revisions.Count);
```

### Ayrıca bakınız

* class [Revision](../../revision/)
* class [RevisionCollection](../)
* ad alanı [Aspose.Words](../../revisioncollection/)
* toplantı [Aspose.Words](../../../)


