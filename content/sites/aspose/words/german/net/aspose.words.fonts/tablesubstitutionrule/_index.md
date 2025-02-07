---
title: Class TableSubstitutionRule
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Fonts.TableSubstitutionRule klas. Ersetzungsregel für Tabellenschriftarten.
type: docs
weight: 2880
url: /de/net/aspose.words.fonts/tablesubstitutionrule/
---
## TableSubstitutionRule class

Ersetzungsregel für Tabellenschriftarten.

```csharp
public class TableSubstitutionRule : FontSubstitutionRule
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| virtual [Enabled](../../aspose.words.fonts/fontsubstitutionrule/enabled/) { get; set; } | Gibt an, ob die Regel aktiviert ist oder nicht. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [AddSubstitutes](../../aspose.words.fonts/tablesubstitutionrule/addsubstitutes/)(string, params string[]) | Fügt Ersatzschriftnamen für den angegebenen Originalschriftnamen hinzu. |
| [GetSubstitutes](../../aspose.words.fonts/tablesubstitutionrule/getsubstitutes/)(string) | Gibt ein Array zurück, das Ersatzschriftnamen für den angegebenen ursprünglichen Schriftartnamen enthält. |
| [Load](../../aspose.words.fonts/tablesubstitutionrule/load/#load)(Stream) | Lädt Tabellenersetzungseinstellungen aus dem XML-Stream. |
| [Load](../../aspose.words.fonts/tablesubstitutionrule/load/#load_1)(string) | Lädt Tabellenersetzungseinstellungen aus der XML-Datei. |
| [LoadAndroidSettings](../../aspose.words.fonts/tablesubstitutionrule/loadandroidsettings/)() | Lädt vordefinierte Tabellenersetzungseinstellungen für die Linux-Plattform. |
| [LoadLinuxSettings](../../aspose.words.fonts/tablesubstitutionrule/loadlinuxsettings/)() | Lädt vordefinierte Tabellenersetzungseinstellungen für die Linux-Plattform. |
| [LoadWindowsSettings](../../aspose.words.fonts/tablesubstitutionrule/loadwindowssettings/)() | Lädt vordefinierte Tabellenersetzungseinstellungen für die Windows-Plattform. |
| [Save](../../aspose.words.fonts/tablesubstitutionrule/save/#save)(Stream) | Speichert die aktuellen Tabellenersetzungseinstellungen im Stream. |
| [Save](../../aspose.words.fonts/tablesubstitutionrule/save/#save_1)(string) | Speichert die aktuellen Tabellenersetzungseinstellungen in einer Datei. |
| [SetSubstitutes](../../aspose.words.fonts/tablesubstitutionrule/setsubstitutes/)(string, params string[]) | Ersatzschriftnamen für den angegebenen Originalschriftnamen überschreiben. |

### Bemerkungen

Diese Regel definiert die Liste der Ersatzzeichensatznamen, die verwendet werden sollen, wenn der Originalzeichensatz nicht verfügbar ist. Ersatzzeichensätze werden auf den Zeichensatznamen und die geprüft[`AltName`](../fontinfo/altname/) (falls vorhanden).

### Beispiele

Zeigt, wie auf Schriftartersetzungstabellen für Windows und Linux zugegriffen wird.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Erstellen Sie eine neue Tabellenersetzungsregel und laden Sie die standardmäßige Schriftartenersetzungstabelle von Microsoft Windows.
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;
tableSubstitutionRule.LoadWindowsSettings();

// In Windows ist der Standardersatz für die Schriftart "Times New Roman CE" "Times New Roman".
Assert.AreEqual(new[] {"Times New Roman"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Wir können die Tabelle in Form eines XML-Dokuments speichern.
tableSubstitutionRule.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Windows.xml");

// Linux hat seine eigene Substitutionstabelle.
// Es gibt mehrere Ersatzschriftarten für "Times New Roman CE".
// Wenn der erste Ersatz "FreeSerif" ebenfalls nicht verfügbar ist,
// Diese Regel durchläuft die anderen im Array, bis sie eine verfügbare findet.
tableSubstitutionRule.LoadLinuxSettings();
Assert.AreEqual(new[] {"FreeSerif", "Liberation Serif", "DejaVu Serif"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Speichern Sie die Linux-Ersetzungstabelle in Form eines XML-Dokuments mithilfe eines Streams.
using (FileStream fileStream = new FileStream(ArtifactsDir + "FontSettings.TableSubstitutionRule.Linux.xml",
    FileMode.Create))
{
    tableSubstitutionRule.Save(fileStream);
}
```

### Siehe auch

* class [FontSubstitutionRule](../fontsubstitutionrule/)
* namensraum [Aspose.Words.Fonts](../../aspose.words.fonts/)
* Montage [Aspose.Words](../../)


