---
title: Font.LocaleId
second_title: Référence de l'API Aspose.Words pour .NET
description: Font propriété. Obtient ou définit lidentificateur de paramètres régionaux langue des caractères formatés.
type: docs
weight: 200
url: /fr/net/aspose.words/font/localeid/
---
## Font.LocaleId property

Obtient ou définit l'identificateur de paramètres régionaux (langue) des caractères formatés.

```csharp
public int LocaleId { get; set; }
```

### Remarques

Pour la liste des identifiants de paramètres régionaux, voir https://msdn.microsoft.com/en-us/library/cc233965.aspx

### Exemples

Montre comment définir les paramètres régionaux du texte que nous ajoutons avec un générateur de document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Si nous définissons les paramètres régionaux de la police sur l'anglais et insérons du texte russe,
// le correcteur orthographique des paramètres régionaux anglais ne reconnaîtra pas le texte et le détectera comme une faute d'orthographe.
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;
builder.Writeln("Привет!");

// Définir une locale correspondante pour le texte que nous sommes sur le point d'ajouter pour appliquer le correcteur orthographique approprié.
builder.Font.LocaleId = new CultureInfo("ru-RU", false).LCID;
builder.Writeln("Привет!");

doc.Save(ArtifactsDir + "Font.LocaleId.docx");
```

### Voir également

* class [Font](../)
* espace de noms [Aspose.Words](../../font/)
* Assemblée [Aspose.Words](../../../)


