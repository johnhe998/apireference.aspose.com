---
title: Class SdtListItem
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Markup.SdtListItem classe. Cet élément spécifie un seul élément de liste dans un parentComboBox ouDropDownList balise de document structuré.
type: docs
weight: 3780
url: /fr/net/aspose.words.markup/sdtlistitem/
---
## SdtListItem class

Cet élément spécifie un seul élément de liste dans un parentComboBox ouDropDownList balise de document structuré.

```csharp
public class SdtListItem
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [SdtListItem](sdtlistitem/#constructor)(string) | Initialise une nouvelle instance de cette classe. |
| [SdtListItem](sdtlistitem/#constructor_1)(string, string) | Initialise une nouvelle instance de cette classe. |

## Propriétés

| Nom | La description |
| --- | --- |
| [DisplayText](../../aspose.words.markup/sdtlistitem/displaytext/) { get; } | Obtient le texte à afficher dans le contenu d'exécution à la place du[`Value`](./value/) contenu d'attribut pour cet élément de liste. |
| [Value](../../aspose.words.markup/sdtlistitem/value/) { get; } | Obtient la valeur de cet élément de liste. |

### Exemples

Montre comment travailler avec des balises de document structurées en liste déroulante.

```csharp
Document doc = new Document();
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.DropDownList, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(tag);

// Une balise de document structurée par liste déroulante est un formulaire qui permet à l'utilisateur de
// sélectionnez une option dans une liste en cliquant avec le bouton gauche et en ouvrant le formulaire dans Microsoft Word.
// La propriété "ListItems" contient tous les éléments de la liste, et chaque élément de la liste est un "SdtListItem".
SdtListItemCollection listItems = tag.ListItems;
listItems.Add(new SdtListItem("Value 1"));

Assert.AreEqual(listItems[0].DisplayText, listItems[0].Value);

// Ajouter 3 autres éléments de liste. Initialisez ces éléments en utilisant un constructeur différent du premier élément
// pour afficher les chaînes qui sont différentes de leurs valeurs.
listItems.Add(new SdtListItem("Item 2", "Value 2"));
listItems.Add(new SdtListItem("Item 3", "Value 3"));
listItems.Add(new SdtListItem("Item 4", "Value 4"));

Assert.AreEqual(4, listItems.Count);

// La liste déroulante affiche le premier élément. Attribuez un élément de liste différent à "SelectedValue" pour l'afficher.
listItems.SelectedValue = listItems[3];

Assert.AreEqual("Value 4", listItems.SelectedValue.Value);

// Énumère la collection et imprime chaque élément.
using (IEnumerator<SdtListItem> enumerator = listItems.GetEnumerator())
{
    while (enumerator.MoveNext())
        if (enumerator.Current != null)
            Console.WriteLine($"List item: {enumerator.Current.DisplayText}, value: {enumerator.Current.Value}");
}

 // Supprime le dernier élément de la liste.
listItems.RemoveAt(3);

Assert.AreEqual(3, listItems.Count);

// Étant donné que notre contrôle déroulant est configuré pour afficher l'élément supprimé par défaut, donnez-lui un élément à afficher qui existe.
listItems.SelectedValue = listItems[1];

doc.Save(ArtifactsDir + "StructuredDocumentTag.ListItemCollection.docx");

// Utilisez la méthode "Clear" pour vider d'un coup toute la collection d'éléments déroulants.
listItems.Clear();

Assert.AreEqual(0, listItems.Count);
```

### Voir également

* espace de noms [Aspose.Words.Markup](../../aspose.words.markup/)
* Assemblée [Aspose.Words](../../)


