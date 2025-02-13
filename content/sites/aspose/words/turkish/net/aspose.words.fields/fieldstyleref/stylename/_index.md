---
title: FieldStyleRef.StyleName
second_title: Aspose.Words for .NET API Referansı
description: FieldStyleRef mülk. Aranacak metnin biçimlendirildiği stilin adını alır veya ayarlar.
type: docs
weight: 70
url: /tr/net/aspose.words.fields/fieldstyleref/stylename/
---
## FieldStyleRef.StyleName property

Aranacak metnin biçimlendirildiği stilin adını alır veya ayarlar.

```csharp
public string StyleName { get; set; }
```

### Örnekler

STYLEREF alanlarının nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bir Microsoft Word liste şablonu kullanarak bir liste oluşturun.
Aspose.Words.Lists.List list = doc.Lists.Add(Aspose.Words.Lists.ListTemplate.NumberDefault);

// Oluşturulan bu listede "1.a )" görüntülenecektir.
 // Köşeli ayraçtan önceki boşluk, bastırabileceğimiz sınırlayıcı olmayan bir karakterdir.
list.ListLevels[0].NumberFormat = "\x0000.";
list.ListLevels[1].NumberFormat = "\x0001 )";

// STYLEREF alanlarının başvuracağı metin ekleyin ve paragraf stilleri uygulayın.
builder.ListFormat.List = list;
builder.ListFormat.ListIndent();
builder.ParagraphFormat.Style = doc.Styles["List Paragraph"];
builder.Writeln("Item 1");
builder.ParagraphFormat.Style = doc.Styles["Quote"];
builder.Writeln("Item 2");
builder.ParagraphFormat.Style = doc.Styles["List Paragraph"];
builder.Writeln("Item 3");
builder.ListFormat.RemoveNumbers();
builder.ParagraphFormat.Style = doc.Styles["Normal"];

// Başlığa bir STYLEREF alanı yerleştirin ve belgedeki ilk "Liste Paragrafı" stili metni görüntüleyin.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
FieldStyleRef field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "List Paragraph";

// Altbilgiye bir STYLEREF alanı yerleştirin ve son metni göstermesini sağlayın.
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "List Paragraph";
field.SearchFromBottom = true;

builder.MoveToDocumentEnd();

// Listelerin liste numaralarını referans almak için STYLEREF alanlarını da kullanabiliriz.
builder.Write("\nParagraph number: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumber = true;

builder.Write("\nParagraph number, relative context: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumberInRelativeContext = true;

builder.Write("\nParagraph number, full context: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumberInFullContext = true;

builder.Write("\nParagraph number, full context, non-delimiter chars suppressed: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumberInFullContext = true;
field.SuppressNonDelimiters = true;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.STYLEREF.docx");
```

### Ayrıca bakınız

* class [FieldStyleRef](../)
* ad alanı [Aspose.Words.Fields](../../fieldstyleref/)
* toplantı [Aspose.Words](../../../)


