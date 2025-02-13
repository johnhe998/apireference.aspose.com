---
title: DocSaveOptions.SavePictureBullet
second_title: Référence de l'API Aspose.Words pour .NET
description: DocSaveOptions propriété. Quandfaux  les données PictureBullet ne sont pas enregistrées dans le document de sortie. La valeur par défaut est vrai .
type: docs
weight: 50
url: /fr/net/aspose.words.saving/docsaveoptions/savepicturebullet/
---
## DocSaveOptions.SavePictureBullet property

Quand`faux` , les données PictureBullet ne sont pas enregistrées dans le document de sortie. La valeur par défaut est **vrai** .

```csharp
public bool SavePictureBullet { get; set; }
```

### Remarques

Cette option est fournie pour Word 97, qui ne peut pas fonctionner correctement avec les données PictureBullet. Pour supprimer les données PictureBullet, définissez l'option sur "false".

### Exemples

Montre comment omettre les données PictureBullet du document lors de l'enregistrement.

```csharp
Document doc = new Document(MyDir + "Image bullet points.docx");

// Certains traitements de texte, tels que Microsoft Word 97, sont incompatibles avec les données PictureBullet.
// En définissant un indicateur dans l'objet SaveOptions,
// nous pouvons convertir toutes les puces de l'image en puces ordinaires lors de l'enregistrement.
DocSaveOptions saveOptions = new DocSaveOptions(SaveFormat.Doc);
saveOptions.SavePictureBullet = false;

doc.Save(ArtifactsDir + "DocSaveOptions.PictureBullets.doc", saveOptions);
```

### Voir également

* class [DocSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../docsaveoptions/)
* Assemblée [Aspose.Words](../../../)


