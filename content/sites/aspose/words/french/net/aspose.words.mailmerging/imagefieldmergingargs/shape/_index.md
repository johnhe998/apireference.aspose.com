---
title: ImageFieldMergingArgs.Shape
second_title: Référence de l'API Aspose.Words pour .NET
description: ImageFieldMergingArgs propriété. Spécifie la forme que le moteur de publipostage doit insérer dans le document.
type: docs
weight: 60
url: /fr/net/aspose.words.mailmerging/imagefieldmergingargs/shape/
---
## ImageFieldMergingArgs.Shape property

Spécifie la forme que le moteur de publipostage doit insérer dans le document.

```csharp
public Shape Shape { get; set; }
```

### Remarques

Lorsque cette propriété est spécifiée, le moteur de fusion et publipostage ignore toutes les autres propriétés telles que[`ImageFileName`](../imagefilename/) ou[`ImageStream`](../imagestream/) et insère simplement la forme dans le document.

Utilisez cette propriété pour contrôler entièrement le processus de fusion d'un champ de fusion d'image. Par exemple, vous pouvez spécifier[`WrapType`](../../../aspose.words.drawing/shapebase/wraptype/)ou toute autre propriété de forme pour affiner le nœud résultant. Cependant, veuillez noter que vous êtes responsable de fournir le contenu de la forme.

### Voir également

* class [Shape](../../../aspose.words.drawing/shape/)
* class [ImageFieldMergingArgs](../)
* espace de noms [Aspose.Words.MailMerging](../../imagefieldmergingargs/)
* Assemblée [Aspose.Words](../../../)


