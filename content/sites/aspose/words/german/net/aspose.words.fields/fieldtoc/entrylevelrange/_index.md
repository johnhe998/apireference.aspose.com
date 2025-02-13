---
title: FieldToc.EntryLevelRange
second_title: Aspose.Words für .NET-API-Referenz
description: FieldToc eigendom. Ruft einen Bereich von Ebenen der einzuschließenden Inhaltsverzeichniseinträge ab oder legt diesen fest.
type: docs
weight: 60
url: /de/net/aspose.words.fields/fieldtoc/entrylevelrange/
---
## FieldToc.EntryLevelRange property

Ruft einen Bereich von Ebenen der einzuschließenden Inhaltsverzeichniseinträge ab oder legt diesen fest.

```csharp
public string EntryLevelRange { get; set; }
```

### Beispiele

Zeigt, wie man ein TOC-Feld einfügt und filtert, welche TC-Felder als Einträge enden.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Fügen Sie ein TOC-Feld ein, das alle TC-Felder in ein Inhaltsverzeichnis kompiliert.
    FieldToc fieldToc = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

    // Konfigurieren Sie das Feld nur so, dass es TC-Einträge vom Typ "A" und einer Eintragsebene zwischen 1 und 3 aufnimmt.
    fieldToc.EntryIdentifier = "A";
    fieldToc.EntryLevelRange = "1-3";

    Assert.AreEqual(" TOC  \\f A \\l 1-3", fieldToc.GetFieldCode());

    // Diese beiden Einträge erscheinen in der Tabelle.
    builder.InsertBreak(BreakType.PageBreak);
    InsertTocEntry(builder, "TC field 1", "A", "1");
    InsertTocEntry(builder, "TC field 2", "A", "2");

    Assert.AreEqual(" TC  \"TC field 1\" \\n \\f A \\l 1", doc.Range.Fields[1].GetFieldCode());

    // Dieser Eintrag wird in der Tabelle weggelassen, da er einen anderen Typ als "A" hat.
    InsertTocEntry(builder, "TC field 3", "B", "1");

    // Dieser Eintrag wird aus der Tabelle weggelassen, da er eine Eintragsebene außerhalb des Bereichs 1-3 hat.
    InsertTocEntry(builder, "TC field 4", "A", "5");

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.TC.docx");

/// <summary>
/// Verwenden Sie einen Document Builder, um ein TC-Feld einzufügen.
/// </summary>
public void InsertTocEntry(DocumentBuilder builder, string text, string typeIdentifier, string entryLevel)
{
    FieldTC fieldTc = (FieldTC)builder.InsertField(FieldType.FieldTOCEntry, true);
    fieldTc.OmitPageNumber = true;
    fieldTc.Text = text;
    fieldTc.TypeIdentifier = typeIdentifier;
    fieldTc.EntryLevel = entryLevel;
}
```

### Siehe auch

* class [FieldToc](../)
* namensraum [Aspose.Words.Fields](../../fieldtoc/)
* Montage [Aspose.Words](../../../)


