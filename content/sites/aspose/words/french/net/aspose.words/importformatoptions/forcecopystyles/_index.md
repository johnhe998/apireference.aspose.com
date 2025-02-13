---
title: ImportFormatOptions.ForceCopyStyles
second_title: Référence de l'API Aspose.Words pour .NET
description: ImportFormatOptions propriété. Obtient ou définit une valeur booléenne indiquant soit de copier les styles en conflit dansKeepSourceFormatting mode. La valeur par défaut estfaux .
type: docs
weight: 20
url: /fr/net/aspose.words/importformatoptions/forcecopystyles/
---
## ImportFormatOptions.ForceCopyStyles property

Obtient ou définit une valeur booléenne indiquant soit de copier les styles en conflit dansKeepSourceFormatting mode. La valeur par défaut est`faux` .

```csharp
public bool ForceCopyStyles { get; set; }
```

### Remarques

Par défaut, si un style correspondant existe déjà dans un document de destination, le style source formatting est développé en attributs de nœud direct et le style de ce nœud est réinitialisé à une valeur par défaut.

Lorsque cette option est définie sur`vrai`, le style source sera copié de force dans le document de destination avec un nom unique et appliqué au nœud importé.

Notez que dans ce cas, il n'est pas garanti que la mise en forme du nœud importé dans le document de destination sera préservée.

### Exemples

Montre comment copier de force des styles source avec des noms uniques.

```csharp
// Les deux documents contiennent MyStyle1 et MyStyle2, MyStyle3 n'existe que dans un document source.
Document srcDoc = new Document(MyDir + "Styles source.docx");
Document dstDoc = new Document(MyDir + "Styles destination.docx");

ImportFormatOptions options = new ImportFormatOptions { ForceCopyStyles = true };
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting, options);

ParagraphCollection paras = dstDoc.Sections[1].Body.Paragraphs;

Assert.AreEqual(paras[0].ParagraphFormat.Style.Name, "MyStyle1_0");
Assert.AreEqual(paras[1].ParagraphFormat.Style.Name, "MyStyle2_0");
Assert.AreEqual(paras[2].ParagraphFormat.Style.Name, "MyStyle3");
```

### Voir également

* class [ImportFormatOptions](../)
* espace de noms [Aspose.Words](../../importformatoptions/)
* Assemblée [Aspose.Words](../../../)


