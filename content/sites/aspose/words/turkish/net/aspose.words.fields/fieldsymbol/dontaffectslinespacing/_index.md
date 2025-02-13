---
title: FieldSymbol.DontAffectsLineSpacing
second_title: Aspose.Words for .NET API Referansı
description: FieldSymbol mülk. Alan tarafından alınan karakterin paragrafın satır aralığını etkileyip etkilemediğini alır veya ayarlar.
type: docs
weight: 30
url: /tr/net/aspose.words.fields/fieldsymbol/dontaffectslinespacing/
---
## FieldSymbol.DontAffectsLineSpacing property

Alan tarafından alınan karakterin paragrafın satır aralığını etkileyip etkilemediğini alır veya ayarlar.

```csharp
public bool DontAffectsLineSpacing { get; set; }
```

### Örnekler

SEMBOL alanının nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aşağıda, tek bir karakter görüntülemek için bir SEMBOL alanını kullanmanın üç yolu bulunmaktadır.
// 1 - Bir ANSI karakter koduyla belirtilen © (Telif hakkı) sembolünü görüntüleyen bir SEMBOL alanı ekleyin:
FieldSymbol field = (FieldSymbol)builder.InsertField(FieldType.FieldSymbol, true);

// ANSI karakter kodu "U+00A9" veya tamsayı biçiminde "169" telif hakkı sembolü için ayrılmıştır.
field.CharacterCode = 0x00a9.ToString();
field.IsAnsi = true;

Assert.AreEqual(" SYMBOL  169 \\a", field.GetFieldCode());

builder.Writeln(" Line 1");

// 2 - ∞ (Sonsuzluk) sembolünü görüntüleyen bir SEMBOL alanı ekleyin ve görünümünü değiştirin:
field = (FieldSymbol)builder.InsertField(FieldType.FieldSymbol, true);

// Unicode'da sonsuzluk sembolü "221E" kodunu kaplar.
field.CharacterCode = 0x221E.ToString();
field.IsUnicode = true;

// Windows Karakter Haritasını kullandıktan sonra sembolümüzün yazı tipini değiştirin
// yazı tipinin bu sembolü temsil etmesini sağlamak için.
field.FontName = "Calibri";
field.FontSize = "24";

// Metnin geri kalanını satırlarında aşağı itmemelerini sağlamak için bu bayrağı uzun semboller için ayarlayabiliriz.
field.DontAffectsLineSpacing = true;

Assert.AreEqual(" SYMBOL  8734 \\u \\f Calibri \\s 24 \\h", field.GetFieldCode());

builder.Writeln("Line 2");

// 3 - あ karakterini gösteren bir SEMBOL alanı ekleyin,
// Shift-JIS (Windows-932) kod sayfasını destekleyen bir yazı tipiyle:
field = (FieldSymbol)builder.InsertField(FieldType.FieldSymbol, true);
field.FontName = "MS Gothic";
field.CharacterCode = 0x82A0.ToString();
field.IsShiftJis = true;

Assert.AreEqual(" SYMBOL  33440 \\f \"MS Gothic\" \\j", field.GetFieldCode());

builder.Write("Line 3");

doc.Save(ArtifactsDir + "Field.SYMBOL.docx");
```

### Ayrıca bakınız

* class [FieldSymbol](../)
* ad alanı [Aspose.Words.Fields](../../fieldsymbol/)
* toplantı [Aspose.Words](../../../)


