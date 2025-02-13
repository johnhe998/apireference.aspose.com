---
title: CustomDocumentProperties.Add
second_title: Référence de l'API Aspose.Words pour .NET
description: CustomDocumentProperties méthode. Crée une nouvelle propriété de document personnalisée du PropertyType.String type de données.
type: docs
weight: 10
url: /fr/net/aspose.words.properties/customdocumentproperties/add/
---
## Add(string, string) {#add_4}

Crée une nouvelle propriété de document personnalisée du **PropertyType.String** type de données.

```csharp
public DocumentProperty Add(string name, string value)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| name | String | Le nom de la propriété. |
| value | String | La valeur de la propriété. |

### Return_Value

L'objet de propriété nouvellement créé.

### Exemples

Montre comment utiliser les propriétés personnalisées d'un document.

```csharp
Document doc = new Document();
CustomDocumentProperties properties = doc.CustomDocumentProperties;

Assert.AreEqual(0, properties.Count);

// Les propriétés de document personnalisées sont des paires clé-valeur que nous pouvons ajouter au document.
properties.Add("Authorized", true);
properties.Add("Authorized By", "John Doe");
properties.Add("Authorized Date", DateTime.Today);
properties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
properties.Add("Authorized Amount", 123.45);

// La collection trie les propriétés personnalisées par ordre alphabétique.
Assert.AreEqual(1, properties.IndexOf("Authorized Amount"));
Assert.AreEqual(5, properties.Count);

// Imprime chaque propriété personnalisée dans le document.
using (IEnumerator<DocumentProperty> enumerator = properties.GetEnumerator())
{
    while (enumerator.MoveNext())
        Console.WriteLine($"Name: \"{enumerator.Current.Name}\"\n\tType: \"{enumerator.Current.Type}\"\n\tValue: \"{enumerator.Current.Value}\"");
}

// Affiche la valeur d'une propriété personnalisée à l'aide d'un champ DOCPROPERTY.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldDocProperty field = (FieldDocProperty)builder.InsertField(" DOCPROPERTY \"Authorized By\"");
field.Update();

Assert.AreEqual("John Doe", field.Result);

// Nous pouvons trouver ces propriétés personnalisées dans Microsoft Word via "Fichier" -> "Propriétés" > "Propriétés avancées" > "Personnalisé".
doc.Save(ArtifactsDir + "DocumentProperties.DocumentPropertyCollection.docx");

// Vous trouverez ci-dessous trois façons de supprimer les propriétés personnalisées d'un document.
// 1 - Supprimer par index :
properties.RemoveAt(1);

Assert.False(properties.Contains("Authorized Amount"));
Assert.AreEqual(4, properties.Count);

// 2 - Supprimer par nom :
properties.Remove("Authorized Revision");

Assert.False(properties.Contains("Authorized Revision"));
Assert.AreEqual(3, properties.Count);

// 3 - Vide toute la collection d'un coup :
properties.Clear();

Assert.AreEqual(0, properties.Count);
```

### Voir également

* class [DocumentProperty](../../documentproperty/)
* class [CustomDocumentProperties](../)
* espace de noms [Aspose.Words.Properties](../../customdocumentproperties/)
* Assemblée [Aspose.Words](../../../)

---

## Add(string, int) {#add_2}

Crée une nouvelle propriété de document personnalisée du **PropertyType.Number** type de données.

```csharp
public DocumentProperty Add(string name, int value)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| name | String | Le nom de la propriété. |
| value | Int32 | La valeur de la propriété. |

### Return_Value

L'objet de propriété nouvellement créé.

### Exemples

Montre comment utiliser les propriétés personnalisées d'un document.

```csharp
Document doc = new Document();
CustomDocumentProperties properties = doc.CustomDocumentProperties;

Assert.AreEqual(0, properties.Count);

// Les propriétés de document personnalisées sont des paires clé-valeur que nous pouvons ajouter au document.
properties.Add("Authorized", true);
properties.Add("Authorized By", "John Doe");
properties.Add("Authorized Date", DateTime.Today);
properties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
properties.Add("Authorized Amount", 123.45);

// La collection trie les propriétés personnalisées par ordre alphabétique.
Assert.AreEqual(1, properties.IndexOf("Authorized Amount"));
Assert.AreEqual(5, properties.Count);

// Imprime chaque propriété personnalisée dans le document.
using (IEnumerator<DocumentProperty> enumerator = properties.GetEnumerator())
{
    while (enumerator.MoveNext())
        Console.WriteLine($"Name: \"{enumerator.Current.Name}\"\n\tType: \"{enumerator.Current.Type}\"\n\tValue: \"{enumerator.Current.Value}\"");
}

// Affiche la valeur d'une propriété personnalisée à l'aide d'un champ DOCPROPERTY.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldDocProperty field = (FieldDocProperty)builder.InsertField(" DOCPROPERTY \"Authorized By\"");
field.Update();

Assert.AreEqual("John Doe", field.Result);

// Nous pouvons trouver ces propriétés personnalisées dans Microsoft Word via "Fichier" -> "Propriétés" > "Propriétés avancées" > "Personnalisé".
doc.Save(ArtifactsDir + "DocumentProperties.DocumentPropertyCollection.docx");

// Vous trouverez ci-dessous trois façons de supprimer les propriétés personnalisées d'un document.
// 1 - Supprimer par index :
properties.RemoveAt(1);

Assert.False(properties.Contains("Authorized Amount"));
Assert.AreEqual(4, properties.Count);

// 2 - Supprimer par nom :
properties.Remove("Authorized Revision");

Assert.False(properties.Contains("Authorized Revision"));
Assert.AreEqual(3, properties.Count);

// 3 - Vide toute la collection d'un coup :
properties.Clear();

Assert.AreEqual(0, properties.Count);
```

