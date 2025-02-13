---
title: FieldTemplate.IncludeFullPath
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldTemplate propriété. Obtient ou définit sil faut inclure le nom complet du chemin daccès au fichier.
type: docs
weight: 20
url: /fr/net/aspose.words.fields/fieldtemplate/includefullpath/
---
## FieldTemplate.IncludeFullPath property

Obtient ou définit s'il faut inclure le nom complet du chemin d'accès au fichier.

```csharp
public bool IncludeFullPath { get; set; }
```

### Exemples

Montre comment utiliser un champ TEMPLATE pour afficher l'emplacement du système de fichiers local du modèle d'un document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Nous pouvons définir un nom de modèle en utilisant les champs. Cette propriété est utilisée lorsque le "doc.AttachedTemplate" est vide.
// Si cette propriété est vide, le nom de fichier de modèle par défaut "Normal.dotm" est utilisé.
doc.FieldOptions.TemplateName = string.Empty;

FieldTemplate field = (FieldTemplate)builder.InsertField(FieldType.FieldTemplate, false);
Assert.AreEqual(" TEMPLATE ", field.GetFieldCode());

builder.Writeln();
field = (FieldTemplate)builder.InsertField(FieldType.FieldTemplate, false);
field.IncludeFullPath = true;

Assert.AreEqual(" TEMPLATE  \\p", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.TEMPLATE.docx");
```

### Voir également

* class [FieldTemplate](../)
* espace de noms [Aspose.Words.Fields](../../fieldtemplate/)
* Assemblée [Aspose.Words](../../../)


