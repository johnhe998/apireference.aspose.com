---
title: FieldFillIn.DefaultResponse
second_title: Aspose.Words für .NET-API-Referenz
description: FieldFillIn eigendom. Ruft die Standardbenutzerantwort ab oder legt sie fest Anfangswert im Eingabeaufforderungsfenster enthalten.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldfillin/defaultresponse/
---
## FieldFillIn.DefaultResponse property

Ruft die Standardbenutzerantwort ab oder legt sie fest (Anfangswert im Eingabeaufforderungsfenster enthalten).

```csharp
public string DefaultResponse { get; set; }
```

### Beispiele

Zeigt, wie das FILLIN-Feld verwendet wird, um den Benutzer zu einer Antwort aufzufordern.

```csharp
public void FieldFillIn()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Ein FILLIN-Feld einfügen. Wenn wir dieses Feld in Microsoft Word manuell aktualisieren,
    // Es fordert uns auf, eine Antwort einzugeben. Das Feld zeigt dann die Antwort als Text an.
    FieldFillIn field = (FieldFillIn)builder.InsertField(FieldType.FieldFillIn, true);
    field.PromptText = "Please enter a response:";
    field.DefaultResponse = "A default response.";

    // Wir können diese Felder auch verwenden, um den Benutzer um eine eindeutige Antwort für jede Seite zu bitten
    // erstellt während eines Seriendrucks mit Microsoft Word.
    field.PromptOnceOnMailMerge = true;

    Assert.AreEqual(" FILLIN  \"Please enter a response:\" \\d \"A default response.\" \\o", field.GetFieldCode());

    FieldMergeField mergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
    mergeField.FieldName = "MergeField";

    // Wenn wir einen Seriendruck programmgesteuert durchführen, können wir einen benutzerdefinierten Prompt-Respondenten verwenden
    // zum automatischen Bearbeiten von Antworten für FILLIN-Felder, auf die der Seriendruck stößt.
    doc.FieldOptions.UserPromptRespondent = new PromptRespondent();
    doc.MailMerge.Execute(new [] { "MergeField" }, new object[] { "" });

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.FILLIN.docx");

/// <summary>
/// Stellt der Standardantwort jedes FILLIN-Felds während eines Seriendrucks eine Zeile voran.
/// </summary>
private class PromptRespondent : IFieldUserPromptRespondent
{
    public string Respond(string promptText, string defaultResponse)
    {
        return "Response modified by PromptRespondent. " + defaultResponse;
    }
}
```

### Siehe auch

* class [FieldFillIn](../)
* namensraum [Aspose.Words.Fields](../../fieldfillin/)
* Montage [Aspose.Words](../../../)


