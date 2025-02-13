---
title: Shape.SignatureLine
second_title: Référence de l'API Aspose.Words pour .NET
description: Shape propriété. ObtientSignatureLine objet si la forme est une ligne de signature. Retour nul sinon.
type: docs
weight: 160
url: /fr/net/aspose.words.drawing/shape/signatureline/
---
## Shape.SignatureLine property

Obtient`SignatureLine` objet si la forme est une ligne de signature. Retour **nul** sinon.

```csharp
public SignatureLine SignatureLine { get; }
```

### Remarques

Vous pouvez insérer de nouvelles SignatureLines dans le document en utilisant[`InsertSignatureLine`](../../../aspose.words/documentbuilder/insertsignatureline/) et

### Exemples

Montre comment créer une ligne pour une signature et l'insérer dans un document.

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

// Insère une forme qui contiendra une ligne de signature, dont nous allons voir l'apparence
// personnaliser en utilisant l'objet "SignatureLineOptions" que nous avons créé ci-dessus.
// Si nous insérons une forme dont les coordonnées proviennent du coin inférieur droit de la page,
// nous devrons fournir des coordonnées x et y négatives pour afficher la forme.
Shape shape = builder.InsertSignatureLine(options, RelativeHorizontalPosition.RightMargin, -170.0, 
        RelativeVerticalPosition.BottomMargin, -60.0, WrapType.None);

Assert.True(shape.IsSignatureLine);

// Vérifier les propriétés de notre ligne de signature via son objet Shape.
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

### Voir également

* class [SignatureLine](../../signatureline/)
* class [Shape](../)
* espace de noms [Aspose.Words.Drawing](../../shape/)
* Assemblée [Aspose.Words](../../../)


