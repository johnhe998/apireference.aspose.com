---
title: Contrôle du contenu de la zone de liste déroulante
linktitle: Contrôle du contenu de la zone de liste déroulante
second_title: API de traitement de documents Aspose.Words
description: Apprenez à créer un contrôle de contenu de zone de liste déroulante dans un document Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/combo-box-content-control/
---

Ce didacticiel explique comment créer un contrôle de contenu de zone de liste déroulante dans un document Word à l'aide de Aspose.Words pour .NET. Les contrôles de contenu de la zone de liste déroulante permettent aux utilisateurs de sélectionner un élément dans une liste déroulante.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de texte avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel au répertoire où vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un document et une balise StructuredDocumentTag
 Créez une nouvelle instance de`Document` classe et une`StructuredDocumentTag` pour représenter le contrôle de contenu de la zone de liste déroulante. Spécifier`SdtType.ComboBox` comme type et`MarkupLevel.Block` comme niveau de balisage pour créer une zone de liste déroulante au niveau du bloc.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Étape 3 : Ajouter des éléments à la zone de liste déroulante
 Ajoutez des éléments à la zone de liste déroulante à l'aide de la`ListItems`propriété de la`StructuredDocumentTag` Chaque élément est représenté par un`SdtListItem` objet, qui prend un texte d'affichage et une valeur. Dans cet exemple, nous ajoutons trois éléments à la zone de liste déroulante.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Étape 4 : ajouter le StructuredDocumentTag au document
 Ajoutez le contrôle de contenu de la zone de liste déroulante au corps du document à l'aide de la`AppendChild` méthode du corps de la première section du document.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Étape 5 : Enregistrer le document
 Enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Exemple de code source pour le contrôle du contenu de la zone de liste déroulante à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

C'est ça! Vous avez créé avec succès un contrôle de contenu de zone de liste déroulante dans votre document Word à l'aide de Aspose.Words pour .NET.