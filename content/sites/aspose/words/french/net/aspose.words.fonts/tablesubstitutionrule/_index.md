---
title: Class TableSubstitutionRule
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Fonts.TableSubstitutionRule classe. Règle de substitution de police de tableau.
type: docs
weight: 2880
url: /fr/net/aspose.words.fonts/tablesubstitutionrule/
---
## TableSubstitutionRule class

Règle de substitution de police de tableau.

```csharp
public class TableSubstitutionRule : FontSubstitutionRule
```

## Propriétés

| Nom | La description |
| --- | --- |
| virtual [Enabled](../../aspose.words.fonts/fontsubstitutionrule/enabled/) { get; set; } | Spécifie si la règle est activée ou non. |

## Méthodes

| Nom | La description |
| --- | --- |
| [AddSubstitutes](../../aspose.words.fonts/tablesubstitutionrule/addsubstitutes/)(string, params string[]) | Ajoute des noms de police de remplacement pour le nom de police d'origine donné. |
| [GetSubstitutes](../../aspose.words.fonts/tablesubstitutionrule/getsubstitutes/)(string) | Renvoie un tableau contenant des noms de police de remplacement pour le nom de police d'origine spécifié. |
| [Load](../../aspose.words.fonts/tablesubstitutionrule/load/#load)(Stream) | Charge les paramètres de substitution de table à partir du flux XML. |
| [Load](../../aspose.words.fonts/tablesubstitutionrule/load/#load_1)(string) | Charge les paramètres de substitution de table à partir du fichier XML. |
| [LoadAndroidSettings](../../aspose.words.fonts/tablesubstitutionrule/loadandroidsettings/)() | Charge les paramètres de substitution de table prédéfinis pour la plate-forme Linux. |
| [LoadLinuxSettings](../../aspose.words.fonts/tablesubstitutionrule/loadlinuxsettings/)() | Charge les paramètres de substitution de table prédéfinis pour la plate-forme Linux. |
| [LoadWindowsSettings](../../aspose.words.fonts/tablesubstitutionrule/loadwindowssettings/)() | Charge les paramètres de substitution de table prédéfinis pour la plate-forme Windows. |
| [Save](../../aspose.words.fonts/tablesubstitutionrule/save/#save)(Stream) | Enregistre les paramètres de substitution de table actuels dans stream. |
| [Save](../../aspose.words.fonts/tablesubstitutionrule/save/#save_1)(string) | Enregistre les paramètres de substitution de table actuels dans le fichier. |
| [SetSubstitutes](../../aspose.words.fonts/tablesubstitutionrule/setsubstitutes/)(string, params string[]) | Remplacer les noms de police de remplacement pour le nom de police d'origine donné. |

### Remarques

Cette règle définit la liste des noms de polices de substitution à utiliser si la police d'origine n'est pas disponible. Les substitutions seront vérifiées pour le nom de la police et le[`AltName`](../fontinfo/altname/) (le cas échéant).

### Exemples

Montre comment accéder aux tables de substitution de polices pour Windows et Linux.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Crée une nouvelle règle de substitution de table et charge la table de substitution de police Microsoft Windows par défaut.
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;
tableSubstitutionRule.LoadWindowsSettings();

// Sous Windows, le substitut par défaut de la police "Times New Roman CE" est "Times New Roman".
Assert.AreEqual(new[] {"Times New Roman"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Nous pouvons enregistrer le tableau sous la forme d'un document XML.
tableSubstitutionRule.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Windows.xml");

// Linux a sa propre table de substitution.
// Il existe plusieurs polices de substitution pour "Times New Roman CE".
// Si le premier substitut, "FreeSerif" est également indisponible,
// cette règle parcourra les autres dans le tableau jusqu'à ce qu'elle en trouve une disponible.
tableSubstitutionRule.LoadLinuxSettings();
Assert.AreEqual(new[] {"FreeSerif", "Liberation Serif", "DejaVu Serif"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Enregistre la table de substitution Linux sous la forme d'un document XML à l'aide d'un flux.
using (FileStream fileStream = new FileStream(ArtifactsDir + "FontSettings.TableSubstitutionRule.Linux.xml",
    FileMode.Create))
{
    tableSubstitutionRule.Save(fileStream);
}
```

### Voir également

* class [FontSubstitutionRule](../fontsubstitutionrule/)
* espace de noms [Aspose.Words.Fonts](../../aspose.words.fonts/)
* Assemblée [Aspose.Words](../../)


