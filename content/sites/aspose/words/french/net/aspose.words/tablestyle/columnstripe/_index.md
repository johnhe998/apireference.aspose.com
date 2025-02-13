---
title: TableStyle.ColumnStripe
second_title: Référence de l'API Aspose.Words pour .NET
description: TableStyle propriété. Obtient ou définit un nombre de colonnes à inclure dans la bande lorsque le style spécifie une bande de colonnes paires/impaires.
type: docs
weight: 70
url: /fr/net/aspose.words/tablestyle/columnstripe/
---
## TableStyle.ColumnStripe property

Obtient ou définit un nombre de colonnes à inclure dans la bande lorsque le style spécifie une bande de colonnes paires/impaires.

```csharp
public int ColumnStripe { get; set; }
```

### Exemples

Montre comment créer des styles de tableau conditionnels qui alternent entre les lignes.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// On peut configurer un style conditionnel d'un tableau pour appliquer une couleur différente à la ligne/colonne,
// selon que la ligne/colonne est paire ou impaire, créant un motif de couleur alterné.
// On peut aussi appliquer un nombre n au banding ligne/colonne,
// ce qui signifie que la couleur alterne toutes les n lignes/colonnes au lieu d'une.
// Crée un tableau où les colonnes et les lignes simples regrouperont les colonnes par trois.
Table table = builder.StartTable();
for (int i = 0; i < 15; i++)
{
    for (int j = 0; j < 4; j++)
    {
        builder.InsertCell();
        builder.Writeln($"{(j % 2 == 0 ? "Even" : "Odd")} column.");
        builder.Write($"Row banding {(i % 3 == 0 ? "start" : "continuation")}.");
    }
    builder.EndRow();
}
builder.EndTable();

// Applique un style de ligne à toutes les bordures du tableau.
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.Color = Color.Black;
tableStyle.Borders.LineStyle = LineStyle.Double;

// Définit les deux couleurs, qui alterneront toutes les 3 lignes.
tableStyle.RowStripe = 3;
tableStyle.ConditionalStyles[ConditionalStyleType.OddRowBanding].Shading.BackgroundPatternColor = Color.LightBlue;
tableStyle.ConditionalStyles[ConditionalStyleType.EvenRowBanding].Shading.BackgroundPatternColor = Color.LightCyan;

// Définissez une couleur à appliquer à chaque colonne paire, qui remplacera toute coloration de ligne personnalisée.
tableStyle.ColumnStripe = 1;
tableStyle.ConditionalStyles[ConditionalStyleType.EvenColumnBanding].Shading.BackgroundPatternColor = Color.LightSalmon;

table.Style = tableStyle;

// La propriété "StyleOptions" active les bandes de ligne par défaut.
Assert.AreEqual(TableStyleOptions.FirstRow | TableStyleOptions.FirstColumn | TableStyleOptions.RowBands,
    table.StyleOptions);

// Utilisez également la propriété "StyleOptions" pour activer les bandes de colonnes.
table.StyleOptions = table.StyleOptions | TableStyleOptions.ColumnBands;

doc.Save(ArtifactsDir + "Table.AlternatingRowStyles.docx");
```

### Voir également

* class [TableStyle](../)
* espace de noms [Aspose.Words](../../tablestyle/)
* Assemblée [Aspose.Words](../../../)


