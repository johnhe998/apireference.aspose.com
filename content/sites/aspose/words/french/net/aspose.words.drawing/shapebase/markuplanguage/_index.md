---
title: ShapeBase.MarkupLanguage
second_title: Référence de l'API Aspose.Words pour .NET
description: ShapeBase propriété. Récupère MarkupLanguage utilisé pour cet objet graphique.
type: docs
weight: 370
url: /fr/net/aspose.words.drawing/shapebase/markuplanguage/
---
## ShapeBase.MarkupLanguage property

Récupère MarkupLanguage utilisé pour cet objet graphique.

```csharp
public ShapeMarkupLanguage MarkupLanguage { get; }
```

### Exemples

Montre comment vérifier la taille et le langage de balisage d'une forme.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Transparent background logo.png");

Assert.AreEqual(ShapeMarkupLanguage.Dml, shape.MarkupLanguage);
Assert.AreEqual(new SizeF(300, 300), shape.SizeInPoints);
```

### Voir également

* enum [ShapeMarkupLanguage](../../shapemarkuplanguage/)
* class [ShapeBase](../)
* espace de noms [Aspose.Words.Drawing](../../shapebase/)
* Assemblée [Aspose.Words](../../../)


