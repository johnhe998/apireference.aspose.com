---
title: Class OlePackage
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Drawing.OlePackage klass. Ger åtkomst till OLEpaketets egenskaper.
type: docs
weight: 1030
url: /sv/net/aspose.words.drawing/olepackage/
---
## OlePackage class

Ger åtkomst till OLE-paketets egenskaper.

```csharp
public class OlePackage
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [DisplayName](../../aspose.words.drawing/olepackage/displayname/) { get; set; } | Hämtar eller ställer in OLE-paketets visningsnamn. |
| [FileName](../../aspose.words.drawing/olepackage/filename/) { get; set; } | Hämtar eller ställer in OLE-paketets filnamn. |

### Anmärkningar

OLE-paketet är ett äldre och "odokumenterat" sätt att lagra inbäddade objekt om OLE-hanteraren är okänd. Tidiga Windows-versioner som Windows 3.1, 95 och 98 hade Packager.exe-applikationen som kunde användas för att bädda in alla typer av data i dokument . Nu är den här applikationen utesluten från Windows men MS Word och andra applikationer använder den fortfarande för att bädda in data om OLE-hanteraren saknas eller är okänd.

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

* namnutrymme [Aspose.Words.Drawing](../../aspose.words.drawing/)
* hopsättning [Aspose.Words](../../)


