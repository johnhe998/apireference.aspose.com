---
title: FieldRD.FileName
second_title: Aspose.Words für .NET-API-Referenz
description: FieldRD eigendom. Ruft den Namen der Datei ab oder legt ihn fest die beim Generieren eines Inhaltsverzeichnisses Rechtsgrundlagenverzeichnisses oder Index einzubeziehen ist.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldrd/filename/
---
## FieldRD.FileName property

Ruft den Namen der Datei ab oder legt ihn fest, die beim Generieren eines Inhaltsverzeichnisses, Rechtsgrundlagenverzeichnisses oder Index einzubeziehen ist.

```csharp
public string FileName { get; set; }
```

### Beispiele

Zeigt die Verwendung des RD-Felds zum Erstellen von Inhaltsverzeichniseinträgen aus Überschriften in anderen Dokumenten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Verwenden Sie einen Document Builder, um ein Inhaltsverzeichnis einzufügen,
// und fügen Sie dann einen Eintrag für das Inhaltsverzeichnis auf der folgenden Seite hinzu.
builder.InsertField(FieldType.FieldTOC, true);
builder.InsertBreak(BreakType.PageBreak);
builder.CurrentParagraph.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("TOC entry from within this document");

// Fügt ein RD-Feld ein, das in seiner FileName-Eigenschaft auf ein anderes lokales Dateisystemdokument verweist.
// Das Inhaltsverzeichnis akzeptiert nun auch alle Überschriften aus dem referenzierten Dokument als Einträge für seine Tabelle.
FieldRD field = (FieldRD)builder.InsertField(FieldType.FieldRefDoc, true);
field.FileName = "ReferencedDocument.docx";
field.IsPathRelative = true;

Assert.AreEqual(" RD  ReferencedDocument.docx \\f", field.GetFieldCode());

 // Erstellen Sie das Dokument, auf das das RD-Feld verweist, und fügen Sie eine Überschrift ein.
// Diese Überschrift wird als Eintrag im TOC-Feld in unserem ersten Dokument angezeigt.
Document referencedDoc = new Document();
DocumentBuilder refDocBuilder = new DocumentBuilder(referencedDoc);
refDocBuilder.CurrentParagraph.ParagraphFormat.StyleName = "Heading 1";
refDocBuilder.Writeln("TOC entry from referenced document");
referencedDoc.Save(ArtifactsDir + "ReferencedDocument.docx");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.RD.docx");
```

### Siehe auch

* class [FieldRD](../)
* namensraum [Aspose.Words.Fields](../../fieldrd/)
* Montage [Aspose.Words](../../../)


