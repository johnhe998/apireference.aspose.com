---
title: Interface IBarcodeGenerator
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Fields.IBarcodeGenerator arayüz. Barkod özel oluşturucu için genel arabirim. Uygulama user. tarafından sağlanmalıdır.
type: docs
weight: 2500
url: /tr/net/aspose.words.fields/ibarcodegenerator/
---
## IBarcodeGenerator interface

Barkod özel oluşturucu için genel arabirim. Uygulama user. tarafından sağlanmalıdır.

```csharp
public interface IBarcodeGenerator
```

## yöntemler

| İsim | Tanım |
| --- | --- |
| [GetBarcodeImage](../../aspose.words.fields/ibarcodegenerator/getbarcodeimage/)(BarcodeParameters) | Parametre setini kullanarak barkod görüntüsü oluşturun (DisplayBarcode alanı için). |
| [GetOldBarcodeImage](../../aspose.words.fields/ibarcodegenerator/getoldbarcodeimage/)(BarcodeParameters) | Parametre setini kullanarak barkod görüntüsü oluşturun (eski moda Barkod alanı için). |

### Notlar

Generator örneği,[`BarcodeGenerator`](../fieldoptions/barcodegenerator/) özellik.

### Örnekler

Barkod oluşturucunun nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Barkod oluşturmak için özel bir IBarcodeGenerator uygulaması kullanabiliriz,
// ve ardından bunları görüntü olarak belgeye ekleyin.
doc.FieldOptions.BarcodeGenerator = new CustomBarcodeGenerator();

// Aşağıda, jeneratörümüzü kullanarak oluşturabileceğimiz dört farklı barkod türü örneği bulunmaktadır.
// Her barkod için yeni bir barkod parametresi seti belirleriz ve ardından görüntüyü oluştururuz.
// Daha sonra görüntüyü belgeye ekleyebilir veya yerel dosya sistemine kaydedebiliriz.
// 1 - QR kodu:
BarcodeParameters barcodeParameters = new BarcodeParameters
{
    BarcodeType = "QR",
    BarcodeValue = "ABC123",
    BackgroundColor = "0xF8BD69",
    ForegroundColor = "0xB5413B",
    ErrorCorrectionLevel = "3",
    ScalingFactor = "250",
    SymbolHeight = "1000",
    SymbolRotation = "0"
};

Image img = doc.FieldOptions.BarcodeGenerator.GetBarcodeImage(barcodeParameters);
img.Save(ArtifactsDir + "FieldOptions.BarcodeGenerator.QR.jpg");

builder.InsertImage(img);

// 2 - EAN13 barkodu:
barcodeParameters = new BarcodeParameters
{
    BarcodeType = "EAN13",
    BarcodeValue = "501234567890",
    DisplayText = true,
    PosCodeStyle = "CASE",
    FixCheckDigit = true
};

img = doc.FieldOptions.BarcodeGenerator.GetBarcodeImage(barcodeParameters);
img.Save(ArtifactsDir + "FieldOptions.BarcodeGenerator.EAN13.jpg");
builder.InsertImage(img);

// 3 - KOD39 barkodu:
barcodeParameters = new BarcodeParameters
{
    BarcodeType = "CODE39",
    BarcodeValue = "12345ABCDE",
    AddStartStopChar = true
};

img = doc.FieldOptions.BarcodeGenerator.GetBarcodeImage(barcodeParameters);
img.Save(ArtifactsDir + "FieldOptions.BarcodeGenerator.CODE39.jpg");
builder.InsertImage(img);

// 4 - ITF14 barkodu:
barcodeParameters = new BarcodeParameters
{
    BarcodeType = "ITF14",
    BarcodeValue = "09312345678907",
    CaseCodeStyle = "STD"
};

img = doc.FieldOptions.BarcodeGenerator.GetBarcodeImage(barcodeParameters);
img.Save(ArtifactsDir + "FieldOptions.BarcodeGenerator.ITF14.jpg");
builder.InsertImage(img);

doc.Save(ArtifactsDir + "FieldOptions.BarcodeGenerator.docx");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Fields](../../aspose.words.fields/)
* toplantı [Aspose.Words](../../)


