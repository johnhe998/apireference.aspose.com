---
title: FieldPrint.PrinterInstructions
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldPrint propriété. Obtient ou définit les caractères de code de contrôle spécifiques à limprimante ou les instructions PostScript.
type: docs
weight: 30
url: /fr/net/aspose.words.fields/fieldprint/printerinstructions/
---
## FieldPrint.PrinterInstructions property

Obtient ou définit les caractères de code de contrôle spécifiques à l'imprimante ou les instructions PostScript.

```csharp
public string PrinterInstructions { get; set; }
```

### Exemples

Indique d'insérer un champ PRINT.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("My paragraph");

// Le champ PRINT peut envoyer des instructions à l'imprimante.
FieldPrint field = (FieldPrint)builder.InsertField(FieldType.FieldPrint, true);

// Définit la zone sur laquelle l'imprimante exécutera les instructions.
// Dans ce cas, ce sera le paragraphe qui contient notre champ PRINT.
field.PostScriptGroup = "para";

// Lorsque nous utilisons une imprimante prenant en charge PostScript pour imprimer notre document,
// cette commande rendra toute la zone que nous avons spécifiée dans "field.PostScriptGroup" blanche.
field.PrinterInstructions = "erasepage";

Assert.AreEqual(" PRINT  erasepage \\p para", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.PRINT.docx");
```

### Voir également

* class [FieldPrint](../)
* espace de noms [Aspose.Words.Fields](../../fieldprint/)
* Assemblée [Aspose.Words](../../../)


