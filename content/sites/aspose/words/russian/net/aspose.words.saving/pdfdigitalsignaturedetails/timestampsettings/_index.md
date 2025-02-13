---
title: PdfDigitalSignatureDetails.TimestampSettings
second_title: Справочник по API Aspose.Words для .NET
description: PdfDigitalSignatureDetails свойство. Получает или задает параметры временной метки цифровой подписи.
type: docs
weight: 70
url: /ru/net/aspose.words.saving/pdfdigitalsignaturedetails/timestampsettings/
---
## PdfDigitalSignatureDetails.TimestampSettings property

Получает или задает параметры временной метки цифровой подписи.

```csharp
public PdfDigitalSignatureTimestampSettings TimestampSettings { get; set; }
```

### Примечания

Значение по умолчанию равно null, и цифровая подпись не будет иметь отметку времени. Если для этого свойства задано допустимое значение[`PdfDigitalSignatureTimestampSettings`](../../pdfdigitalsignaturetimestampsettings/) object, , то цифровая подпись в документе PDF будет иметь отметку времени.

### Примеры

Показывает, как подписать сохраненный PDF-документ цифровой подписью и поставить на нем отметку времени.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Signed PDF contents.");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions options = new PdfSaveOptions();

 // Создаем цифровую подпись и назначаем ее нашему объекту SaveOptions, чтобы подписывать документ при его сохранении в формате PDF.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
options.DigitalSignatureDetails = new PdfDigitalSignatureDetails(certificateHolder, "Test Signing", "Aspose Office", DateTime.Now);

// Создать временную метку, проверенную авторитетом.
options.DigitalSignatureDetails.TimestampSettings =
    new PdfDigitalSignatureTimestampSettings("https://freetsa.org/tsr", "JohnDoe", "MyPassword");

// Срок жизни временной метки по умолчанию составляет 100 секунд.
Assert.AreEqual(100.0d, options.DigitalSignatureDetails.TimestampSettings.Timeout.TotalSeconds);

// Мы можем установить период ожидания через конструктор.
options.DigitalSignatureDetails.TimestampSettings =
    new PdfDigitalSignatureTimestampSettings("https://freetsa.org/tsr", "JohnDoe", "MyPassword", TimeSpan.FromMinutes(30));

Assert.AreEqual(1800.0d, options.DigitalSignatureDetails.TimestampSettings.Timeout.TotalSeconds);
Assert.AreEqual("https://freetsa.org/tsr", options.DigitalSignatureDetails.TimestampSettings.ServerUrl);
Assert.AreEqual("JohnDoe", options.DigitalSignatureDetails.TimestampSettings.UserName);
Assert.AreEqual("MyPassword", options.DigitalSignatureDetails.TimestampSettings.Password);

// В это время метод "Сохранить" применит нашу подпись к выходному документу.
doc.Save(ArtifactsDir + "PdfSaveOptions.PdfDigitalSignatureTimestamp.pdf", options);
```

### Смотрите также

* class [PdfDigitalSignatureTimestampSettings](../../pdfdigitalsignaturetimestampsettings/)
* class [PdfDigitalSignatureDetails](../)
* пространство имен [Aspose.Words.Saving](../../pdfdigitalsignaturedetails/)
* сборка [Aspose.Words](../../../)


