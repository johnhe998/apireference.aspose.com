---
title: Font.NameAscii
second_title: Référence de l'API Aspose.Words pour .NET
description: Font propriété. Renvoie ou définit la police utilisée pour le texte latin caractères avec des codes de caractère de 0 zéro à 127.
type: docs
weight: 240
url: /fr/net/aspose.words/font/nameascii/
---
## Font.NameAscii property

Renvoie ou définit la police utilisée pour le texte latin (caractères avec des codes de caractère de 0 (zéro) à 127).

```csharp
public string NameAscii { get; set; }
```

### Exemples

Montre comment Microsoft Word peut combiner deux polices différentes en une seule exécution.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Supposons une exécution que nous utilisons le constructeur pour insérer lors de l'utilisation de cette configuration de police
// contient des caractères dans la plage des caractères ASCII. Dans ce cas,
// il affichera ces caractères en utilisant cette police.
builder.Font.NameAscii = "Calibri";

// Sans autre police spécifiée, le générateur appliquera également cette police à tous les caractères qu'il insère.
Assert.AreEqual("Calibri", builder.Font.Name);

// Spécifiez une police à utiliser pour tous les caractères en dehors de la plage ASCII.
// Idéalement, cette police devrait avoir un glyphe pour chaque code de caractère non-ASCII requis.
builder.Font.NameOther = "Courier New";

// Insère une exécution avec un mot composé de caractères ASCII et un mot avec tous les caractères en dehors de cette plage.
// Chaque caractère sera affiché en utilisant l'une des polices, selon.
builder.Writeln("Hello, Привет");

doc.Save(ArtifactsDir + "Font.NameAscii.docx");
```

### Voir également

* property [Name](../name/)
* class [Font](../)
* espace de noms [Aspose.Words](../../font/)
* Assemblée [Aspose.Words](../../../)


