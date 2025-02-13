---
title: FieldSeq.InsertNextNumber
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldSeq propriété. Obtient ou définit sil faut insérer le numéro de séquence suivant pour lélément spécifié.
type: docs
weight: 30
url: /fr/net/aspose.words.fields/fieldseq/insertnextnumber/
---
## FieldSeq.InsertNextNumber property

Obtient ou définit s'il faut insérer le numéro de séquence suivant pour l'élément spécifié.

```csharp
public bool InsertNextNumber { get; set; }
```

### Exemples

Montre créer une numérotation à l'aide des champs SEQ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Les champs SEQ affichent un décompte qui s'incrémente à chaque champ SEQ.
// Ces champs conservent également des décomptes séparés pour chaque séquence nommée unique
// identifié par la propriété "SequenceIdentifier" du champ SEQ.
// Insère un champ SEQ qui affichera la valeur de comptage actuelle de "MaSéquence",
// après avoir utilisé la propriété "ResetNumber" pour la définir sur 100.
builder.Write("#");
FieldSeq fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.ResetNumber = "100";
fieldSeq.Update();

Assert.AreEqual(" SEQ  MySequence \\r 100", fieldSeq.GetFieldCode());
Assert.AreEqual("100", fieldSeq.Result);

// Affiche le numéro suivant dans cette séquence avec un autre champ SEQ.
builder.Write(", #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.Update();

Assert.AreEqual("101", fieldSeq.Result);

// Insère un titre de niveau 1.
builder.InsertBreak(BreakType.ParagraphBreak);
builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("This level 1 heading will reset MySequence to 1");
builder.ParagraphFormat.Style = doc.Styles["Normal"];

// Insérez un autre champ SEQ de la même séquence et configurez-le pour réinitialiser le décompte à chaque en-tête avec 1.
builder.Write("\n#");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.ResetHeadingLevel = "1";
fieldSeq.Update();

// L'en-tête ci-dessus est un en-tête de niveau 1, donc le décompte de cette séquence est réinitialisé à 1.
Assert.AreEqual(" SEQ  MySequence \\s 1", fieldSeq.GetFieldCode());
Assert.AreEqual("1", fieldSeq.Result);

// Passe au numéro suivant de cette séquence.
builder.Write(", #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.InsertNextNumber = true;
fieldSeq.Update();

Assert.AreEqual(" SEQ  MySequence \\n", fieldSeq.GetFieldCode());
Assert.AreEqual("2", fieldSeq.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.SEQ.ResetNumbering.docx");
```

### Voir également

* class [FieldSeq](../)
* espace de noms [Aspose.Words.Fields](../../fieldseq/)
* Assemblée [Aspose.Words](../../../)


