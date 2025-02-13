---
title: FieldMacroButton.DisplayText
second_title: Aspose.Words for .NET API Referansı
description: FieldMacroButton mülk. Metni makroyu veya komutu çalıştırmak için seçilen düğme olarak görünecek şekilde alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.fields/fieldmacrobutton/displaytext/
---
## FieldMacroButton.DisplayText property

Metni, makroyu veya komutu çalıştırmak için seçilen "düğme" olarak görünecek şekilde alır veya ayarlar.

```csharp
public string DisplayText { get; set; }
```

### Örnekler

Bir belgenin makrolarını tıklayarak çalıştırmamıza izin vermek için MACROBUTTON alanlarının nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Macro.docm");
DocumentBuilder builder = new DocumentBuilder(doc);

Assert.IsTrue(doc.HasMacros);

// Bir MACROBUTTON alanı ekleyin ve MacroName özelliğinde belgenin makrolarından birine ada göre başvuruda bulunun.
FieldMacroButton field = (FieldMacroButton)builder.InsertField(FieldType.FieldMacroButton, true);
field.MacroName = "MyMacro";
field.DisplayText = "Double click to run macro: " + field.MacroName;

Assert.AreEqual(" MACROBUTTON  MyMacro Double click to run macro: MyMacro", field.GetFieldCode());

// Microsoft Word ile birlikte gelen bir makro olan "ViewZoom200"e başvurmak için özelliği kullanın.
// Diğer tüm makroları Görünüm -> Makrolar (açılır menü) -> Makroları Görüntüle.
// Bu menüde, "Makrolar:" açılır menüsünden "Kelime Komutları"nı seçin.
// Belgemiz stok makrosu ile aynı ada sahip özel bir makro içeriyorsa,
// makromuz MACROBUTTON alanının çalıştıracağı makro olacaktır.
builder.InsertParagraph();
field = (FieldMacroButton)builder.InsertField(FieldType.FieldMacroButton, true);
field.MacroName = "ViewZoom200";
field.DisplayText = "Run " + field.MacroName;

Assert.AreEqual(" MACROBUTTON  ViewZoom200 Run ViewZoom200", field.GetFieldCode());

// Belgeyi makro etkin bir belge türü olarak kaydedin.
doc.Save(ArtifactsDir + "Field.MACROBUTTON.docm");
```

### Ayrıca bakınız

* class [FieldMacroButton](../)
* ad alanı [Aspose.Words.Fields](../../fieldmacrobutton/)
* toplantı [Aspose.Words](../../../)


