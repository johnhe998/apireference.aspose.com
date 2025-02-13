---
title: Enum ContentDisposition
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.ContentDisposition opsomming. Listet verschiedene Möglichkeiten auf das Dokument im ClientBrowser darzustellen.
type: docs
weight: 330
url: /de/net/aspose.words/contentdisposition/
---
## ContentDisposition enumeration

Listet verschiedene Möglichkeiten auf, das Dokument im Client-Browser darzustellen.

```csharp
public enum ContentDisposition
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Attachment | `0` | Senden Sie das Dokument an den Browser und präsentieren Sie eine Option zum Speichern des Dokuments auf der Festplatte oder zum Öffnen in der Anwendung , die der Erweiterung des Dokuments zugeordnet ist. |
| Inline | `1` | Sendet das Dokument an den Browser und bietet eine Option zum Speichern des Dokuments auf der Festplatte oder zum Öffnen im Browser. |

### Bemerkungen

Beachten Sie, dass das tatsächliche Verhalten im Client-Browser von der Sicherheitskonfiguration des Browsers beeinflusst werden kann.

### Beispiele

Zeigt, wie Sie einen Seriendruck durchführen und das Dokument dann im Client-Browser speichern.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" MERGEFIELD FullName ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD Company ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD Address ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD City ");

doc.MailMerge.Execute(new string[] { "FullName", "Company", "Address", "City" },
    new object[] { "James Bond", "MI5 Headquarters", "Milbank", "London" });

// Senden Sie das Dokument an den Client-Browser.
Assert.That(() => doc.Save(response, "Artifacts/MailMerge.ExecuteArray.docx", ContentDisposition.Inline, null),
    Throws.TypeOf<ArgumentNullException>()); //Wird ausgelöst, weil HttpResponse im Test null ist.

// Wir müssen diese Antwort manuell schließen, um sicherzustellen, dass wir dem Dokument nach dem Speichern keine überflüssigen Inhalte hinzufügen.
Assert.That(() => response.End(), Throws.TypeOf<NullReferenceException>());
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


