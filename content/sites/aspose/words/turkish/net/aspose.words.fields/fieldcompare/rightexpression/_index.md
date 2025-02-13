---
title: FieldCompare.RightExpression
second_title: Aspose.Words for .NET API Referansı
description: FieldCompare mülk. Karşılaştırma ifadesinin doğru kısmını alır veya ayarlar.
type: docs
weight: 40
url: /tr/net/aspose.words.fields/fieldcompare/rightexpression/
---
## FieldCompare.RightExpression property

Karşılaştırma ifadesinin doğru kısmını alır veya ayarlar.

```csharp
public string RightExpression { get; set; }
```

### Örnekler

KARŞILAŞTIR alanını kullanarak ifadelerin nasıl karşılaştırılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldCompare field = (FieldCompare)builder.InsertField(FieldType.FieldCompare, true);
field.LeftExpression = "3";
field.ComparisonOperator = "<";
field.RightExpression = "2";
field.Update();

// KARŞILAŞTIR alanı, ifadesinin doğruluğuna bağlı olarak "0" veya "1" görüntüler.
// Bu ifadenin sonucu false olduğundan bu alan "0" gösterecektir.
Assert.AreEqual(" COMPARE  3 < 2", field.GetFieldCode());
Assert.AreEqual("0", field.Result);

builder.Writeln();

field = (FieldCompare)builder.InsertField(FieldType.FieldCompare, true);
field.LeftExpression = "5";
field.ComparisonOperator = "=";
field.RightExpression = "2 + 3";
field.Update();

// Bu alan, ifade doğru olduğundan "1" görüntüler.
Assert.AreEqual(" COMPARE  5 = \"2 + 3\"", field.GetFieldCode());
Assert.AreEqual("1", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.COMPARE.docx");
```

### Ayrıca bakınız

* class [FieldCompare](../)
* ad alanı [Aspose.Words.Fields](../../fieldcompare/)
* toplantı [Aspose.Words](../../../)


