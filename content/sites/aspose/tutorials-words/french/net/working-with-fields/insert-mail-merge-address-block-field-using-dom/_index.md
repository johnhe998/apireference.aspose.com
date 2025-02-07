---
title: Insérer un champ de bloc d'adresse de fusion et publipostage à l'aide de DOM
linktitle: Insérer un champ de bloc d'adresse de fusion et publipostage à l'aide de DOM
second_title: API de traitement de documents Aspose.Words
description: Apprenez à insérer un champ de bloc d'adresse de fusion et publipostage dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité "Insert Mail Merge Address Block Field" d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez spécifier le répertoire de vos documents. Remplacez la valeur "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document et de DocumentBuilder

Nous commençons par créer un nouveau document et initialiser un DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Déplacer le curseur vers le paragraphe

 Nous utilisons le DocumentBuilder`MoveTo()` méthode pour déplacer le curseur vers le paragraphe où nous voulons insérer le champ de bloc d'adresse de fusion et publipostage.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Étape 4 : Insertion du champ de bloc d'adresse de publipostage

 Nous utilisons le DocumentBuilder`InsertField()` méthode pour insérer un champ de bloc d'adresse de fusion et publipostage dans le paragraphe.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Nous configurons ensuite les propriétés du champ de bloc d'adresse en spécifiant les options appropriées, telles que l'inclusion du nom du pays/de la région, le formatage de l'adresse en fonction du pays/de la région, les noms de pays/de la région exclus, le format du nom et de l'adresse et l'identifiant de la langue.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Enfin, nous appelons le`Update()` méthode pour mettre à jour le champ.

```csharp
field. Update();
```

### Exemple de code source pour insérer un champ de bloc d'adresse de fusion et publipostage avec Aspose.Words pour .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Nous voulons insérer un bloc d'adresse de fusion et publipostage comme celui-ci :
// { BLOC D'ADRESSES \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { BLOC D'ADRESSES \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { BLOC D'ADRESSES \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { BLOC D'ADRESSES \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { BLOC D'ADRESSES \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { BLOC D'ADRESSES \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### FAQ

#### Q : Comment puis-je personnaliser le format de l'adresse postale dans un document Word avec Aspose.Words pour .NET ?

 R : Vous pouvez personnaliser le format de l'adresse postale dans un document Word avec Aspose.Words pour .NET en utilisant les propriétés du`FieldAddressBlock`objet. Vous pouvez définir les options de formatage telles que le style d'adresse, les séparateurs, les éléments facultatifs, etc. pour obtenir le format souhaité.

#### Q : Comment puis-je spécifier les données source pour le champ d'adresse postale dans Aspose.Words pour .NET ?

 R : Pour spécifier les données source du champ d'adresse postale dans Aspose.Words pour .NET, vous pouvez utiliser le`FieldAddressBlock.StartAddress` et`FieldAddressBlock.EndAddress` propriétés. Ces propriétés sont utilisées pour définir les plages d'adresses dans la source de données externe, comme un fichier CSV, une base de données, etc.

#### Q : Puis-je inclure des éléments facultatifs dans le champ d'adresse postale avec Aspose.Words pour .NET ?

 R : Oui, vous pouvez inclure des éléments facultatifs dans le champ d'adresse postale avec Aspose.Words pour .NET. Vous pouvez définir des éléments facultatifs à l'aide de la`FieldAddressBlock.OmitOptional` méthode pour spécifier s'il faut inclure ou exclure des éléments facultatifs tels que le nom du destinataire, le nom de l'entreprise, etc.

#### Q : L'insertion d'un champ d'adresse postale à l'aide du DOM affecte-t-elle la structure du document Word avec Aspose.Words pour .NET ?

: L'insertion d'un champ d'adresse postale à l'aide du DOM n'affecte pas directement la structure du document Word. Cependant, il ajoute un nouvel élément de champ au contenu du document. Vous pouvez manipuler la structure du document en ajoutant, supprimant ou modifiant les éléments existants selon vos besoins.