---
title: HtmlSaveOptions.ExportShapesAsSvg
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. Shape düğümler HTML MHTML veya EPUBa kaydedilirken SVG görüntülerine dönüştürülür. Varsayılan değeryanlış .
type: docs
weight: 260
url: /tr/net/aspose.words.saving/htmlsaveoptions/exportshapesassvg/
---
## HtmlSaveOptions.ExportShapesAsSvg property

[`Shape`](../../../aspose.words.drawing/shape/) düğümler, HTML, MHTML veya EPUB'a kaydedilirken SVG görüntülerine dönüştürülür. Varsayılan değer`yanlış` .

```csharp
public bool ExportShapesAsSvg { get; set; }
```

### Notlar

Bu seçenek olarak ayarlanırsa`doğru` ,[`Shape`](../../../aspose.words.drawing/shape/) düğümler &lt;svg&gt; öğeleri olarak dışa aktarılır. Aksi takdirde, bit eşlemlere dönüştürülür ve &lt;img&gt; öğeleri olarak dışa aktarılır.

Bu seçeneklerin metin kutularını da etkilediğini unutmayın, çünkü bunlar[`Shape`](../../../aspose.words.drawing/shape/) Nodes. Sonuç olarak, bu seçenek olarak ayarlanırsa`doğru` , geçersiz kılarExportTextBoxAsSvgproperty değeri ve metin kutularının SVG'ye dönüştürülmesine neden olur.

### Örnekler

Şeklin ölçeklenebilir vektör grafikleri olarak nasıl dışa aktarılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBox = builder.InsertShape(ShapeType.TextBox, 100.0, 60.0);
builder.MoveTo(textBox.FirstParagraph);
builder.Write("My text box");

// Belgeyi HTML'ye kaydettiğimizde, SaveOptions nesnesini iletebiliriz
// kaydetme işleminin metin kutusu şekillerini nasıl dışa aktaracağını belirlemek için.
// "ExportTextBoxAsSvg" bayrağını "true" olarak ayarlarsak,
// kaydetme işlemi, metin içeren şekilleri SVG nesnelerine dönüştürecektir.
// "ExportTextBoxAsSvg" bayrağını "false" olarak ayarlarsak,
// kaydetme işlemi, metin içeren şekilleri resimlere dönüştürecektir.
HtmlSaveOptions options = new HtmlSaveOptions { ExportShapesAsSvg = exportShapesAsSvg };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportTextBox.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportTextBox.html");

if (exportShapesAsSvg)
{
    Assert.True(outDocContents.Contains(
        "<span style=\"-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\">" +
        "<svg xmlns=\"http://www.w3.org/2000/svg\" xmlns:xlink=\"http://www.w3.org/1999/xlink\" version=\"1.1\" width=\"133\" height= \"80\">"));
}
else
{
    Assert.True(outDocContents.Contains(
        "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
            "<img src=\"HtmlSaveOptions.ExportTextBox.001.png\" width=\"136\" height=\"83\" alt=\"\" " +
            "style=\"-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\" />" +
        "</p>"));
}
```

### Ayrıca bakınız

* class [HtmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlsaveoptions/)
* toplantı [Aspose.Words](../../../)


