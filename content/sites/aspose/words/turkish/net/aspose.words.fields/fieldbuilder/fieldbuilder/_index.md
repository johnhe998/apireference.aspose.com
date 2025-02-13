---
title: FieldBuilder.FieldBuilder
second_title: Aspose.Words for .NET API Referansı
description: FieldBuilder inşaatçı. Şunun bir örneğini başlatırFieldBuilder sınıf.
type: docs
weight: 10
url: /tr/net/aspose.words.fields/fieldbuilder/fieldbuilder/
---
## FieldBuilder constructor

Şunun bir örneğini başlatır:[`FieldBuilder`](../) sınıf.

```csharp
public FieldBuilder(FieldType fieldType)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| fieldType | FieldType | İnşa edilecek alanın türü. |

### Örnekler

Alan oluşturucu kullanarak bir alanın nasıl oluşturulacağını ve ekleneceğini gösterir.

```csharp
Document doc = new Document();

// Bir belgeye metin içeriği eklemenin uygun bir yolu belge oluşturucudur.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write(" Hello world! This text is one Run, which is an inline node.");

// Alanların, parça parça alan kodu oluşturmak için kullanabileceğimiz oluşturucuları vardır.
// Bu durumda, ABD posta kodunu temsil eden bir BARKOD alanı oluşturacağız,
// ve ardından bir Run'ın önüne ekleyin.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldBarcode);
fieldBuilder.AddArgument("90210");
fieldBuilder.AddSwitch("\\f", "A");
fieldBuilder.AddSwitch("\\u");

fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph.Runs[0]);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.CreateWithFieldBuilder.docx");
```

### Ayrıca bakınız

* enum [FieldType](../../fieldtype/)
* class [FieldBuilder](../)
* ad alanı [Aspose.Words.Fields](../../fieldbuilder/)
* toplantı [Aspose.Words](../../../)


