---
title: SignatureLine.AllowComments
second_title: Aspose.Words per .NET API Reference
description: SignatureLine proprietà. Ottiene o imposta un valore che indica che il firmatario può aggiungere commenti nella finestra di dialogo Segno. Il valore predefinito per questa proprietà è falso .
type: docs
weight: 10
url: /it/net/aspose.words.drawing/signatureline/allowcomments/
---
## SignatureLine.AllowComments property

Ottiene o imposta un valore che indica che il firmatario può aggiungere commenti nella finestra di dialogo Segno. Il valore predefinito per questa proprietà è **falso** .

```csharp
public bool AllowComments { get; set; }
```

### Esempi

Mostra come creare una riga per una firma e inserirla in un documento.

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

// Inserisci una forma che conterrà una linea di firma, il cui aspetto sarà
// personalizza usando l'oggetto "SignatureLineOptions" che abbiamo creato sopra.
// Se inseriamo una forma le cui coordinate hanno origine nell'angolo in basso a destra della pagina,
// dovremo fornire coordinate xey negative per visualizzare la forma.
Shape shape = builder.InsertSignatureLine(options, RelativeHorizontalPosition.RightMargin, -170.0, 
        RelativeVerticalPosition.BottomMargin, -60.0, WrapType.None);

Assert.True(shape.IsSignatureLine);

// Verifica le proprietà della nostra linea di firma tramite il suo oggetto Shape.
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

### Guarda anche

* class [SignatureLine](../)
* spazio dei nomi [Aspose.Words.Drawing](../../signatureline/)
* assemblea [Aspose.Words](../../../)


