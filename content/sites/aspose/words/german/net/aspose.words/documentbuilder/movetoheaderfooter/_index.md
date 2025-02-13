---
title: DocumentBuilder.MoveToHeaderFooter
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentBuilder methode. Bewegt den Cursor an den Anfang einer Kopf oder Fußzeile im aktuellen Abschnitt.
type: docs
weight: 520
url: /de/net/aspose.words/documentbuilder/movetoheaderfooter/
---
## DocumentBuilder.MoveToHeaderFooter method

Bewegt den Cursor an den Anfang einer Kopf- oder Fußzeile im aktuellen Abschnitt.

```csharp
public void MoveToHeaderFooter(HeaderFooterType headerFooterType)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| headerFooterType | HeaderFooterType | Gibt die Kopf- oder Fußzeile an, zu der verschoben werden soll. |

### Bemerkungen

Nachdem Sie den Cursor in eine Kopf- oder Fußzeile bewegt haben, können Sie die restlichen DocumentBuilder -Methoden verwenden, um den Inhalt der Kopf- oder Fußzeile zu ändern.

Wenn Sie für die erste Seite unterschiedliche Kopf- und Fußzeilen erstellen möchten, müssen Sie festlegen[`DifferentFirstPageHeaderFooter`](../../pagesetup/differentfirstpageheaderfooter/).

Wenn Sie für gerade und ungerade Seiten unterschiedliche Kopf- und Fußzeilen erstellen möchten, müssen Sie festlegen[`OddAndEvenPagesHeaderFooter`](../../pagesetup/oddandevenpagesheaderfooter/).

Verwenden[`MoveToSection`](../movetosection/) um aus der Kopfzeile in den Haupttext zu gelangen.

### Beispiele

Zeigt, wie ein Bild eingefügt und als Wasserzeichen verwendet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie das Bild in die Kopfzeile ein, damit es auf jeder Seite sichtbar ist.
Image image = Image.FromFile(ImageDir + "Transparent background logo.png");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
Shape shape = builder.InsertImage(image);
shape.WrapType = WrapType.None;
shape.BehindText = true;

// Platzieren Sie das Bild in der Mitte der Seite.
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.Left = (builder.PageSetup.PageWidth - shape.Width) / 2;
shape.Top = (builder.PageSetup.PageHeight - shape.Height) / 2;

doc.Save(ArtifactsDir + "DocumentBuilder.InsertWatermark.docx");
```

Zeigt, wie ein Bild eingefügt und als Wasserzeichen verwendet wird (.NetStandard 2.0).

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie das Bild in die Kopfzeile ein, damit es auf jeder Seite sichtbar ist.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

using (SKBitmap image = SKBitmap.Decode(ImageDir + "Transparent background logo.png"))
{
    builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
    Shape shape = builder.InsertImage(image);
    shape.WrapType = WrapType.None;
    shape.BehindText = true;

    // Platzieren Sie das Bild in der Mitte der Seite.
    shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
    shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
    shape.Left = (builder.PageSetup.PageWidth - shape.Width) / 2;
    shape.Top = (builder.PageSetup.PageHeight - shape.Height) / 2;
}

doc.Save(ArtifactsDir + "DocumentBuilder.InsertWatermarkNetStandard2.docx");
```

Zeigt, wie Kopf- und Fußzeilen in einem Dokument mit DocumentBuilder erstellt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Geben Sie an, dass wir unterschiedliche Kopf- und Fußzeilen für die erste, gerade und ungerade Seite wünschen.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Kopfzeilen erstellen, dann drei Seiten zum Dokument hinzufügen, um jeden Kopfzeilentyp anzuzeigen.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page3");

doc.Save(ArtifactsDir + "DocumentBuilder.HeadersAndFooters.docx");
```

### Siehe auch

* enum [HeaderFooterType](../../headerfootertype/)
* class [DocumentBuilder](../)
* namensraum [Aspose.Words](../../documentbuilder/)
* Montage [Aspose.Words](../../../)


