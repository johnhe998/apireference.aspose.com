---
title: Enum ImportFormatMode
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.ImportFormatMode Sıralama. İçeriği başka bir belgeden içe aktarırken biçimlendirmenin nasıl birleştirileceğini belirtir.
type: docs
weight: 3030
url: /tr/net/aspose.words/importformatmode/
---
## ImportFormatMode enumeration

İçeriği başka bir belgeden içe aktarırken biçimlendirmenin nasıl birleştirileceğini belirtir.

```csharp
public enum ImportFormatMode
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| UseDestinationStyles | `0` | Hedef belge stillerini kullanın ve yeni stilleri kopyalayın. Bu varsayılan seçenektir. |
| KeepSourceFormatting | `1` | Gerekli tüm stilleri hedef belgeye kopyalayın, gerekirse benzersiz stil adları oluşturun. |
| KeepDifferentStyles | `2` | Yalnızca kaynak belgedekilerden farklı stilleri kopyalayın. |

### Notlar

Düğümleri bir belgeden diğerine kopyaladığınızda, bu seçenek, her iki belgenin de aynı ada sahip ancak farklı biçimlendirmeye sahip bir stili olduğunda formatting öğesinin nasıl çözüleceğini belirtir.

Biçimlendirme şu şekilde çözülür:

1. Yerleşik stiller, yerel ayardan bağımsız stil tanımlayıcıları kullanılarak eşleştirilir. Kullanıcı tanımlı stiller, büyük/küçük harfe duyarlı stil adı kullanılarak eşleştirilir.
2. Hedef belgede eşleşen bir stil bulunamazsa, style (ve onun tarafından başvurulan tüm stiller) hedef document 'ye kopyalanır ve içe aktarılan düğümler yeni stile başvurmak üzere güncellenir.
3. Hedef belgede zaten eşleşen bir stil varsa, ne olacağı `importFormatMode` parametre 'ye geçti[`Document.ImportNode`](../documentbase/importnode/) aşağıda açıklandığı gibi.

kullanırken **KullanımVarış Stilleri**seçenek, hedef belgede zaten eşleşen bir stil varsa , stil kopyalanmaz ve içe aktarılan düğümler mevcut stile başvurmak için güncellenir .

kullanmanın dezavantajı **KullanımVarış Stilleri** içe aktarılan metnin kaynak belgeyle karşılaştırıldığında hedef belgede farklı görünmesidir. Örneğin, kaynak belgedeki "Başlık 1" stili Arial 16pt yazı tipini kullanır ve hedef belgedeki "Başlık 1" stili Times New kullanır Roman 14pt font. Başka bir doğrudan biçimlendirme olmadan "Başlık 1" stilindeki metni içe aktarırken, hedef belgede Times New Roman 14pt yazı tipi olarak görünür.

**Kaynak biçimlendirmesini koruyun**seçeneği, içe aktarılan içeriğin hedef belgede kaynak belgede göründüğü gibi aynı göründüğünden emin olmanızı sağlar. Hedef belgede zaten eşleşen bir stil varsa, kaynak stil biçimlendirmesi doğrudan Düğüm niteliklerine genişletilir ve stil Normal olarak değiştirildi. Stil hedef belgede yoksa, kaynak stil hedef belgeye aktarılır ve içe aktarılan düğüme uygulanır. Kaynak stili korumanın her zaman mümkün olmadığını unutmayın. hedef belgede mevcut değil. Bu durumda, bu tür bir stilin biçimlendirmesi, orijinal Düğüm biçimlendirmesinin korunması lehine doğrudan Düğüm özniteliklerine genişletilecektir.

kullanmanın dezavantajı **Kaynak biçimlendirmesini koruyun**birden fazla içe aktarma gerçekleştirirseniz, hedef belgede birçok stil elde edebilirsiniz ve bu, Microsoft Word'de tutarlı stil biçimlendirmesini bu belge için zorlaştırabilir.

kullanma **KeepFarklıStiller** seçenek, sağladıkları biçimlendirme kaynak belgedeki stiller aynıysa hedef styles 'nin yeniden kullanılmasına izin verir. Hedef belgedeki stil kaynaktan farklıysa, içe aktarılır.

### Örnekler

Bir belgenin başka bir belgeye nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Document.docx");

DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);

Document docToInsert = new Document(MyDir + "Formatted elements.docx");

builder.InsertDocument(docToInsert, ImportFormatMode.KeepSourceFormatting);
builder.Document.Save(ArtifactsDir + "DocumentBuilder.InsertDocument.docx");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


