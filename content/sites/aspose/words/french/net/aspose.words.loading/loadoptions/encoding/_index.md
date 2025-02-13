---
title: LoadOptions.Encoding
second_title: Référence de l'API Aspose.Words pour .NET
description: LoadOptions propriété. Obtient ou définit lencodage qui sera utilisé pour charger un document HTML TXT ou CHM si lencodage nest pas spécifié dans le document. Peut être nul. La valeur par défaut est null.
type: docs
weight: 50
url: /fr/net/aspose.words.loading/loadoptions/encoding/
---
## LoadOptions.Encoding property

Obtient ou définit l'encodage qui sera utilisé pour charger un document HTML, TXT ou CHM si l'encodage n'est pas spécifié dans le document. Peut être nul. La valeur par défaut est null.

```csharp
public Encoding Encoding { get; set; }
```

### Remarques

Cette propriété est utilisée uniquement lors du chargement de documents HTML, TXT ou CHM.

Si l'encodage n'est pas spécifié dans le document et que cette propriété est`nul`, le système essaiera de détecter automatiquement l'encodage.

### Exemples

Montre comment définir l'encodage avec lequel ouvrir un document.

```csharp
// Un objet FileFormatInfo détectera ce fichier comme étant encodé dans autre chose que UTF-7.
FileFormatInfo fileFormatInfo = FileFormatUtil.DetectFileFormat(MyDir + "Encoded in UTF-7.txt");

Assert.AreNotEqual(Encoding.UTF7, fileFormatInfo.Encoding);

// Si nous chargeons le document sans configuration de chargement, Aspose.Words détectera son encodage en UTF-8.
Document doc = new Document(MyDir + "Encoded in UTF-7.txt");

// Le contenu, analysé en UTF-8, crée une chaîne valide.
// Cependant, sachant que le fichier est en UTF-7, on peut voir que le résultat est incorrect.
Assert.AreEqual("Hello world+ACE-", doc.ToString(SaveFormat.Text).Trim());

// En cas d'encodage ambigu comme celui-ci, nous pouvons définir une variante d'encodage spécifique
// pour analyser le fichier dans un objet LoadOptions.
LoadOptions loadOptions = new LoadOptions
{
    Encoding = Encoding.UTF7
};

// Charge le document en passant l'objet LoadOptions, puis vérifie le contenu du document.
doc = new Document(MyDir + "Encoded in UTF-7.txt", loadOptions);

Assert.AreEqual("Hello world!", doc.ToString(SaveFormat.Text).Trim());
```

### Voir également

* class [LoadOptions](../)
* espace de noms [Aspose.Words.Loading](../../loadoptions/)
* Assemblée [Aspose.Words](../../../)


