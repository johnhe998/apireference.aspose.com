---
title: PageSetup.BorderSurroundsFooter
second_title: Aspose.Words for .NET API Referansı
description: PageSetup mülk. Sayfa kenarlığının altbilgiyi içerip içermediğini belirtir.
type: docs
weight: 60
url: /tr/net/aspose.words/pagesetup/bordersurroundsfooter/
---
## PageSetup.BorderSurroundsFooter property

Sayfa kenarlığının altbilgiyi içerip içermediğini belirtir.

```csharp
public bool BorderSurroundsFooter { get; set; }
```

### Notlar

Bu özelliğin değiştirilmesinin belgedeki tüm bölümleri etkilediğini unutmayın.

### Örnekler

Sayfaya ve üstbilgiye/altbilgiye nasıl kenarlık uygulanacağını gösterir.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world! This is the main body text.");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("This is the header.");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("This is the footer.");
builder.MoveToDocumentEnd();

// Çift çizgili mavi bir kenarlık ekleyin.
PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.Borders.LineStyle = LineStyle.Double;
pageSetup.Borders.Color = Color.Blue;

// Bir bölümün PageSetup nesnesi, aşağıdakileri belirleyen "BorderSurroundsHeader" ve "BorderSurroundsFooter" bayraklarına sahiptir.
// bir sayfa kenarlığının ana gövde metnini çevreleyip çevrelemediği, sırasıyla üstbilgi veya altbilgiyi de içerir.
// Başlığı kenarlığımızla çevrelemek için "BorderSurroundsHeader" bayrağını "true" olarak ayarlayın,
// ve sonra "BorderSurroundsFooter" bayrağını altbilgiyi sınırın dışında bırakacak şekilde ayarlayın.
pageSetup.BorderSurroundsHeader = true;
pageSetup.BorderSurroundsFooter = false;

doc.Save(ArtifactsDir + "PageSetup.PageBorder.docx");
```

### Ayrıca bakınız

* class [PageSetup](../)
* ad alanı [Aspose.Words](../../pagesetup/)
* toplantı [Aspose.Words](../../../)


