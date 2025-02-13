---
title: Document.JoinRunsWithSameFormatting
second_title: Aspose.Words for .NET API Referansı
description: Document yöntem. Belgenin tüm paragraflarında aynı biçimlendirmeyle çalıştırmaları birleştirir.
type: docs
weight: 600
url: /tr/net/aspose.words/document/joinrunswithsameformatting/
---
## Document.JoinRunsWithSameFormatting method

Belgenin tüm paragraflarında aynı biçimlendirmeyle çalıştırmaları birleştirir.

```csharp
public int JoinRunsWithSameFormatting()
```

### Geri dönüş değeri

Gerçekleştirilen birleştirme sayısı. Ne zaman **N** bitişik koşular birleştirilir, sayılırlar **N - 1** katılır.

### Notlar

Bu bir optimizasyon yöntemidir. Bazı belgeler aynı biçimlendirmeye sahip bitişik çalıştırmalar içerir. Genellikle bu, bir belge yoğun bir şekilde manuel olarak düzenlendiyse oluşur. Bu çalıştırmalara katılarak belge boyutunu küçültebilir ve daha fazla işlemeyi hızlandırabilirsiniz.

İşlem her kontrol eder[`Paragraph`](../../paragraph/) bitişik için belgedeki düğüm[`Run`](../../run/) aynı özelliklere sahip düğümler. run oluşturma ve değiştirme düzenleme oturumlarını izlemek için kullanılan benzersiz tanımlayıcıları yok sayar. Her birleştirme sırasındaki ilk çalıştırma, tüm metni biriktirir. Kalan çalıştırmalar belgeden silinir.

### Örnekler

Gereksiz çalıştırmaları azaltmak için bir belgedeki çalıştırmaların nasıl birleştirileceğini gösterir.

```csharp
// Aynı biçimlendirmeye sahip bitişik metin dizileri içeren bir belge açın,
// aynı paragrafı Microsoft Word'de birden çok kez düzenlersek genellikle oluşur.
Document doc = new Document(MyDir + "Rendering.docx");

// Bu çalıştırmalardan herhangi biri aynı biçimlendirmeye bitişikse,
// daha sonra belge basitleştirilebilir.
Assert.AreEqual(317, doc.GetChildNodes(NodeType.Run, true).Count);

// Bu tür çalıştırmaları bu yöntemle birleştirin ve gerçekleşecek çalıştırma birleştirmelerinin sayısını doğrulayın.
Assert.AreEqual(121, doc.JoinRunsWithSameFormatting());

// Birleştirme sayısı ve birleştirmeden sonra sahip olduğumuz çalıştırma sayısı
// başlangıçta sahip olduğumuz çalıştırma sayısını toplamalıyız.
Assert.AreEqual(196, doc.GetChildNodes(NodeType.Run, true).Count);
```

### Ayrıca bakınız

* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


