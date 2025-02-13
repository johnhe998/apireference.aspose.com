---
title: SaveOptions.UpdateLastPrintedProperty
second_title: Référence de l'API Aspose.Words pour .NET
description: SaveOptions propriété. Obtient ou définit une valeur déterminant si leLastPrinted la propriété est mise à jour avant lenregistrement.
type: docs
weight: 180
url: /fr/net/aspose.words.saving/saveoptions/updatelastprintedproperty/
---
## SaveOptions.UpdateLastPrintedProperty property

Obtient ou définit une valeur déterminant si le[`LastPrinted`](../../../aspose.words.properties/builtindocumentproperties/lastprinted/) la propriété est mise à jour avant l'enregistrement.

```csharp
public bool UpdateLastPrintedProperty { get; set; }
```

### Exemples

Montre comment mettre à jour la propriété "CreatedTime" d'un document lors de l'enregistrement.

```csharp
Document doc = new Document();
doc.BuiltInDocumentProperties.CreatedTime = new DateTime(2019, 12, 20);

// Cet indicateur détermine si l'heure créée, qui est une propriété intégrée, est mise à jour.
// Si c'est le cas, alors la date de la dernière opération d'enregistrement du document
// avec cet objet SaveOptions passé en paramètre est utilisé comme heure de création.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.UpdateCreatedTimeProperty = isUpdateCreatedTimeProperty;

doc.Save(ArtifactsDir + "DocSaveOptions.UpdateCreatedTimeProperty.docx", saveOptions);

// Ouvre le document enregistré, puis vérifie la valeur de la propriété.
doc = new Document(ArtifactsDir + "DocSaveOptions.UpdateCreatedTimeProperty.docx");

Assert.AreNotEqual(isUpdateCreatedTimeProperty, new DateTime(2019, 12, 20) == doc.BuiltInDocumentProperties.CreatedTime);
```

Montre comment mettre à jour la propriété "Dernière impression" d'un document lors de l'enregistrement.

```csharp
Document doc = new Document();
doc.BuiltInDocumentProperties.LastPrinted = new DateTime(2019, 12, 20);

// Cet indicateur détermine si la dernière date imprimée, qui est une propriété intégrée, est mise à jour.
// Si c'est le cas, alors la date de la dernière opération d'enregistrement du document
// avec cet objet SaveOptions passé en paramètre est utilisé comme date d'impression.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.UpdateLastPrintedProperty = isUpdateLastPrintedProperty;

// Dans Microsoft Word 2003, cette propriété peut être trouvée via Fichier -> Propriétés -> Statistiques -> Imprimé.
// Il peut également être affiché dans le corps du document en utilisant un champ PRINTDATE.
doc.Save(ArtifactsDir + "DocSaveOptions.UpdateLastPrintedProperty.doc", saveOptions);

// Ouvre le document enregistré, puis vérifie la valeur de la propriété.
doc = new Document(ArtifactsDir + "DocSaveOptions.UpdateLastPrintedProperty.doc");

Assert.AreNotEqual(isUpdateLastPrintedProperty, new DateTime(2019, 12, 20) == doc.BuiltInDocumentProperties.LastPrinted);
```

### Voir également

* class [SaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../saveoptions/)
* Assemblée [Aspose.Words](../../../)


