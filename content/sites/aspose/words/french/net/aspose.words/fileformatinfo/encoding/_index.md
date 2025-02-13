---
title: FileFormatInfo.Encoding
second_title: Référence de l'API Aspose.Words pour .NET
description: FileFormatInfo propriété. Obtient lencodage détecté si applicable au format de document actuel. Détecte actuellement lencodage uniquement pour les documents HTML.
type: docs
weight: 10
url: /fr/net/aspose.words/fileformatinfo/encoding/
---
## FileFormatInfo.Encoding property

Obtient l'encodage détecté si applicable au format de document actuel. Détecte actuellement l'encodage uniquement pour les documents HTML.

```csharp
public Encoding Encoding { get; }
```

### Exemples

Montre comment détecter l'encodage dans un fichier html.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(MyDir + "Document.html");

Assert.AreEqual(LoadFormat.Html, info.LoadFormat);

// La propriété Encoding est utilisée uniquement lorsque nous créons un objet FileFormatInfo pour un document html.
Assert.AreEqual("Western European (Windows)", info.Encoding.EncodingName);
Assert.AreEqual(1252, info.Encoding.CodePage);
```

### Voir également

* class [FileFormatInfo](../)
* espace de noms [Aspose.Words](../../fileformatinfo/)
* Assemblée [Aspose.Words](../../../)


