---
title: FieldPrint.PostScriptGroup
second_title: Aspose.Words for .NET API Referansı
description: FieldPrint mülk. PostScript talimatlarının üzerinde çalıştığı çizim dikdörtgenini alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.fields/fieldprint/postscriptgroup/
---
## FieldPrint.PostScriptGroup property

PostScript talimatlarının üzerinde çalıştığı çizim dikdörtgenini alır veya ayarlar.

```csharp
public string PostScriptGroup { get; set; }
```

### Örnekler

YAZDIR alanı eklemeyi gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("My paragraph");

// YAZDIR alanı, yazıcıya talimat gönderebilir.
FieldPrint field = (FieldPrint)builder.InsertField(FieldType.FieldPrint, true);

// Yazıcının yönergeleri yerine getireceği alanı ayarlayın.
// Bu durumda PRINT alanımızı içeren paragraf olacaktır.
field.PostScriptGroup = "para";

// Belgemizi yazdırmak için PostScript'i destekleyen bir yazıcı kullandığımızda,
// bu komut, "field.PostScriptGroup" içinde belirttiğimiz tüm alanı beyaza çevirecektir.
field.PrinterInstructions = "erasepage";

Assert.AreEqual(" PRINT  erasepage \\p para", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.PRINT.docx");
```

### Ayrıca bakınız

* class [FieldPrint](../)
* ad alanı [Aspose.Words.Fields](../../fieldprint/)
* toplantı [Aspose.Words](../../../)


