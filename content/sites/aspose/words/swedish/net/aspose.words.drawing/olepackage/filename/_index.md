---
title: OlePackage.FileName
second_title: Aspose.Words för .NET API Referens
description: OlePackage fast egendom. Hämtar eller ställer in OLEpaketets filnamn.
type: docs
weight: 20
url: /sv/net/aspose.words.drawing/olepackage/filename/
---
## OlePackage.FileName property

Hämtar eller ställer in OLE-paketets filnamn.

```csharp
public string FileName { get; set; }
```

### Exempel

Visar hur man infogar ett OLE-objekt i ett dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// OLE-objekt tillåter oss att öppna andra filer i det lokala filsystemet med ett annat installerat program
// i vårt operativsystem genom att dubbelklicka på formen som innehåller OLE-objektet i dokumentets brödtext.
// I det här fallet kommer vår externa fil att vara ett ZIP-arkiv.
byte[] zipFileBytes = File.ReadAllBytes(DatabaseDir + "cat001.zip");

using (MemoryStream stream = new MemoryStream(zipFileBytes))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);

    shape.OleFormat.OlePackage.FileName = "Package file name.zip";
    shape.OleFormat.OlePackage.DisplayName = "Package display name.zip";
}

doc.Save(ArtifactsDir + "Shape.InsertOlePackage.docx");
```

### Se även

* class [OlePackage](../)
* namnutrymme [Aspose.Words.Drawing](../../olepackage/)
* hopsättning [Aspose.Words](../../../)


