---
title: FieldAutoNumLgl.RemoveTrailingPeriod
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldAutoNumLgl propriété. Obtient ou définit sil faut afficher le nombre sans point final.
type: docs
weight: 20
url: /fr/net/aspose.words.fields/fieldautonumlgl/removetrailingperiod/
---
## FieldAutoNumLgl.RemoveTrailingPeriod property

Obtient ou définit s'il faut afficher le nombre sans point final.

```csharp
public bool RemoveTrailingPeriod { get; set; }
```

### Exemples

Montre comment organiser un document à l'aide des champs AUTONUMLGL.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    const string fillerText = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. " +
                              "\nUt enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. ";

    // Les champs AUTONUMLGL affichent un nombre qui s'incrémente à chaque champ AUTONUMLGL dans son niveau d'en-tête actuel.
    // Ces champs maintiennent un décompte séparé pour chaque niveau de titre,
     // et chaque champ affiche également le champ AUTONUMLGL compte pour tous les niveaux de titre en dessous du sien.
    // Changer le décompte pour n'importe quel niveau de titre réinitialise les décomptes pour tous les niveaux au-dessus de ce niveau à 1.
    // Cela nous permet d'organiser notre document sous la forme d'une liste sommaire.
    // Il s'agit du premier champ AUTONUMLGL au niveau d'en-tête 1, affichant "1". dans le document.
    InsertNumberedClause(builder, "\tHeading 1", fillerText, StyleIdentifier.Heading1);

    // Il s'agit du deuxième champ AUTONUMLGL au niveau d'en-tête 1, il affichera donc "2.".
    InsertNumberedClause(builder, "\tHeading 2", fillerText, StyleIdentifier.Heading1);

    // Il s'agit du premier champ AUTONUMLGL au niveau d'en-tête 2,
    // et le compte AUTONUMLGL pour le niveau de titre en dessous est "2", donc il affichera "2.1.".
    InsertNumberedClause(builder, "\tHeading 3", fillerText, StyleIdentifier.Heading2);

     // Il s'agit du premier champ AUTONUMLGL au niveau d'en-tête 3.
    // Fonctionnant de la même manière que le champ ci-dessus, il affichera "2.1.1.".
    InsertNumberedClause(builder, "\tHeading 4", fillerText, StyleIdentifier.Heading3);

    // Ce champ est au niveau d'en-tête de 2, et son compte AUTONUMLGL respectif est à 2, donc le champ affichera "2.2.".
    InsertNumberedClause(builder, "\tHeading 5", fillerText, StyleIdentifier.Heading2);

    // Incrémentation du compteur AUTONUMLGL pour un niveau de titre inférieur à celui-ci
    // a réinitialisé le décompte pour ce niveau afin que ce champ affiche "2.2.1.".
    InsertNumberedClause(builder, "\tHeading 6", fillerText, StyleIdentifier.Heading3);

    foreach (FieldAutoNumLgl field in doc.Range.Fields.Where(f => f.Type == FieldType.FieldAutoNumLegal))
    {
        // Le caractère séparateur, qui apparaît dans le champ result immédiatement après le nombre,
        // est un point par défaut. Si nous laissons cette propriété nulle,
        // notre dernier champ AUTONUMLGL affichera "2.2.1." dans le document.
        Assert.IsNull(field.SeparatorCharacter);

        // Définition d'un caractère de séparation personnalisé et suppression du point de fin
        // changera l'apparence de ce champ de "2.2.1." à "2:2:1".
        // Nous appliquerons ceci à tous les champs que nous avons créés.
        field.SeparatorCharacter = ":";
        field.RemoveTrailingPeriod = true;
        Assert.AreEqual(" AUTONUMLGL  \\s : \\e", field.GetFieldCode());
    }

    doc.Save(ArtifactsDir + "Field.AUTONUMLGL.docx");

/// <summary>
/// Utilise un générateur de document pour insérer une clause numérotée par un champ AUTONUMLGL.
/// </summary>
private static void InsertNumberedClause(DocumentBuilder builder, string heading, string contents, StyleIdentifier headingStyle)
{
    builder.InsertField(FieldType.FieldAutoNumLegal, true);
    builder.CurrentParagraph.ParagraphFormat.StyleIdentifier = headingStyle;
    builder.Writeln(heading);

    // Ce texte appartiendra au champ légal auto num au-dessus.
    // Il s'effondrera lorsque nous cliquerons sur la flèche à côté du champ AUTONUMLGL correspondant dans Microsoft Word.
    builder.CurrentParagraph.ParagraphFormat.StyleIdentifier = StyleIdentifier.BodyText;
    builder.Writeln(contents);
}
```

### Voir également

* class [FieldAutoNumLgl](../)
* espace de noms [Aspose.Words.Fields](../../fieldautonumlgl/)
* Assemblée [Aspose.Words](../../../)


