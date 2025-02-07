---
title: HtmlSaveOptions.ExportDropDownFormFieldAsText
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlSaveOptions eigendom. Steuert wie DropdownFormularfelder in HTML oder MHTML gespeichert werden. Standardwert istFALSCH .
type: docs
weight: 140
url: /de/net/aspose.words.saving/htmlsaveoptions/exportdropdownformfieldastext/
---
## HtmlSaveOptions.ExportDropDownFormFieldAsText property

Steuert, wie Dropdown-Formularfelder in HTML oder MHTML gespeichert werden. Standardwert ist`FALSCH` .

```csharp
public bool ExportDropDownFormFieldAsText { get; set; }
```

### Bemerkungen

Wenn eingestellt auf`Stimmt` , exportiert Dropdown-Formularfelder als normalen Text. When`FALSCH`, exportiert Dropdown-Formularfelder als SELECT-Element in HTML.

Beim Exportieren in EPUB werden Text-Dropdown-Formularfelder aufgrund von Anforderungen dieses Formats immer als Text gespeichert.

### Beispiele

Zeigt, wie Dropdown-Kombinationsfeld-Formularfelder beim Speichern in HTML mit Absatztext verschmolzen werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Verwenden Sie einen Dokumentenersteller, um ein Kombinationsfeld mit dem ausgewählten Wert "Zwei" einzufügen.
builder.InsertComboBox("MyComboBox", new[] { "One", "Two", "Three" }, 1);

// Das "ExportDropDownFormFieldAsText"-Flag dieses SaveOptions-Objekts ermöglicht uns dies
// Steuern, wie das Speichern des Dokuments in HTML Dropdown-Kombinationsfelder behandelt.
// Wenn Sie es auf "true" setzen, wird jedes Kombinationsfeld in einfachen Text umgewandelt
// das zeigt den aktuell ausgewählten Wert des Kombinationsfelds an und friert ihn effektiv ein.
// Wenn Sie es auf "false" setzen, wird die Funktionalität des Kombinationsfelds mit <select> und <Option> Stichworte.
HtmlSaveOptions options = new HtmlSaveOptions();
options.ExportDropDownFormFieldAsText = exportDropDownFormFieldAsText;    

doc.Save(ArtifactsDir + "HtmlSaveOptions.DropDownFormField.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.DropDownFormField.html");

if (exportDropDownFormFieldAsText)
    Assert.True(outDocContents.Contains(
        "<span>Two</span>"));
else
    Assert.True(outDocContents.Contains(
        "<select name=\"MyComboBox\">" +
            "<option>One</option>" +
            "<option selected=\"selected\">Two</option>" +
            "<option>Three</option>" +
        "</select>"));
```

### Siehe auch

* class [HtmlSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlsaveoptions/)
* Montage [Aspose.Words](../../../)


