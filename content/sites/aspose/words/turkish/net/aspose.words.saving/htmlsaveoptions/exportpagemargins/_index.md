---
title: HtmlSaveOptions.ExportPageMargins
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. Sayfa kenar boşluklarının HTML MHTML veya EPUB olarak dışa aktarılıp aktarılmayacağını belirtir. Varsayılanyanlış .
type: docs
weight: 220
url: /tr/net/aspose.words.saving/htmlsaveoptions/exportpagemargins/
---
## HtmlSaveOptions.ExportPageMargins property

Sayfa kenar boşluklarının HTML, MHTML veya EPUB olarak dışa aktarılıp aktarılmayacağını belirtir. Varsayılan`yanlış` .

```csharp
public bool ExportPageMargins { get; set; }
```

### Notlar

Aspose.Words varsayılan olarak sayfa kenar boşluklarını göstermez. Herhangi bir öğe belge kenarı tarafından tamamen veya kısmen kırpılırsa, görüntülenen alan bu seçenek ile genişletilebilir.

### Örnekler

Çıkış HTML belgelerinde sınır dışı nesnelerin nasıl gösterileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sarma olmadan bir şekil eklemek için bir oluşturucu kullanın.
Shape shape = builder.InsertShape(ShapeType.Cube, 200, 200);

shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.WrapType = WrapType.None;

// Negatif şekil konumu değerleri, şekli sayfa sınırlarının dışına yerleştirebilir.
// Bunu HTML'ye aktarırsak, şekil kesilmiş olarak görünecektir.
shape.Left = -150;

// Belgeyi HTML'ye kaydederken SaveOptions nesnesini iletebiliriz
// Sayfanın, sınırların dışındaki nesneleri tam olarak görüntüleyecek şekilde ayarlanıp ayarlanmayacağına karar vermek için.
// "ExportPageMargins" bayrağını "true" olarak ayarlarsak, şekil çıktı HTML'sinde tamamen görünür olacaktır.
// "ExportPageMargins" bayrağını "false" olarak ayarlarsak,
// belgemiz, Microsoft Word'de göreceğimiz gibi kesilmiş şekli gösterecek.
HtmlSaveOptions options = new HtmlSaveOptions { ExportPageMargins = exportPageMargins };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportPageMargins.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportPageMargins.html");

if (exportPageMargins)
{
    Assert.True(outDocContents.Contains("<style type=\"text/css\">div.Section1 { margin:70.85pt }</style>"));
    Assert.True(outDocContents.Contains("<div class=\"Section1\"><p style=\"margin-top:0pt; margin-left:151pt; margin-bottom:0pt\">"));
}
else
{
    Assert.False(outDocContents.Contains("style type=\"text/css\">"));
    Assert.True(outDocContents.Contains("<div><p style=\"margin-top:0pt; margin-left:221.85pt; margin-bottom:0pt\">"));
}
```

### Ayrıca bakınız

* class [HtmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlsaveoptions/)
* toplantı [Aspose.Words](../../../)


