---
title: Interface IFieldUpdatingCallback
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Fields.IFieldUpdatingCallback interface. Implémentez cette interface si vous souhaitez que vos propres méthodes personnalisées soient appelées lors dune mise à jour de champ.
type: docs
weight: 2550
url: /fr/net/aspose.words.fields/ifieldupdatingcallback/
---
## IFieldUpdatingCallback interface

Implémentez cette interface si vous souhaitez que vos propres méthodes personnalisées soient appelées lors d'une mise à jour de champ.

```csharp
public interface IFieldUpdatingCallback
```

## Méthodes

| Nom | La description |
| --- | --- |
| [FieldUpdated](../../aspose.words.fields/ifieldupdatingcallback/fieldupdated/)(Field) | Une méthode définie par l'utilisateur qui est appelée juste après la mise à jour d'un champ. |
| [FieldUpdating](../../aspose.words.fields/ifieldupdatingcallback/fieldupdating/)(Field) | Une méthode définie par l'utilisateur qui est appelée juste avant la mise à jour d'un champ. |

### Exemples

Montre comment utiliser les méthodes de rappel lors d'une mise à jour de champ.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(" DATE \\@ \"dddd, d MMMM yyyy\" ");
    builder.InsertField(" TIME ");
    builder.InsertField(" REVNUM ");
    builder.InsertField(" AUTHOR  \"John Doe\" ");
    builder.InsertField(" SUBJECT \"My Subject\" ");
    builder.InsertField(" QUOTE \"Hello world!\" ");

    FieldUpdatingCallback callback = new FieldUpdatingCallback();
    doc.FieldOptions.FieldUpdatingCallback = callback;

    doc.UpdateFields();

    Assert.True(callback.FieldUpdatedCalls.Contains("Updating John Doe"));
}

/// <summary>
/// Implémentez cette interface si vous souhaitez que vos propres méthodes personnalisées soient appelées lors d'une mise à jour de champ.
/// </summary>
public class FieldUpdatingCallback : IFieldUpdatingCallback
{
    public FieldUpdatingCallback()
    {
        FieldUpdatedCalls = new List<string>();
    }

    /// <summary>
    /// Une méthode définie par l'utilisateur qui est appelée juste avant la mise à jour d'un champ.
    /// </summary>
    void IFieldUpdatingCallback.FieldUpdating(Field field)
    {
        if (field.Type == FieldType.FieldAuthor)
        {
            FieldAuthor fieldAuthor = (FieldAuthor) field;
            fieldAuthor.AuthorName = "Updating John Doe";
        }
    }

    /// <summary>
    /// Une méthode définie par l'utilisateur qui est appelée juste après la mise à jour d'un champ.
    /// </summary>
    void IFieldUpdatingCallback.FieldUpdated(Field field)
    {
        FieldUpdatedCalls.Add(field.Result);
    }

    public IList<string> FieldUpdatedCalls { get; }
}
```

### Voir également

* espace de noms [Aspose.Words.Fields](../../aspose.words.fields/)
* Assemblée [Aspose.Words](../../)


