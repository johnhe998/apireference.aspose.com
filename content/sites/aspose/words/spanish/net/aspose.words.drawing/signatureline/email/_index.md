---
title: SignatureLine.Email
second_title: Referencia de API de Aspose.Words para .NET
description: SignatureLine propiedad. Obtiene o establece la dirección de correo electrónico del firmante sugerido. El valor predeterminado para esta propiedad es cuerda vacía Empty .
type: docs
weight: 30
url: /es/net/aspose.words.drawing/signatureline/email/
---
## SignatureLine.Email property

Obtiene o establece la dirección de correo electrónico del firmante sugerido. El valor predeterminado para esta propiedad es **cuerda vacía** (Empty ).

```csharp
public string Email { get; set; }
```

### Ejemplos

Muestra cómo crear una línea para una firma e insertarla en un documento.

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

// Inserta una forma que contendrá una línea de firma, cuya apariencia vamos a
// personalizar utilizando el objeto "SignatureLineOptions" que hemos creado anteriormente.
// Si insertamos una forma cuyas coordenadas se originan en la esquina inferior derecha de la página,
// necesitaremos proporcionar coordenadas x e y negativas para mostrar la forma.
Shape shape = builder.InsertSignatureLine(options, RelativeHorizontalPosition.RightMargin, -170.0, 
        RelativeVerticalPosition.BottomMargin, -60.0, WrapType.None);

Assert.True(shape.IsSignatureLine);

// Verifica las propiedades de nuestra línea de firma a través de su objeto Shape.
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

### Ver también

* class [SignatureLine](../)
* espacio de nombres [Aspose.Words.Drawing](../../signatureline/)
* asamblea [Aspose.Words](../../../)


