---
title: ListLevel.IsLegal
second_title: Référence de l'API Aspose.Words pour .NET
description: ListLevel propriété. Vrai si le niveau transforme tous les nombres hérités en arabe faux sil conserve leur style de nombre.
type: docs
weight: 50
url: /fr/net/aspose.words.lists/listlevel/islegal/
---
## ListLevel.IsLegal property

Vrai si le niveau transforme tous les nombres hérités en arabe, faux s'il conserve leur style de nombre.

```csharp
public bool IsLegal { get; set; }
```

### Exemples

Affiche des méthodes avancées de personnalisation des étiquettes de liste.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Une liste nous permet d'organiser et de décorer des ensembles de paragraphes avec des symboles de préfixe et des retraits.
// Nous pouvons créer des listes imbriquées en augmentant le niveau d'indentation. 
// Nous pouvons commencer et terminer une liste en utilisant la propriété "ListFormat" d'un générateur de document. 
// Chaque paragraphe que nous ajoutons entre le début et la fin d'une liste deviendra un élément de la liste.
List list = doc.Lists.Add(ListTemplate.NumberDefault);

// Les étiquettes de niveau 1 seront formatées selon le style de paragraphe "Titre 1" et auront un préfixe.
// Celles-ci ressembleront à "Appendix A", "Appendix B"...
list.ListLevels[0].NumberFormat = "Appendix \x0000";
list.ListLevels[0].NumberStyle = NumberStyle.UppercaseLetter;
list.ListLevels[0].LinkedStyle = doc.Styles["Heading 1"];

// Les étiquettes de niveau 2 afficheront les numéros actuels des premier et deuxième niveaux de liste et auront des zéros non significatifs.
// Si le premier niveau de liste est à 1, alors les étiquettes de liste de celles-ci ressembleront à "Section (1.01)", "Section (1.02)"...
list.ListLevels[1].NumberFormat = "Section (\x0000.\x0001)";
list.ListLevels[1].NumberStyle = NumberStyle.LeadingZero;

// Notez que le niveau supérieur utilise la numérotation en lettres majuscules.
// Nous pouvons définir la propriété "IsLegal" pour utiliser des chiffres arabes pour les niveaux de liste supérieurs.
list.ListLevels[1].IsLegal = true;
list.ListLevels[1].RestartAfterLevel = 0;

// Les étiquettes de niveau 3 seront des chiffres romains majuscules avec un préfixe et un suffixe et recommenceront à chaque élément de niveau 1 de la liste.
// Ces étiquettes de liste ressembleront à "-I-", "-II-"...
list.ListLevels[2].NumberFormat = "-\x0002-";
list.ListLevels[2].NumberStyle = NumberStyle.UppercaseRoman;
list.ListLevels[2].RestartAfterLevel = 1;

// Met les étiquettes de tous les niveaux de liste en gras.
foreach (ListLevel level in list.ListLevels)
    level.Font.Bold = true;

// Applique le formatage de la liste au paragraphe courant.
builder.ListFormat.List = list;

// Créez des éléments de liste qui afficheront nos trois niveaux de liste.
for (int n = 0; n < 2; n++)
{
    for (int i = 0; i < 3; i++)
    {
        builder.ListFormat.ListLevelNumber = i;
        builder.Writeln("Level " + i);
    }
}

builder.ListFormat.RemoveNumbers();

doc.Save(ArtifactsDir + "Lists.CreateListRestartAfterHigher.docx");
```

### Voir également

* class [ListLevel](../)
* espace de noms [Aspose.Words.Lists](../../listlevel/)
* Assemblée [Aspose.Words](../../../)


