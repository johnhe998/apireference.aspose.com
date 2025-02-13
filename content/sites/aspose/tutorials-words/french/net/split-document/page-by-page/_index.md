---
title: Diviser un document Word par page
linktitle: Diviser un document Word par page
second_title: API de traitement de documents Aspose.Words
description: Apprenez à diviser un document Word en pages individuelles à l'aide d'Aspose.Words pour .NET. Cette puissante API simplifie le processus de fractionnement des documents, le rendant efficace et pratique.
type: docs
weight: 10
url: /fr/net/split-document/page-by-page/
---

Dans ce didacticiel, nous vous expliquerons comment diviser un document Word en pages individuelles à l'aide de la fonction de traitement de document d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et obtenir des documents distincts pour chaque page.

## Étape 1 : Chargement du document

Pour commencer, spécifiez le répertoire de votre document et chargez le document dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Étape 2 : Découpage du document par page

Nous allons maintenant parcourir chaque page du document et diviser le document en pages individuelles. Voici comment:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Enregistrez chaque page dans un document distinct.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Exemple de code source pour Page By Page utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Page par page d'Aspose.Words pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	// Enregistrez chaque page dans un document distinct.
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

Avec ce code, vous pourrez diviser un document Word en pages individuelles en utilisant Aspose.Words pour .NET. Vous pouvez également fusionner des documents distincts si nécessaire.

## Conclusion

Toutes nos félicitations! Vous avez appris à diviser un document Word en pages individuelles à l'aide de la fonctionnalité Page par page d'Aspose.Words pour .NET. En suivant le code source fourni, vous pouvez extraire chaque page d'un document et les enregistrer en tant que documents distincts.

Fractionner un document par page peut être utile lorsque vous devez travailler avec des pages spécifiques ou distribuer du contenu de manière granulaire. Aspose.Words pour .NET fournit une API puissante qui simplifie le processus de fractionnement des documents, le rendant efficace et pratique.

N'hésitez pas à explorer d'autres fonctionnalités offertes par Aspose.Words pour .NET pour améliorer vos capacités de traitement de documents et rationaliser votre flux de travail.

### FAQ

#### Comment puis-je diviser un document en plusieurs pages en utilisant Aspose.Words pour .NET ?

 Pour diviser un document en plusieurs pages, vous pouvez utiliser le`ExtractPages` méthode de l'API Aspose.Words pour obtenir la plage de pages. En spécifiant la page de départ et le nombre de pages à extraire, vous pouvez créer des documents distincts pour chaque page.

#### Puis-je personnaliser le format de sortie lors de la division d'un document par page ?

Oui, Aspose.Words pour .NET prend en charge divers formats de sortie lors du fractionnement d'un document par page. Vous pouvez enregistrer chaque page en tant que document distinct dans des formats tels que DOCX, PDF, HTML, etc., selon vos besoins.

#### Puis-je diviser un document par une plage de pages spécifique ?

Absolument! Aspose.Words pour .NET vous permet de diviser un document par une plage de pages spécifique. En ajustant la page de départ et le nombre de pages à extraire, vous pouvez définir précisément la plage de pages pour fractionner le document.

#### Est-il possible de fusionner les documents fractionnés en un seul document ?

Oui, vous pouvez fusionner les documents fractionnés en un seul document à l'aide de la fonctionnalité de fusion fournie par Aspose.Words pour .NET. En combinant les documents séparés, vous pouvez recréer le document d'origine ou créer un nouveau document avec une structure différente, selon vos besoins.