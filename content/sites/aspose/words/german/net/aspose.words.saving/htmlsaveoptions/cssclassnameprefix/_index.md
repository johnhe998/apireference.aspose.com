---
title: HtmlSaveOptions.CssClassNamePrefix
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlSaveOptions eigendom. Gibt ein Präfix an das allen CSSKlassennamen hinzugefügt wird. Der Standardwert ist eine leere Zeichenfolge und generierte CSSKlassennamen haben kein gemeinsames Präfix.
type: docs
weight: 30
url: /de/net/aspose.words.saving/htmlsaveoptions/cssclassnameprefix/
---
## HtmlSaveOptions.CssClassNamePrefix property

Gibt ein Präfix an, das allen CSS-Klassennamen hinzugefügt wird. Der Standardwert ist eine leere Zeichenfolge, und generierte CSS-Klassennamen haben kein gemeinsames Präfix.

```csharp
public string CssClassNamePrefix { get; set; }
```

### Ausnahmen

| Ausnahme | Bedingung |
| --- | --- |
| ArgumentException | Der Wert ist nicht leer und kein gültiger CSS-Bezeichner. |

### Bemerkungen

Wenn dieser Wert nicht leer ist, beginnen alle von Aspose.Words generierten CSS-Klassen mit dem angegebenen Präfix. Dies kann beispielsweise nützlich sein, wenn Sie benutzerdefiniertes CSS zu generierten Dokumenten hinzufügen und Namenskonflikte von class verhindern möchten.

Wenn der Wert nicht ist`Null` oder leer, muss es sich um einen gültigen CSS-Bezeichner handeln.

### Beispiele

Zeigt, wie Sie ein Dokument in HTML speichern und allen CSS-Klassennamen ein Präfix hinzufügen.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    CssClassNamePrefix = "myprefix-"
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.CssClassNamePrefix.html", saveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.CssClassNamePrefix.html");

Assert.True(outDocContents.Contains("<p class=\"myprefix-Header\">"));
Assert.True(outDocContents.Contains("<p class=\"myprefix-Footer\">"));

outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.CssClassNamePrefix.css");

Assert.True(outDocContents.Contains(".myprefix-Footer { margin-bottom:0pt; line-height:normal; font-family:Arial; font-size:11pt }\r\n" +
                                    ".myprefix-Header { margin-bottom:0pt; line-height:normal; font-family:Arial; font-size:11pt }\r\n"));
```

### Siehe auch

* class [HtmlSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlsaveoptions/)
* Montage [Aspose.Words](../../../)


