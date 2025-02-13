---
title: ImportFormatOptions.SmartStyleBehavior
second_title: Référence de l'API Aspose.Words pour .NET
description: ImportFormatOptions propriété. Obtient ou définit une valeur booléenne qui spécifie comment les styles seront importés lorsquils ont des noms identiques dans les documents source et de destination. La valeur par défaut estfaux .
type: docs
weight: 70
url: /fr/net/aspose.words/importformatoptions/smartstylebehavior/
---
## ImportFormatOptions.SmartStyleBehavior property

Obtient ou définit une valeur booléenne qui spécifie comment les styles seront importés lorsqu'ils ont des noms identiques dans les documents source et de destination. La valeur par défaut est`faux` .

```csharp
public bool SmartStyleBehavior { get; set; }
```

### Remarques

Lorsque cette option est **activé** , le style source sera développé en attributs directs dans le document de destination a , siKeepSourceFormatting le mode d'importation est utilisé.

Lorsque cette option est **désactivé**, le style source ne sera développé que s'il est numéroté. Les attributs de destination existants ne seront pas remplacés, y compris les listes.

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

* class [ImportFormatOptions](../)
* espace de noms [Aspose.Words](../../importformatoptions/)
* Assemblée [Aspose.Words](../../../)


