---
title: PageSetup.FirstPageTray
second_title: Référence de l'API Aspose.Words pour .NET
description: PageSetup propriété. Obtient ou définit le bac à papier bac à utiliser pour la première page dune section. La valeur est spécifique à limplémentation imprimante.
type: docs
weight: 130
url: /fr/net/aspose.words/pagesetup/firstpagetray/
---
## PageSetup.FirstPageTray property

Obtient ou définit le bac à papier (bac) à utiliser pour la première page d'une section. La valeur est spécifique à l'implémentation (imprimante).

```csharp
public int FirstPageTray { get; set; }
```

### Exemples

Montre comment faire en sorte que toutes les sections d'un document utilisent le bac à papier par défaut de l'imprimante sélectionnée.

```csharp
Document doc = new Document();

// Trouve l'imprimante par défaut que nous utiliserons pour imprimer ce document.
// Vous pouvez définir une imprimante spécifique à l'aide de la propriété "PrinterName" de l'objet PrinterSettings.
PrinterSettings settings = new PrinterSettings();

// La valeur du bac à papier stockée dans les documents est spécifique à l'imprimante.
// Cela signifie que le code ci-dessous réinitialise toutes les valeurs de bac de page pour utiliser le bac par défaut actuel de l'imprimante.
// Vous pouvez énumérer PrinterSettings.PaperSources pour trouver les autres valeurs de bac à papier valides de l'imprimante sélectionnée.
foreach (Section section in doc.Sections.OfType<Section>())
{
    section.PageSetup.FirstPageTray = settings.DefaultPageSettings.PaperSource.RawKind;
    section.PageSetup.OtherPagesTray = settings.DefaultPageSettings.PaperSource.RawKind;
}
```

Explique comment configurer l'impression à l'aide de différents bacs d'imprimante pour différents formats de papier.

```csharp
Document doc = new Document();

// Trouve l'imprimante par défaut que nous utiliserons pour imprimer ce document.
// Vous pouvez définir une imprimante spécifique à l'aide de la propriété "PrinterName" de l'objet PrinterSettings.
PrinterSettings settings = new PrinterSettings();

// Il s'agit du bac que nous utiliserons pour les pages au format papier "A4".
int printerTrayForA4 = settings.PaperSources[0].RawKind;

// C'est le bac que nous utiliserons pour les pages au format papier "Letter".
int printerTrayForLetter = settings.PaperSources[1].RawKind;

// Modifiez l'objet PageSettings de cette section pour que Microsoft Word instruise l'imprimante
// pour utiliser l'un des bacs que nous avons identifiés ci-dessus, en fonction du format de papier de cette section.
foreach (Section section in doc.Sections.OfType<Section>())
{
    if (section.PageSetup.PaperSize == Aspose.Words.PaperSize.Letter)
    {
        section.PageSetup.FirstPageTray = printerTrayForLetter;
        section.PageSetup.OtherPagesTray = printerTrayForLetter;
    }
    else if (section.PageSetup.PaperSize == Aspose.Words.PaperSize.A4)
    {
        section.PageSetup.FirstPageTray = printerTrayForA4;
        section.PageSetup.OtherPagesTray = printerTrayForA4;
    }
}
```

### Voir également

* class [PageSetup](../)
* espace de noms [Aspose.Words](../../pagesetup/)
* Assemblée [Aspose.Words](../../../)


