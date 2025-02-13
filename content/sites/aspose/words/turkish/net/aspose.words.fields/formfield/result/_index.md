---
title: FormField.Result
second_title: Aspose.Words for .NET API Referansı
description: FormField mülk. Bu form alanının sonucunu temsil eden bir dize alır veya ayarlar.
type: docs
weight: 170
url: /tr/net/aspose.words.fields/formfield/result/
---
## FormField.Result property

Bu form alanının sonucunu temsil eden bir dize alır veya ayarlar.

```csharp
public string Result { get; set; }
```

### Notlar

Bir metin form alanı için sonuç, alandaki metindir.

Bir onay kutusu form alanı için, işaretli veya işaretsiz olduğunu belirtmek için sonuç "1" veya "0" olabilir.

Açılır form alanı için sonuç, açılır menüden seçilen dizedir.

Ayar`Result` bir metin formu alanı için belirtilen format metnini uygulamıyor[`TextInputFormat`](../textinputformat/) . Bir değer belirlemek ve the biçimini uygulamak istiyorsanız,[`SetTextInputValue`](../settextinputvalue/) yöntem.

Bir metin formu alanı için[`TextInputDefault`](../textinputdefault/) değer, eğer application ise*value* dır-dir`hükümsüz`.

### Örnekler

Birleşik giriş kutusunun nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please select a fruit: ");

// Kullanıcının bir dizi diziden bir seçenek seçmesine izin verecek bir birleşik giriş kutusu ekleyin.
FormField comboBox = builder.InsertComboBox("MyComboBox", new[] { "Apple", "Banana", "Cherry" }, 0);

Assert.AreEqual("MyComboBox", comboBox.Name);
Assert.AreEqual(FieldType.FieldFormDropDown, comboBox.Type);
Assert.AreEqual("Apple", comboBox.Result);

// Form alanı bir "select" html etiketi şeklinde görünecektir.
doc.Save(ArtifactsDir + "FormFields.Create.html");
```

### Ayrıca bakınız

* class [FormField](../)
* ad alanı [Aspose.Words.Fields](../../formfield/)
* toplantı [Aspose.Words](../../../)


