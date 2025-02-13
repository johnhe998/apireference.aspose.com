---
title: OoxmlSaveOptions.Password
second_title: Aspose.Words för .NET API Referens
description: OoxmlSaveOptions fast egendom. Hämtar/ställer in ett lösenord för att kryptera dokument med ECMA376 Standard krypteringsalgoritm.
type: docs
weight: 50
url: /sv/net/aspose.words.saving/ooxmlsaveoptions/password/
---
## OoxmlSaveOptions.Password property

Hämtar/ställer in ett lösenord för att kryptera dokument med ECMA376 Standard krypteringsalgoritm.

```csharp
public string Password { get; set; }
```

### Anmärkningar

För att spara dokument utan kryptering bör denna egenskap vara null eller tom sträng.

### Exempel

Visar hur man skapar ett lösenordskrypterat Office Open XML-dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.Password = "MyPassword";

doc.Save(ArtifactsDir + "OoxmlSaveOptions.Password.docx", saveOptions);

// Vi kommer inte att kunna öppna detta dokument med Microsoft Word eller
// Aspose.Words utan att ange rätt lösenord.
Assert.Throws<IncorrectPasswordException>(() =>
    doc = new Document(ArtifactsDir + "OoxmlSaveOptions.Password.docx"));

// Öppna det krypterade dokumentet genom att skicka in rätt lösenord i ett LoadOptions-objekt.
doc = new Document(ArtifactsDir + "OoxmlSaveOptions.Password.docx", new LoadOptions("MyPassword"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Se även

* class [OoxmlSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../ooxmlsaveoptions/)
* hopsättning [Aspose.Words](../../../)


