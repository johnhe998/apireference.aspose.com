---
title: Class ImportFormatOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.ImportFormatOptions classe. Permet de spécifier diverses options dimportation pour formater la sortie.
type: docs
weight: 3040
url: /fr/net/aspose.words/importformatoptions/
---
## ImportFormatOptions class

Permet de spécifier diverses options d'importation pour formater la sortie.

```csharp
public class ImportFormatOptions
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [ImportFormatOptions](importformatoptions/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [ForceCopyStyles](../../aspose.words/importformatoptions/forcecopystyles/) { get; set; } | Obtient ou définit une valeur booléenne indiquant soit de copier les styles en conflit dansKeepSourceFormatting mode. La valeur par défaut est`faux` . |
| [IgnoreHeaderFooter](../../aspose.words/importformatoptions/ignoreheaderfooter/) { get; set; } | Obtient ou définit une valeur booléenne qui spécifie que la mise en forme source du contenu des en-têtes/pieds de page est ignorée siKeepSourceFormatting mode est utilisé. La valeur par défaut est`vrai` . |
| [IgnoreTextBoxes](../../aspose.words/importformatoptions/ignoretextboxes/) { get; set; } | Obtient ou définit une valeur booléenne qui spécifie que la mise en forme source du contenu des zones de texte est ignorée siKeepSourceFormatting mode est utilisé. La valeur par défaut est`vrai` . |
| [KeepSourceNumbering](../../aspose.words/importformatoptions/keepsourcenumbering/) { get; set; } | Obtient ou définit une valeur booléenne qui spécifie comment la numérotation sera importée en cas de conflit dans les documents source et destination. La valeur par défaut est`faux` . |
| [MergePastedLists](../../aspose.words/importformatoptions/mergepastedlists/) { get; set; } | Obtient ou définit une valeur booléenne qui spécifie si les listes collées seront fusionnées avec les listes environnantes. La valeur par défaut est`faux` . |
| [SmartStyleBehavior](../../aspose.words/importformatoptions/smartstylebehavior/) { get; set; } | Obtient ou définit une valeur booléenne qui spécifie comment les styles seront importés lorsqu'ils ont des noms identiques dans les documents source et de destination. La valeur par défaut est`faux` . |

### Exemples

Montre comment résoudre les styles en double lors de l'insertion de documents.

```csharp
Document dstDoc = new Document();
DocumentBuilder builder = new DocumentBuilder(dstDoc);

Style myStyle = builder.Document.Styles.Add(StyleType.Paragraph, "MyStyle");
myStyle.Font.Size = 14;
myStyle.Font.Name = "Courier New";
myStyle.Font.Color = Color.Blue;

builder.ParagraphFormat.StyleName = myStyle.Name;
builder.Writeln("Hello world!");

// Clone le document et édite le style "MyStyle" du clone, de sorte qu'il soit d'une couleur différente de celle de l'original.
// Si nous insérons le clone dans le document d'origine, les deux styles portant le même nom provoqueront un conflit.
Document srcDoc = dstDoc.Clone();
srcDoc.Styles["MyStyle"].Font.Color = Color.Red;

// Lorsque nous activons SmartStyleBehavior et utilisons le mode de format d'importation KeepSourceFormatting,
// Aspose.Words résoudra les conflits de style en convertissant les styles du document source.
// avec les mêmes noms que les styles de destination dans les attributs de paragraphe directs.
ImportFormatOptions options = new ImportFormatOptions();
options.SmartStyleBehavior = true;

builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting, options);

dstDoc.Save(ArtifactsDir + "DocumentBuilder.SmartStyleBehavior.docx");
```

### Voir également

* espace de noms [Aspose.Words](../../aspose.words/)
* Assemblée [Aspose.Words](../../)


