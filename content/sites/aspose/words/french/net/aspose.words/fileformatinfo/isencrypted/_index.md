---
title: FileFormatInfo.IsEncrypted
second_title: Référence de l'API Aspose.Words pour .NET
description: FileFormatInfo propriété. Renvoie true si le document est crypté et nécessite un mot de passe pour souvrir.
type: docs
weight: 30
url: /fr/net/aspose.words/fileformatinfo/isencrypted/
---
## FileFormatInfo.IsEncrypted property

Renvoie true si le document est crypté et nécessite un mot de passe pour s'ouvrir.

```csharp
public bool IsEncrypted { get; }
```

### Remarques

Cette propriété existe pour vous aider à trier les documents chiffrés de ceux qui ne le sont pas. Si vous tentez de charger un document chiffré en utilisant Aspose.Words sans fournir de mot de passe, une exception sera levée. Vous pouvez utiliser cette propriété pour détecter si un document nécessite un mot de passe et prendre des mesures avant de charger un document, par exemple, demander à l'utilisateur un mot de passe.

### Exemples

Montre comment utiliser la classe FileFormatUtil pour détecter le format et le chiffrement du document.

```csharp
Document doc = new Document();

// Configure un objet SaveOptions pour chiffrer le document
// avec un mot de passe lorsque nous l'enregistrons, puis enregistrez le document.
OdtSaveOptions saveOptions = new OdtSaveOptions(SaveFormat.Odt);
saveOptions.Password = "MyPassword";

doc.Save(ArtifactsDir + "File.DetectDocumentEncryption.odt", saveOptions);

// Vérifiez le type de fichier de notre document et son statut de cryptage.
FileFormatInfo info = FileFormatUtil.DetectFileFormat(ArtifactsDir + "File.DetectDocumentEncryption.odt");

Assert.AreEqual(".odt", FileFormatUtil.LoadFormatToExtension(info.LoadFormat));
Assert.True(info.IsEncrypted);
```

### Voir également

* class [FileFormatInfo](../)
* espace de noms [Aspose.Words](../../fileformatinfo/)
* Assemblée [Aspose.Words](../../../)


