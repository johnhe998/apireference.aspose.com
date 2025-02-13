---
title: OleFormat.OlePackage
second_title: Référence de l'API Aspose.Words pour .NET
description: OleFormat propriété. Fournir laccès àOlePackage si lobjet OLE est un package OLE. Renvoie null sinon.
type: docs
weight: 80
url: /fr/net/aspose.words.drawing/oleformat/olepackage/
---
## OleFormat.OlePackage property

Fournir l'accès à[`OlePackage`](../../olepackage/) si l'objet OLE est un package OLE. Renvoie null sinon.

```csharp
public OlePackage OlePackage { get; }
```

### Remarques

Le package OLE est une technologie héritée qui permet d'encapsuler n'importe quel format de fichier non présent dans le registre OLE de un système Windows dans un package générique permettant d'intégrer presque n'importe quoi dans un document. Voir[`OlePackage`](../../olepackage/)tapez pour plus d'informations.

### Exemples

Montre comment insérer un objet OLE dans un document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Les objets OLE nous permettent d'ouvrir d'autres fichiers dans le système de fichiers local à l'aide d'une autre application installée
// dans notre système d'exploitation en double-cliquant sur la forme qui contient l'objet OLE dans le corps du document.
// Dans ce cas, notre fichier externe sera une archive ZIP.
byte[] zipFileBytes = File.ReadAllBytes(DatabaseDir + "cat001.zip");

using (MemoryStream stream = new MemoryStream(zipFileBytes))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);

    shape.OleFormat.OlePackage.FileName = "Package file name.zip";
    shape.OleFormat.OlePackage.DisplayName = "Package display name.zip";
}

doc.Save(ArtifactsDir + "Shape.InsertOlePackage.docx");
```

### Voir également

* class [OlePackage](../../olepackage/)
* class [OleFormat](../)
* espace de noms [Aspose.Words.Drawing](../../oleformat/)
* Assemblée [Aspose.Words](../../../)