### Voir également

* class [DocumentProperty](../../documentproperty/)
* class [CustomDocumentProperties](../)
* espace de noms [Aspose.Words.Properties](../../customdocumentproperties/)
* Assemblée [Aspose.Words](../../../)

---

## Add(string, DateTime) {#add_3}

Crée une nouvelle propriété de document personnalisée du **PropertyType.DateTime** type de données.

```csharp
public DocumentProperty Add(string name, DateTime value)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| name | String | Le nom de la propriété. |
| value | DateTime | La valeur de la propriété. |

### Return_Value

L'objet de propriété nouvellement créé.

### Exemples

Montre comment créer une propriété de document personnalisée qui contient une date et une heure.

```csharp
Document doc = new Document();

doc.CustomDocumentProperties.Add("AuthorizationDate", DateTime.Now);

Console.WriteLine($"Document authorized on {doc.CustomDocumentProperties["AuthorizationDate"].ToDateTime()}");
```

Montre comment utiliser les propriétés personnalisées d'un document.

```csharp
Document doc = new Document();
CustomDocumentProperties properties = doc.CustomDocumentProperties;

Assert.AreEqual(0, properties.Count);

// Les propriétés de document personnalisées sont des paires clé-valeur que nous pouvons ajouter au document.
properties.Add("Authorized", true);
properties.Add("Authorized By", "John Doe");
properties.Add("Authorized Date", DateTime.Today);
properties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
properties.Add("Authorized Amount", 123.45);

// La collection trie les propriétés personnalisées par ordre alphabétique.
Assert.AreEqual(1, properties.IndexOf("Authorized Amount"));
Assert.AreEqual(5, properties.Count);

// Imprime chaque propriété personnalisée dans le document.
using (IEnumerator<DocumentProperty> enumerator = properties.GetEnumerator())
{
    while (enumerator.MoveNext())
        Console.WriteLine($"Name: \"{enumerator.Current.Name}\"\n\tType: \"{enumerator.Current.Type}\"\n\tValue: \"{enumerator.Current.Value}\"");
}

// Affiche la valeur d'une propriété personnalisée à l'aide d'un champ DOCPROPERTY.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldDocProperty field = (FieldDocProperty)builder.InsertField(" DOCPROPERTY \"Authorized By\"");
field.Update();

Assert.AreEqual("John Doe", field.Result);

// Nous pouvons trouver ces propriétés personnalisées dans Microsoft Word via "Fichier" -> "Propriétés" > "Propriétés avancées" > "Personnalisé".
doc.Save(ArtifactsDir + "DocumentProperties.DocumentPropertyCollection.docx");

// Vous trouverez ci-dessous trois façons de supprimer les propriétés personnalisées d'un document.
// 1 - Supprimer par index :
properties.RemoveAt(1);

Assert.False(properties.Contains("Authorized Amount"));
Assert.AreEqual(4, properties.Count);

// 2 - Supprimer par nom :
properties.Remove("Authorized Revision");

Assert.False(properties.Contains("Authorized Revision"));
Assert.AreEqual(3, properties.Count);

// 3 - Vide toute la collection d'un coup :
properties.Clear();

Assert.AreEqual(0, properties.Count);
```

### Voir également

* class [DocumentProperty](../../documentproperty/)
* class [CustomDocumentProperties](../)
* espace de noms [Aspose.Words.Properties](../../customdocumentproperties/)
* Assemblée [Aspose.Words](../../../)

---

## Add(string, bool) {#add}

Crée une nouvelle propriété de document personnalisée du **PropertyType.Boolean** type de données.

```csharp
public DocumentProperty Add(string name, bool value)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| name | String | Le nom de la propriété. |
| value | Boolean | La valeur de la propriété. |

### Return_Value

L'objet de propriété nouvellement créé.

### Exemples

Montre comment utiliser les propriétés personnalisées d'un document.

