---
title: Style.BuiltIn
second_title: Référence de l'API Aspose.Words pour .NET
description: Style propriété. Vrai si ce style est lun des styles intégrés dans MS Word.
type: docs
weight: 30
url: /fr/net/aspose.words/style/builtin/
---
## Style.BuiltIn property

Vrai si ce style est l'un des styles intégrés dans MS Word.

```csharp
public bool BuiltIn { get; }
```

### Exemples

Montre comment différencier les styles personnalisés des styles intégrés.

```csharp
Document doc = new Document();

// Lorsque nous créons un document à l'aide de Microsoft Word ou par programmation à l'aide de Aspose.Words,
// le document viendra avec une collection de styles à appliquer à son texte pour modifier son apparence.
// Nous pouvons accéder à ces styles intégrés via la collection "Styles" du document.
// Ces styles auront tous le drapeau "BuiltIn" défini sur "true".
Style style = doc.Styles["Emphasis"];

Assert.True(style.BuiltIn);

// Crée un style personnalisé et l'ajoute à la collection.
 // Les styles personnalisés tels que celui-ci auront le drapeau "BuiltIn" défini sur "false".
style = doc.Styles.Add(StyleType.Character, "MyStyle");
style.Font.Color = Color.Navy;
style.Font.Name = "Courier New";

Assert.False(style.BuiltIn);
```

### Voir également

* class [Style](../)
* espace de noms [Aspose.Words](../../style/)
* Assemblée [Aspose.Words](../../../)


