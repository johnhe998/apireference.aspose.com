---
title: CustomXmlPart.Id
second_title: Référence de l'API Aspose.Words pour .NET
description: CustomXmlPart propriété. Obtient ou définit la chaîne qui identifie cette partie XML personnalisée dans un document OOXML.
type: docs
weight: 40
url: /fr/net/aspose.words.markup/customxmlpart/id/
---
## CustomXmlPart.Id property

Obtient ou définit la chaîne qui identifie cette partie XML personnalisée dans un document OOXML.

```csharp
public string Id { get; set; }
```

### Remarques

ISO/IEC 29500 spécifie que cette valeur est un GUID, mais les anciennes versions de Microsoft Word autorisaient ici any string. Aspose.Words fait de même pour le format ECMA-376. Mais notez que Microsoft Word Online échoue pour ouvrir un document créé avec une valeur non GUID. Ainsi, un GUID est la valeur préférée pour cette propriété.

Une valeur valide doit être un identifiant unique parmi toutes les parties de données XML personnalisées de ce document.

La valeur par défaut est une chaîne vide. La valeur ne peut pas être`nul`.

### Exemples

Montre comment créer une balise de document structurée avec des données XML personnalisées.

```csharp
Document doc = new Document();

// Construire une partie XML qui contient des données et l'ajouter à la collection du document.
// Si nous activons l'onglet "Développeur" dans Microsoft Word,
// nous pouvons trouver des éléments de cette collection dans le "XML Mapping Pane", ainsi que quelques éléments par défaut.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Hello world!</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

Assert.AreEqual(Encoding.ASCII.GetBytes(xmlPartContent), xmlPart.Data);
Assert.AreEqual(xmlPartId, xmlPart.Id);

// Vous trouverez ci-dessous deux façons de faire référence à des parties XML.
// 1 - Par un index dans la collection de parties XML personnalisée :
Assert.AreEqual(xmlPart, doc.CustomXmlParts[0]);

// 2 - Par GUID :
Assert.AreEqual(xmlPart, doc.CustomXmlParts.GetById(xmlPartId));

// Ajouter une association de schéma XML.
xmlPart.Schemas.Add("http://www.w3.org/2001/XMLSchema");

// Clone une partie, puis l'insère dans la collection.
CustomXmlPart xmlPartClone = xmlPart.Clone();
xmlPartClone.Id = Guid.NewGuid().ToString("B");
doc.CustomXmlParts.Add(xmlPartClone);

Assert.AreEqual(2, doc.CustomXmlParts.Count);

// Itérer dans la collection et imprimer le contenu de chaque partie.
using (IEnumerator<CustomXmlPart> enumerator = doc.CustomXmlParts.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"XML part index {index}, ID: {enumerator.Current.Id}");
        Console.WriteLine($"\tContent: {Encoding.UTF8.GetString(enumerator.Current.Data)}");
        index++;
    }
}

// Utilisez la méthode "RemoveAt" pour supprimer la partie clonée par index.
doc.CustomXmlParts.RemoveAt(1);

Assert.AreEqual(1, doc.CustomXmlParts.Count);

// Clone la collection de parties XML, puis utilise la méthode "Clear" pour supprimer tous ses éléments d'un coup.
CustomXmlPartCollection customXmlParts = doc.CustomXmlParts.Clone();
customXmlParts.Clear();

// Crée une balise de document structurée qui affichera le contenu de notre partie et l'insérera dans le corps du document.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
tag.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", string.Empty);

doc.FirstSection.Body.AppendChild(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.CustomXml.docx");
```

### Voir également

* class [CustomXmlPart](../)
* espace de noms [Aspose.Words.Markup](../../customxmlpart/)
* Assemblée [Aspose.Words](../../../)