```csharp
Document doc = new Document();
CustomDocumentProperties properties = doc.CustomDocumentProperties;

Assert.AreEqual(0, properties.Count);

// Les propriétés de document personnalisées sont des paires clé-valeur que nous pouvons ajouter au document.
properties.Add("Authorized", true);
properties.Add("Authorized By", "John Doe");
properties.Add("Authorized Date", DateTime.Today);
properties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
properties.Add("Authorized Amount", 123.45);

// La collection trie les propriétés personnalisées par ordre alphabétique.
Assert.AreEqual(1, properties.IndexOf("Authorized Amount"));
Assert.AreEqual(5, properties.Count);

// Imprime chaque propriété personnalisée dans le document.
using (IEnumerator<DocumentProperty> enumerator = properties.GetEnumerator())
{
    while (enumerator.MoveNext())
        Console.WriteLine($"Name: \"{enumerator.Current.Name}\"\n\tType: \"{enumerator.Current.Type}\"\n\tValue: \"{enumerator.Current.Value}\"");
}

// Affiche la valeur d'une propriété personnalisée à l'aide d'un champ DOCPROPERTY.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldDocProperty field = (FieldDocProperty)builder.InsertField(" DOCPROPERTY \"Authorized By\"");
field.Update();

Assert.AreEqual("John Doe", field.Result);

// Nous pouvons trouver ces propriétés personnalisées dans Microsoft Word via "Fichier" -> "Propriétés" > "Propriétés avancées" > "Personnalisé".
doc.Save(ArtifactsDir + "DocumentProperties.DocumentPropertyCollection.docx");

// Vous trouverez ci-dessous trois façons de supprimer les propriétés personnalisées d'un document.
// 1 - Supprimer par index :
properties.RemoveAt(1);

Assert.False(properties.Contains("Authorized Amount"));
Assert.AreEqual(4, properties.Count);

// 2 - Supprimer par nom :
properties.Remove("Authorized Revision");

Assert.False(properties.Contains("Authorized Revision"));
Assert.AreEqual(3, properties.Count);

// 3 - Vide toute la collection d'un coup :
properties.Clear();

Assert.AreEqual(0, properties.Count);
```

### Voir également

* class [DocumentProperty](../../documentproperty/)
* class [CustomDocumentProperties](../)
* espace de noms [Aspose.Words.Properties](../../customdocumentproperties/)
* Assemblée [Aspose.Words](../../../)

---

## Add(string, double) {#add_1}

Crée une nouvelle propriété de document personnalisée du **PropertyType.Float** type de données.

```csharp
public DocumentProperty Add(string name, double value)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| name | String | Le nom de la propriété. |
| value | Double | La valeur de la propriété. |

### Return_Value

L'objet de propriété nouvellement créé.

### Exemples

Montre comment utiliser les propriétés personnalisées d'un document.

```csharp
Document doc = new Document();
CustomDocumentProperties properties = doc.CustomDocumentProperties;

Assert.AreEqual(0, properties.Count);

// Les propriétés de document personnalisées sont des paires clé-valeur que nous pouvons ajouter au document.
properties.Add("Authorized", true);
properties.Add("Authorized By", "John Doe");
properties.Add("Authorized Date", DateTime.Today);
properties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
properties.Add("Authorized Amount", 123.45);

// La collection trie les propriétés personnalisées par ordre alphabétique.
Assert.AreEqual(1, properties.IndexOf("Authorized Amount"));
Assert.AreEqual(5, properties.Count);

// Imprime chaque propriété personnalisée dans le document.
using (IEnumerator<DocumentProperty> enumerator = properties.GetEnumerator())
{
    while (enumerator.MoveNext())
        Console.WriteLine($"Name: \"{enumerator.Current.Name}\"\n\tType: \"{enumerator.Current.Type}\"\n\tValue: \"{enumerator.Current.Value}\"");
}

// Affiche la valeur d'une propriété personnalisée à l'aide d'un champ DOCPROPERTY.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldDocProperty field = (FieldDocProperty)builder.InsertField(" DOCPROPERTY \"Authorized By\"");
field.Update();

Assert.AreEqual("John Doe", field.Result);

// Nous pouvons trouver ces propriétés personnalisées dans Microsoft Word via "Fichier" -> "Propriétés" > "Propriétés avancées" > "Personnalisé".
doc.Save(ArtifactsDir + "DocumentProperties.DocumentPropertyCollection.docx");

// Vous trouverez ci-dessous trois façons de supprimer les propriétés personnalisées d'un document.
// 1 - Supprimer par index :
properties.RemoveAt(1);

Assert.False(properties.Contains("Authorized Amount"));
Assert.AreEqual(4, properties.Count);

// 2 - Supprimer par nom :
properties.Remove("Authorized Revision");

Assert.False(properties.Contains("Authorized Revision"));
Assert.AreEqual(3, properties.Count);

// 3 - Vide toute la collection d'un coup :
properties.Clear();

Assert.AreEqual(0, properties.Count);
```

### Voir également

* class [DocumentProperty](../../documentproperty/)
* class [CustomDocumentProperties](../)
* espace de noms [Aspose.Words.Properties](../../customdocumentproperties/)
* Assemblée [Aspose.Words](../../../)


