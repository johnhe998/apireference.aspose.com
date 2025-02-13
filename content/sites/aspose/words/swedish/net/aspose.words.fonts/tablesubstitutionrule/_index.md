---
title: Class TableSubstitutionRule
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Fonts.TableSubstitutionRule klass. Regel för ersättning av tabellteckensnitt.
type: docs
weight: 2880
url: /sv/net/aspose.words.fonts/tablesubstitutionrule/
---
## TableSubstitutionRule class

Regel för ersättning av tabellteckensnitt.

```csharp
public class TableSubstitutionRule : FontSubstitutionRule
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| virtual [Enabled](../../aspose.words.fonts/fontsubstitutionrule/enabled/) { get; set; } | Anger om regeln är aktiverad eller inte. |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [AddSubstitutes](../../aspose.words.fonts/tablesubstitutionrule/addsubstitutes/)(string, params string[]) | Lägger till ersättande teckensnittsnamn för det ursprungliga teckensnittsnamnet. |
| [GetSubstitutes](../../aspose.words.fonts/tablesubstitutionrule/getsubstitutes/)(string) | Returnerar array som innehåller ersättande teckensnittsnamn för det angivna ursprungliga teckensnittsnamnet. |
| [Load](../../aspose.words.fonts/tablesubstitutionrule/load/#load)(Stream) | Laddar inställningar för tabellersättning från XML-ström. |
| [Load](../../aspose.words.fonts/tablesubstitutionrule/load/#load_1)(string) | Laddar tabellersättningsinställningar från XML-fil. |
| [LoadAndroidSettings](../../aspose.words.fonts/tablesubstitutionrule/loadandroidsettings/)() | Laddar fördefinierade tabellersättningsinställningar för Linux-plattformen. |
| [LoadLinuxSettings](../../aspose.words.fonts/tablesubstitutionrule/loadlinuxsettings/)() | Laddar fördefinierade tabellersättningsinställningar för Linux-plattformen. |
| [LoadWindowsSettings](../../aspose.words.fonts/tablesubstitutionrule/loadwindowssettings/)() | Laddar fördefinierade tabellersättningsinställningar för Windows-plattformen. |
| [Save](../../aspose.words.fonts/tablesubstitutionrule/save/#save)(Stream) | Sparar de aktuella inställningarna för tabellersättning för att streama. |
| [Save](../../aspose.words.fonts/tablesubstitutionrule/save/#save_1)(string) | Sparar de aktuella inställningarna för tabellersättning i filen. |
| [SetSubstitutes](../../aspose.words.fonts/tablesubstitutionrule/setsubstitutes/)(string, params string[]) | Åsidosätt ersättande teckensnittsnamn för det ursprungliga teckensnittsnamnet. |

### Anmärkningar

Den här regeln definierar listan över ersättningsteckensnittsnamn som ska användas om det ursprungliga teckensnittet inte är tillgängligt. Ersättningar kommer att kontrolleras för teckensnittsnamnet och[`AltName`](../fontinfo/altname/) (om någon).

### Exempel

Visar hur du får åtkomst till teckensnittsersättningstabeller för Windows och Linux.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Skapa en ny regel för tabellersättning och ladda standardtabellen för Microsoft Windows-teckensnittsersättning.
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;
tableSubstitutionRule.LoadWindowsSettings();

// I Windows är standardersättningen för "Times New Roman CE"-teckensnittet "Times New Roman".
Assert.AreEqual(new[] {"Times New Roman"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Vi kan spara tabellen i form av ett XML-dokument.
tableSubstitutionRule.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Windows.xml");

// Linux har sin egen ersättningstabell.
// Det finns flera ersättningsteckensnitt för "Times New Roman CE".
// Om den första ersättningen, "FreeSerif" inte heller är tillgänglig,
// denna regel kommer att cykla genom de andra i arrayen tills den hittar en tillgänglig.
tableSubstitutionRule.LoadLinuxSettings();
Assert.AreEqual(new[] {"FreeSerif", "Liberation Serif", "DejaVu Serif"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Spara Linux-ersättningstabellen i form av ett XML-dokument med hjälp av en ström.
using (FileStream fileStream = new FileStream(ArtifactsDir + "FontSettings.TableSubstitutionRule.Linux.xml",
    FileMode.Create))
{
    tableSubstitutionRule.Save(fileStream);
}
```

### Se även

* class [FontSubstitutionRule](../fontsubstitutionrule/)
* namnutrymme [Aspose.Words.Fonts](../../aspose.words.fonts/)
* hopsättning [Aspose.Words](../../)


