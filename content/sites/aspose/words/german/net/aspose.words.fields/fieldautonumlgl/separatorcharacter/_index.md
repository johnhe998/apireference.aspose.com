---
title: FieldAutoNumLgl.SeparatorCharacter
second_title: Aspose.Words für .NET-API-Referenz
description: FieldAutoNumLgl eigendom. Ruft das zu verwendende Trennzeichen ab oder setzt es.
type: docs
weight: 30
url: /de/net/aspose.words.fields/fieldautonumlgl/separatorcharacter/
---
## FieldAutoNumLgl.SeparatorCharacter property

Ruft das zu verwendende Trennzeichen ab oder setzt es.

```csharp
public string SeparatorCharacter { get; set; }
```

### Beispiele

Zeigt, wie ein Dokument mithilfe von AUTONUMLGL-Feldern organisiert wird.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    const string fillerText = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. " +
                              "\nUt enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. ";

    // AUTONUMLGL-Felder zeigen eine Zahl an, die sich bei jedem AUTONUMLGL-Feld innerhalb der aktuellen Überschriftenebene erhöht.
    // Diese Felder verwalten eine separate Zählung für jede Überschriftenebene,
     // und jedes Feld zeigt auch die Anzahl der AUTONUMLGL-Felder für alle Überschriftenebenen unterhalb seiner eigenen an.
    // Das Ändern der Zählung für eine beliebige Überschriftenebene setzt die Zählungen für alle Ebenen über dieser Ebene auf 1 zurück.
    // Dadurch können wir unser Dokument in Form einer Gliederungsliste organisieren.
    // Dies ist das erste AUTONUMLGL-Feld auf Überschriftenebene 1, das "1" anzeigt. im Dokument.
    InsertNumberedClause(builder, "\tHeading 1", fillerText, StyleIdentifier.Heading1);

    // Dies ist das zweite AUTONUMLGL-Feld auf Überschriftenebene 1, daher wird "2." angezeigt.
    InsertNumberedClause(builder, "\tHeading 2", fillerText, StyleIdentifier.Heading1);

    // Dies ist das erste AUTONUMLGL-Feld auf Überschriftenebene 2,
    // und der AUTONUMLGL-Zähler für die Überschriftenebene darunter ist "2", also wird "2.1." angezeigt.
    InsertNumberedClause(builder, "\tHeading 3", fillerText, StyleIdentifier.Heading2);

     // Dies ist das erste AUTONUMLGL-Feld auf Überschriftenebene 3.
    // Auf dieselbe Weise wie im obigen Feld arbeitend, wird "2.1.1." angezeigt.
    InsertNumberedClause(builder, "\tHeading 4", fillerText, StyleIdentifier.Heading3);

    // Dieses Feld befindet sich auf einer Überschriftenebene von 2 und sein entsprechender AUTONUMLGL-Zähler ist 2, sodass das Feld "2.2." anzeigt.
    InsertNumberedClause(builder, "\tHeading 5", fillerText, StyleIdentifier.Heading2);

    // Erhöhen des AUTONUMLGL-Zählers für eine Überschriftenebene unterhalb dieser
    // hat die Zählung für dieses Level zurückgesetzt, sodass dieses Feld "2.2.1." anzeigt.
    InsertNumberedClause(builder, "\tHeading 6", fillerText, StyleIdentifier.Heading3);

    foreach (FieldAutoNumLgl field in doc.Range.Fields.Where(f => f.Type == FieldType.FieldAutoNumLegal))
    {
        // Das Trennzeichen, das im Feld result unmittelbar nach der Zahl erscheint,
        // ist standardmäßig ein Punkt. Wenn wir diese Eigenschaft null lassen,
        // Unser letztes AUTONUMLGL-Feld zeigt "2.2.1" an. im Dokument.
        Assert.IsNull(field.SeparatorCharacter);

        // Festlegen eines benutzerdefinierten Trennzeichens und Entfernen des nachgestellten Punkts
        // ändert das Aussehen dieses Felds von "2.2.1." zu "2:2:1".
        // Wir wenden dies auf alle Felder an, die wir erstellt haben.
        field.SeparatorCharacter = ":";
        field.RemoveTrailingPeriod = true;
        Assert.AreEqual(" AUTONUMLGL  \\s : \\e", field.GetFieldCode());
    }

    doc.Save(ArtifactsDir + "Field.AUTONUMLGL.docx");

/// <summary>
/// Verwendet einen Document Builder, um eine Klausel einzufügen, die durch ein AUTONUMLGL-Feld nummeriert ist.
/// </summary>
private static void InsertNumberedClause(DocumentBuilder builder, string heading, string contents, StyleIdentifier headingStyle)
{
    builder.InsertField(FieldType.FieldAutoNumLegal, true);
    builder.CurrentParagraph.ParagraphFormat.StyleIdentifier = headingStyle;
    builder.Writeln(heading);

    // Dieser Text gehört zum Auto-Num-Rechtsfeld darüber.
    // Es wird reduziert, wenn wir auf den Pfeil neben dem entsprechenden AUTONUMLGL-Feld in Microsoft Word klicken.
    builder.CurrentParagraph.ParagraphFormat.StyleIdentifier = StyleIdentifier.BodyText;
    builder.Writeln(contents);
}
```

### Siehe auch

* class [FieldAutoNumLgl](../)
* namensraum [Aspose.Words.Fields](../../fieldautonumlgl/)
* Montage [Aspose.Words](../../../)


