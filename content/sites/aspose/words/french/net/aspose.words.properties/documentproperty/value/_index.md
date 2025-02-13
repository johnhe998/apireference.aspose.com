---
title: DocumentProperty.Value
second_title: Référence de l'API Aspose.Words pour .NET
description: DocumentProperty propriété. Obtient ou définit la valeur de la propriété.
type: docs
weight: 50
url: /fr/net/aspose.words.properties/documentproperty/value/
---
## DocumentProperty.Value property

Obtient ou définit la valeur de la propriété.

```csharp
public object Value { get; set; }
```

### Remarques

Ne peut pas être nulle.

### Exemples

Montre comment utiliser les propriétés de document intégrées.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// L'objet "Document" contient certaines de ses métadonnées dans ses membres.
Console.WriteLine($"Document filename:\n\t \"{doc.OriginalFileName}\"");

// Le document stocke également les métadonnées dans ses propriétés intégrées.
// Chaque propriété intégrée est membre de l'objet "BuiltInDocumentProperties" du document.
Console.WriteLine("Built-in Properties:");
foreach (DocumentProperty docProperty in doc.BuiltInDocumentProperties)
{
    Console.WriteLine(docProperty.Name);
    Console.WriteLine($"\tType:\t{docProperty.Type}");

    // Certaines propriétés peuvent stocker plusieurs valeurs.
    if (docProperty.Value is ICollection<object>)
    {
        foreach (object value in docProperty.Value as ICollection<object>)
            Console.WriteLine($"\tValue:\t\"{value}\"");
    }
    else
    {
        Console.WriteLine($"\tValue:\t\"{docProperty.Value}\"");
    }
}
```

### Voir également

* class [DocumentProperty](../)
* espace de noms [Aspose.Words.Properties](../../documentproperty/)
* Assemblée [Aspose.Words](../../../)


