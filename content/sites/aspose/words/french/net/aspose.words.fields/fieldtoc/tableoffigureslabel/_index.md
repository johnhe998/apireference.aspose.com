---
title: FieldToc.TableOfFiguresLabel
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldToc propriété. Obtient ou définit le nom de lidentificateur de séquence utilisé lors de la création dun tableau des illustrations.
type: docs
weight: 160
url: /fr/net/aspose.words.fields/fieldtoc/tableoffigureslabel/
---
## FieldToc.TableOfFiguresLabel property

Obtient ou définit le nom de l'identificateur de séquence utilisé lors de la création d'un tableau des illustrations.

```csharp
public string TableOfFiguresLabel { get; set; }
```

### Exemples

Montre comment remplir un champ TOC avec des entrées à l'aide des champs SEQ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Un champ TOC peut créer une entrée dans sa table des matières pour chaque champ SEQ présent dans le document.
// Chaque entrée contient le paragraphe qui inclut le champ SEQ et le numéro de page sur lequel le champ apparaît.
FieldToc fieldToc = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

// Les champs SEQ affichent un décompte qui s'incrémente à chaque champ SEQ.
// Ces champs conservent également des décomptes séparés pour chaque séquence nommée unique
// identifié par la propriété "SequenceIdentifier" du champ SEQ.
// Utilisez la propriété "TableOfFiguresLabel" pour nommer une séquence principale pour la table des matières.
// Désormais, cette table des matières créera uniquement des entrées à partir des champs SEQ avec leur "SequenceIdentifier" défini sur "MySequence".
fieldToc.TableOfFiguresLabel = "MySequence";

// Nous pouvons nommer une autre séquence de champs SEQ dans la propriété "PrefixedSequenceIdentifier".
 // Les champs SEQ de cette séquence de préfixes ne créeront pas d'entrées TOC.
// Chaque entrée de table des matières créée à partir d'un champ SEQ de séquence principale affichera désormais également le nombre qui
// la séquence de préfixe est actuellement activée dans le champ SEQ de séquence primaire qui a effectué l'entrée.
fieldToc.PrefixedSequenceIdentifier = "PrefixSequence";

// Chaque entrée TOC affichera le nombre de séquences de préfixes immédiatement à gauche
// du numéro de page sur lequel apparaît le champ SEQ de la séquence principale.
// Nous pouvons spécifier un séparateur personnalisé qui apparaîtra entre ces deux nombres.
fieldToc.SequenceSeparator = ">";

Assert.AreEqual(" TOC  \\c MySequence \\s PrefixSequence \\d >", fieldToc.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);

// Il existe deux manières d'utiliser les champs SEQ pour remplir cette table des matières.
// 1 - Insertion d'un champ SEQ appartenant à la séquence de préfixe de la TOC :
// Ce champ incrémentera le nombre de séquences SEQ pour la "PrefixSequence" de 1.
// Comme ce champ n'appartient pas à la séquence principale identifiée
// par la propriété "TableOfFiguresLabel" de la table des matières, elle n'apparaîtra pas comme une entrée.
FieldSeq fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "PrefixSequence";
builder.InsertParagraph();

Assert.AreEqual(" SEQ  PrefixSequence", fieldSeq.GetFieldCode());

// 2 - Insertion d'un champ SEQ appartenant à la séquence principale de la TOC :
// Ce champ SEQ créera une entrée dans la table des matières.
// L'entrée TOC contiendra le paragraphe dans lequel se trouve le champ SEQ et le numéro de la page sur laquelle il apparaît.
// Cette entrée affichera également le décompte auquel se trouve actuellement la séquence de préfixes,
// séparé du numéro de page par la valeur de la propriété SeqenceSeparator de la table des matières.
// Le décompte "PrefixSequence" est à 1, ce champ SEQ de la séquence principale est en page 2,
// et le séparateur est ">", donc l'entrée affichera "1>2".
builder.Write("First TOC entry, MySequence #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";

Assert.AreEqual(" SEQ  MySequence", fieldSeq.GetFieldCode());

// Insérez une page, avancez la séquence de préfixes de 2 et insérez un champ SEQ pour créer une entrée TOC par la suite.
// La séquence du préfixe est maintenant à 2, et le champ SEQ de la séquence principale est à la page 3,
// donc l'entrée TOC affichera "2>3" à son nombre de pages.
builder.InsertBreak(BreakType.PageBreak);
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "PrefixSequence";
builder.InsertParagraph();
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
builder.Write("Second TOC entry, MySequence #");
fieldSeq.SequenceIdentifier = "MySequence";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.TOC.SEQ.docx");
```

### Voir également

* class [FieldToc](../)
* espace de noms [Aspose.Words.Fields](../../fieldtoc/)
* Assemblée [Aspose.Words](../../../)


