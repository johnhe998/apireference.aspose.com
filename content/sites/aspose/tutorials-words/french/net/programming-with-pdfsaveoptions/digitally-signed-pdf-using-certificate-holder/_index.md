---
title: Ajouter une signature numérique au PDF à l'aide du titulaire du certificat
linktitle: Ajouter une signature numérique au PDF à l'aide du titulaire du certificat
second_title: API de traitement de documents Aspose.Words
description: Apprenez à ajouter une signature numérique au PDF à l'aide du titulaire du certificat avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

Dans ce didacticiel, nous vous expliquerons les étapes à suivre pour ajouter une signature numérique à un PDF à l'aide d'un détenteur de certificat avec Aspose.Words pour .NET. La signature numérique ajoute une couche de sécurité et d'intégrité au document PDF. Suivez les étapes ci-dessous :

## Étape 1 : création du document et ajout de contenu

Commencez par créer une instance de la classe Document :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Ajouter du contenu au document

 Utilisez ensuite le`DocumentBuilder`pour ajouter du contenu au document. Par exemple, pour ajouter un paragraphe contenant le texte "Tester le PDF signé", utilisez la`Writeln` méthode:

```csharp
builder.Writeln("Test Signed PDF.");
```

Vous pouvez ajouter d'autres éléments de contenu si nécessaire.

## Étape 3 : Définir les options d'enregistrement PDF

Créez une instance de la classe PdfSaveOptions et spécifiez les détails de la signature numérique :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Assurez-vous de spécifier le chemin correct vers votre certificat et le mot de passe associé. Vous pouvez également personnaliser la raison et l'emplacement de la signature.

## Étape 4 : Enregistrer le document en tant que PDF signé numériquement

 Utilisez le`Save` méthode pour enregistrer le document au format PDF en spécifiant les options d'enregistrement :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin d'accès correct pour enregistrer le PDF signé numériquement.

En suivant ces étapes, vous pouvez facilement créer un PDF signé numériquement avec un certificat en utilisant Aspose.Words pour .NET.

### Exemple de code source pour un PDF signé numériquement à l'aide d'un détenteur de certificat à l'aide d'Aspose.Words pour .NET

Voici le code source complet du Pdf signé numériquement à l'aide du titulaire du certificat d'un document utilisant Aspose.Words pour .NET :

```csharp

            // Chemin d'accès au répertoire des documents.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## Conclusion

Dans ce didacticiel, nous avons exploré les étapes pour ajouter une signature numérique à un document PDF à l'aide d'un certificat avec Aspose.Words pour .NET. La signature numérique ajoute une couche de sécurité et d'intégrité au document, garantissant ainsi son authenticité et permettant de détecter toute modification ultérieure. En suivant les étapes indiquées, vous pouvez facilement créer un PDF signé numériquement à l'aide d'un certificat avec Aspose.Words pour .NET.

### Questions fréquemment posées

#### Q : Qu'est-ce qu'une signature numérique et pourquoi est-elle importante dans un document PDF ?
R : Une signature numérique est une technique de sécurité qui permet de garantir l'authenticité, l'intégrité et la non-répudiation d'un document électronique, tel qu'un fichier PDF. Il utilise un certificat numérique pour ajouter une couche de sécurité au document, ce qui permet de vérifier l'identité de l'auteur et de détecter toute modification ultérieure du contenu.

#### Q : Comment puis-je ajouter une signature numérique à un document PDF à l'aide d'un certificat avec Aspose.Words pour .NET ?
R : Pour ajouter une signature numérique à un document PDF à l'aide d'un certificat avec Aspose.Words pour .NET, suivez ces étapes :

 Créer une instance de`Document` classe pour représenter le document.

 Utilisez le`DocumentBuilder` classe pour ajouter le contenu souhaité au document.

 Créer une instance de`PdfSaveOptions` classe et spécifiez les détails de la signature numérique à l'aide de la`PdfDigitalSignatureDetails` classe. Vous devrez fournir le chemin d'accès au certificat (`CertificateHolder.Create`), le mot de passe associé, ainsi que le motif et l'emplacement de la signature.

 Utilisez le`Save` méthode pour enregistrer le document au format PDF en spécifiant les options d'enregistrement.

#### Q : Comment puis-je obtenir un certificat pour ajouter une signature numérique à un document PDF ?
R : Pour obtenir un certificat permettant d'ajouter une signature numérique à un document PDF, vous pouvez généralement contacter une autorité de certification (AC) ou un fournisseur de services de confiance. Ces entités délivrent des certificats numériques après vérification de votre identité et validation de votre demande. Une fois que vous avez obtenu un certificat, vous pouvez l'utiliser dans votre application pour ajouter des signatures numériques aux documents PDF.

#### Q : Est-il possible de personnaliser les détails de la signature numérique, tels que le motif et l'emplacement ?
 R : Oui, vous pouvez personnaliser les détails de la signature numérique en spécifiant la raison et l'emplacement de la signature. Dans l'exemple de code fourni, vous pouvez modifier les valeurs des`reason` et`location` paramètres lors de la création du`PdfDigitalSignatureDetails` objet. Assurez-vous de fournir les informations appropriées pour chaque paramètre afin de refléter la raison et l'emplacement de la signature dans votre document PDF.