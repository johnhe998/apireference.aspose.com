---
title: SmartTag.Properties
second_title: Aspose.Words für .NET-API-Referenz
description: SmartTag eigendom. Eine Sammlung der SmarttagEigenschaften.
type: docs
weight: 40
url: /de/net/aspose.words.markup/smarttag/properties/
---
## SmartTag.Properties property

Eine Sammlung der Smarttag-Eigenschaften.

```csharp
public CustomXmlPropertyCollection Properties { get; }
```

### Bemerkungen

Kann nicht Null sein.

### Beispiele

Zeigt, wie Smarttags erstellt werden.

```csharp
public void Create()
{
    Document doc = new Document();

    // Ein Smart Tag erscheint in einem Dokument mit Microsoft Word erkennt einen Teil seines Textes als irgendeine Form von Daten,
    // wie Name, Datum oder Adresse, und wandelt sie in einen Hyperlink um, der eine violett gepunktete Unterstreichung anzeigt.
    SmartTag smartTag = new SmartTag(doc);

    // Smarttags sind zusammengesetzte Knoten, die ihren erkannten Text vollständig enthalten.
    // Inhalte manuell zu diesem Smart Tag hinzufügen.
    smartTag.AppendChild(new Run(doc, "May 29, 2019"));

    // Microsoft Word kann den obigen Inhalt als Datum erkennen.
    // Smarttags verwenden die "Element"-Eigenschaft, um die Art der Daten widerzuspiegeln, die sie enthalten.
    smartTag.Element = "date";

    // Einige Smarttag-Typen verarbeiten ihren Inhalt weiter in benutzerdefinierte XML-Eigenschaften.
    smartTag.Properties.Add(new CustomXmlProperty("Day", string.Empty, "29"));
    smartTag.Properties.Add(new CustomXmlProperty("Month", string.Empty, "5"));
    smartTag.Properties.Add(new CustomXmlProperty("Year", string.Empty, "2019"));

    // Den URI des Smarttags auf den Standardwert setzen.
    smartTag.Uri = "urn:schemas-microsoft-com:office:smarttags";

    doc.FirstSection.Body.FirstParagraph.AppendChild(smartTag);
    doc.FirstSection.Body.FirstParagraph.AppendChild(new Run(doc, " is a date. "));

    // Erstellen Sie ein weiteres Smart Tag für einen Börsenticker.
    smartTag = new SmartTag(doc);
    smartTag.Element = "stockticker";
    smartTag.Uri = "urn:schemas-microsoft-com:office:smarttags";

    smartTag.AppendChild(new Run(doc, "MSFT"));

    doc.FirstSection.Body.FirstParagraph.AppendChild(smartTag);
    doc.FirstSection.Body.FirstParagraph.AppendChild(new Run(doc, " is a stock ticker."));

    // Alle Smart-Tags in unserem Dokument mit einem Dokumentbesucher drucken.
    doc.Accept(new SmartTagPrinter());

    // Ältere Versionen von Microsoft Word unterstützen Smart Tags.
    doc.Save(ArtifactsDir + "SmartTag.Create.doc");

    // Verwenden Sie die Methode "RemoveSmartTags", um alle Smarttags aus einem Dokument zu entfernen.
    Assert.AreEqual(2, doc.GetChildNodes(NodeType.SmartTag, true).Count);

    doc.RemoveSmartTags();

    Assert.AreEqual(0, doc.GetChildNodes(NodeType.SmartTag, true).Count);
}

/// <summary>
/// Druckt besuchte Smarttags und deren Inhalt.
/// </summary>
private class SmartTagPrinter : DocumentVisitor
{
    /// <summary>
    /// Wird aufgerufen, wenn im Dokument ein SmartTag-Knoten gefunden wird.
    /// </summary>
    public override VisitorAction VisitSmartTagStart(SmartTag smartTag)
    {
        Console.WriteLine($"Smart tag type: {smartTag.Element}");
        return VisitorAction.Continue;
    }

    /// <summary>
    /// Wird aufgerufen, wenn der Besuch eines SmartTag-Knotens beendet ist.
    /// </summary>
    public override VisitorAction VisitSmartTagEnd(SmartTag smartTag)
    {
        Console.WriteLine($"\tContents: \"{smartTag.ToString(SaveFormat.Text)}\"");

        if (smartTag.Properties.Count == 0)
        {
            Console.WriteLine("\tContains no properties");
        }
        else
        {
            Console.Write("\tProperties: ");
            string[] properties = new string[smartTag.Properties.Count];
            int index = 0;

            foreach (CustomXmlProperty cxp in smartTag.Properties)
                properties[index++] = $"\"{cxp.Name}\" = \"{cxp.Value}\"";

            Console.WriteLine(string.Join(", ", properties));
        }

        return VisitorAction.Continue;
    }
}
```

### Siehe auch

* class [CustomXmlPropertyCollection](../../customxmlpropertycollection/)
* class [SmartTag](../)
* namensraum [Aspose.Words.Markup](../../smarttag/)
* Montage [Aspose.Words](../../../)


