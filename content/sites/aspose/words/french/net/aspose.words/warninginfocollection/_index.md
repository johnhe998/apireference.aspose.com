---
title: Class WarningInfoCollection
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.WarningInfoCollection classe. Représente une collection typée deWarningInfo objets.
type: docs
weight: 6330
url: /fr/net/aspose.words/warninginfocollection/
---
## WarningInfoCollection class

Représente une collection typée de[`WarningInfo`](../warninginfo/) objets.

```csharp
public class WarningInfoCollection : IEnumerable<WarningInfo>, IWarningCallback
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [WarningInfoCollection](warninginfocollection/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [Count](../../aspose.words/warninginfocollection/count/) { get; } | Obtient le nombre d'éléments contenus dans la collection. |
| [Item](../../aspose.words/warninginfocollection/item/) { get; } | Obtient un élément à l'index spécifié. |

## Méthodes

| Nom | La description |
| --- | --- |
| [Clear](../../aspose.words/warninginfocollection/clear/)() | Supprime tous les éléments de la collection. |
| [GetEnumerator](../../aspose.words/warninginfocollection/getenumerator/)() | Renvoie un objet énumérateur qui peut être utilisé pour itérer sur tous les éléments de la collection. |
| [Warning](../../aspose.words/warninginfocollection/warning/)(WarningInfo) | Implémente le[`IWarningCallback`](../iwarningcallback/) interface. Ajoute un avertissement à cette collection. |

### Remarques

Vous pouvez utiliser cet objet de collection comme la forme la plus simple de[`IWarningCallback`](../iwarningcallback/)implémentation pour rassembler tous les avertissements générés par Aspose.Words lors d'une opération de chargement ou de sauvegarde. Créez une instance de cette classe et affectez-la au[`WarningCallback`](../../aspose.words.loading/loadoptions/warningcallback/) ou[`WarningCallback`](../documentbase/warningcallback/) propriété.

### Exemples

Montre comment définir la propriété pour rechercher la correspondance la plus proche pour une police manquante à partir des sources de polices disponibles.

```csharp
[Test]
public void EnableFontSubstitution()
{
    // Ouvre un document contenant du texte formaté avec une police qui n'existe dans aucune de nos sources de polices.
    Document doc = new Document(MyDir + "Missing font.docx");

    // Affecte un rappel pour gérer les avertissements de substitution de police.
    HandleDocumentSubstitutionWarnings substitutionWarningHandler = new HandleDocumentSubstitutionWarnings();
    doc.WarningCallback = substitutionWarningHandler;

    // Définir un nom de police par défaut et activer la substitution de police.
    FontSettings fontSettings = new FontSettings();
    fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
    ;
    fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = true;

    // Nous recevrons un avertissement de substitution de police si nous enregistrons un document avec une police manquante.
    doc.FontSettings = fontSettings;
    doc.Save(ArtifactsDir + "FontSettings.EnableFontSubstitution.pdf");

    using (IEnumerator<WarningInfo> warnings = substitutionWarningHandler.FontWarnings.GetEnumerator())
        while (warnings.MoveNext())
            Console.WriteLine(warnings.Current.Description);

    // Nous pouvons également vérifier les avertissements dans la collection et les effacer.
    Assert.AreEqual(WarningSource.Layout, substitutionWarningHandler.FontWarnings[0].Source);
    Assert.AreEqual(
        "Font '28 Days Later' has not been found. Using 'Calibri' font instead. Reason: alternative name from document.",
        substitutionWarningHandler.FontWarnings[0].Description);

    substitutionWarningHandler.FontWarnings.Clear();

    Assert.That(substitutionWarningHandler.FontWarnings, Is.Empty);
}

public class HandleDocumentSubstitutionWarnings : IWarningCallback
{
    /// <summary>
    /// Appelé chaque fois qu'un avertissement se produit lors du chargement/sauvegarde.
    /// </summary>
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

### Voir également

* class [WarningInfo](../warninginfo/)
* interface [IWarningCallback](../iwarningcallback/)
* espace de noms [Aspose.Words](../../aspose.words/)
* Assemblée [Aspose.Words](../../)


