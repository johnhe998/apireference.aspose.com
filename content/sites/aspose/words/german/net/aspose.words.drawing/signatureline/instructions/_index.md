---
title: SignatureLine.Instructions
second_title: Aspose.Words für .NET-API-Referenz
description: SignatureLine eigendom. Ruft Anweisungen für den Unterzeichner ab oder legt sie fest die beim Unterschreiben der Unterschriftszeile angezeigt werden. Diese Eigenschaft wird ignoriert wennDefaultInstructions ist gesetzt. Der Standardwert für diese Eigenschaft ist leerer String Empty .
type: docs
weight: 50
url: /de/net/aspose.words.drawing/signatureline/instructions/
---
## SignatureLine.Instructions property

Ruft Anweisungen für den Unterzeichner ab oder legt sie fest, die beim Unterschreiben der Unterschriftszeile angezeigt werden. Diese Eigenschaft wird ignoriert, wenn[`DefaultInstructions`](../defaultinstructions/) ist gesetzt. Der Standardwert für diese Eigenschaft ist **leerer String** (Empty ).

```csharp
public string Instructions { get; set; }
```

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

* class [SignatureLine](../)
* namensraum [Aspose.Words.Drawing](../../signatureline/)
* Montage [Aspose.Words](../../../)


