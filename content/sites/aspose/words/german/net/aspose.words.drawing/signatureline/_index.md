---
title: Class SignatureLine
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.SignatureLine klas. Bietet Zugriff auf Signaturzeileneigenschaften.
type: docs
weight: 1150
url: /de/net/aspose.words.drawing/signatureline/
---
## SignatureLine class

Bietet Zugriff auf Signaturzeileneigenschaften.

```csharp
public class SignatureLine
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [AllowComments](../../aspose.words.drawing/signatureline/allowcomments/) { get; set; } | Ruft einen Wert ab oder legt einen Wert fest, der angibt, dass der Unterzeichner Kommentare im Dialogfeld „Signieren“ hinzufügen kann. Der Standardwert für diese Eigenschaft ist **FALSCH** . |
| [DefaultInstructions](../../aspose.words.drawing/signatureline/defaultinstructions/) { get; set; } | Ruft einen Wert ab oder legt einen Wert fest, der angibt, dass Standardanweisungen im Dialogfeld „Signieren“ angezeigt werden. Der Standardwert für diese Eigenschaft ist **Stimmt** . |
| [Email](../../aspose.words.drawing/signatureline/email/) { get; set; } | Ruft die E-Mail-Adresse des vorgeschlagenen Unterzeichners ab oder legt sie fest. Der Standardwert für diese Eigenschaft ist **leerer String** (Empty ). |
| [Id](../../aspose.words.drawing/signatureline/id/) { get; set; } | Ruft die Kennung für diese Signaturzeile ab oder legt sie fest. |
| [Instructions](../../aspose.words.drawing/signatureline/instructions/) { get; set; } | Ruft Anweisungen für den Unterzeichner ab oder legt sie fest, die beim Unterschreiben der Unterschriftszeile angezeigt werden. Diese Eigenschaft wird ignoriert, wenn[`DefaultInstructions`](./defaultinstructions/) ist gesetzt. Der Standardwert für diese Eigenschaft ist **leerer String** (Empty ). |
| [IsSigned](../../aspose.words.drawing/signatureline/issigned/) { get; } | Gibt an, dass die Signaturzeile mit einer digitalen Signatur signiert ist. |
| [IsValid](../../aspose.words.drawing/signatureline/isvalid/) { get; } | Gibt an, dass die Signaturzeile mit einer digitalen Signatur signiert ist und diese digitale Signatur gültig ist. |
| [ProviderId](../../aspose.words.drawing/signatureline/providerid/) { get; set; } | Ruft die Kennung des Signaturanbieters für diese Signaturzeile ab oder legt sie fest. Der Standardwert ist "{00000000-0000-0000-0000-000000000000}". |
| [ShowDate](../../aspose.words.drawing/signatureline/showdate/) { get; set; } | Ruft einen Wert ab oder legt einen Wert fest, der angibt, dass das Vorzeichendatum in der Signaturzeile angezeigt wird. Der Standardwert für diese Eigenschaft ist **Stimmt** . |
| [Signer](../../aspose.words.drawing/signatureline/signer/) { get; set; } | Ruft den vorgeschlagenen Unterzeichner der Signaturzeile ab oder legt ihn fest. Der Standardwert für diese Eigenschaft ist **leerer String** (Empty ). |
| [SignerTitle](../../aspose.words.drawing/signatureline/signertitle/) { get; set; } | Ruft den Titel des vorgeschlagenen Unterzeichners ab oder legt ihn fest (z. B. Manager). Der Standardwert für diese Eigenschaft ist **leerer String** (Empty ). |

### Beispiele

Zeigt, wie eine Zeile für eine Signatur erstellt und in ein Dokument eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

SignatureLineOptions options = new SignatureLineOptions
{
    AllowComments = true,
    DefaultInstructions = true,
    Email = "john.doe@management.com",
    Instructions = "Please sign here",
    ShowDate = true,
    Signer = "John Doe",
    SignerTitle = "Senior Manager"
};

// Fügen Sie eine Form ein, die eine Signaturlinie enthält, deren Aussehen wir festlegen werden
// Anpassen mit dem oben erstellten "SignatureLineOptions"-Objekt.
// Wenn wir eine Form einfügen, deren Koordinaten von der rechten unteren Ecke der Seite stammen,
// Wir müssen negative x- und y-Koordinaten angeben, um die Form sichtbar zu machen.
Shape shape = builder.InsertSignatureLine(options, RelativeHorizontalPosition.RightMargin, -170.0, 
        RelativeVerticalPosition.BottomMargin, -60.0, WrapType.None);

Assert.True(shape.IsSignatureLine);

// Überprüfen Sie die Eigenschaften unserer Signaturlinie über ihr Shape-Objekt.
SignatureLine signatureLine = shape.SignatureLine;

Assert.AreEqual("john.doe@management.com", signatureLine.Email);
Assert.AreEqual("John Doe", signatureLine.Signer);
Assert.AreEqual("Senior Manager", signatureLine.SignerTitle);
Assert.AreEqual("Please sign here", signatureLine.Instructions);
Assert.True(signatureLine.ShowDate);
Assert.True(signatureLine.AllowComments);
Assert.True(signatureLine.DefaultInstructions);

doc.Save(ArtifactsDir + "Shape.SignatureLine.docx");
```

### Siehe auch

* namensraum [Aspose.Words.Drawing](../../aspose.words.drawing/)
* Montage [Aspose.Words](../../)


