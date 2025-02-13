---
title: StructuredDocumentTag.DateDisplayLocale
second_title: Référence de l'API Aspose.Words pour .NET
description: StructuredDocumentTag propriété. Permet de définir/obtenir le format de langue pour la date affichée dans ce TDS .
type: docs
weight: 100
url: /fr/net/aspose.words.markup/structureddocumenttag/datedisplaylocale/
---
## StructuredDocumentTag.DateDisplayLocale property

Permet de définir/obtenir le format de langue pour la date affichée dans ce **TDS** .

```csharp
public int DateDisplayLocale { get; set; }
```

### Remarques

L'accès à cette propriété ne fonctionnera que pourDate Type SDT.

Pour tous les autres types de SDT, une exception se produira.

### Exemples

Montre comment inviter l'utilisateur à saisir une date avec une balise de document structurée.

```csharp
Document doc = new Document();

// Insère une balise de document structurée qui invite l'utilisateur à saisir une date.
// Dans Microsoft Word, cet élément est appelé "Contrôle de contenu du sélecteur de date".
// Lorsque nous cliquons sur la flèche à l'extrémité droite de cette balise dans Microsoft Word,
// nous verrons une fenêtre contextuelle sous la forme d'un calendrier cliquable.
// Nous pouvons utiliser ce popup pour sélectionner une date que la balise affichera.
StructuredDocumentTag sdtDate = new StructuredDocumentTag(doc, SdtType.Date, MarkupLevel.Inline);

// Affiche la date, selon les paramètres régionaux de l'arabe saoudien.
sdtDate.DateDisplayLocale = CultureInfo.GetCultureInfo("ar-SA").LCID;

// Définit le format avec lequel afficher la date.
sdtDate.DateDisplayFormat = "dd MMMM, yyyy";
sdtDate.DateStorageFormat = SdtDateStorageFormat.DateTime;

// Affiche la date selon le calendrier Hijri.
sdtDate.CalendarType = SdtCalendarType.Hijri;

// Avant que l'utilisateur ne choisisse une date dans Microsoft Word, la balise affichera le texte "Cliquez ici pour entrer une date.".
// En fonction du calendrier de la balise, définissez la propriété "FullDate" pour que la balise affiche une date par défaut.
sdtDate.FullDate = new DateTime(1440, 10, 20);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(sdtDate);

doc.Save(ArtifactsDir + "StructuredDocumentTag.Date.docx");
```

### Voir également

* class [StructuredDocumentTag](../)
* espace de noms [Aspose.Words.Markup](../../structureddocumenttag/)
* Assemblée [Aspose.Words](../../../)


