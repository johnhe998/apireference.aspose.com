---
title: FieldBuilder.FieldBuilder
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldBuilder constructeur. Initialise une instance duFieldBuilder classe.
type: docs
weight: 10
url: /fr/net/aspose.words.fields/fieldbuilder/fieldbuilder/
---
## FieldBuilder constructor

Initialise une instance du[`FieldBuilder`](../) classe.

```csharp
public FieldBuilder(FieldType fieldType)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| fieldType | FieldType | Type de champ à créer. |

### Exemples

Montre comment créer et insérer un champ à l'aide d'un générateur de champs.

```csharp
Document doc = new Document();

// Un moyen pratique d'ajouter du contenu textuel à un document consiste à utiliser un générateur de document.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write(" Hello world! This text is one Run, which is an inline node.");

// Les champs ont leur constructeur, que nous pouvons utiliser pour construire un code de champ morceau par morceau.
// Dans ce cas, nous allons construire un champ BARCODE représentant un code postal américain,
// puis insérez-le devant un Run.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldBarcode);
fieldBuilder.AddArgument("90210");
fieldBuilder.AddSwitch("\\f", "A");
fieldBuilder.AddSwitch("\\u");

fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph.Runs[0]);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.CreateWithFieldBuilder.docx");
```

### Voir également

* enum [FieldType](../../fieldtype/)
* class [FieldBuilder](../)
* espace de noms [Aspose.Words.Fields](../../fieldbuilder/)
* Assemblée [Aspose.Words](../../../)


