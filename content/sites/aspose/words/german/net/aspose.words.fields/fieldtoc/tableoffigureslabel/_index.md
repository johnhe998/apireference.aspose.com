---
title: FieldToc.TableOfFiguresLabel
second_title: Aspose.Words für .NET-API-Referenz
description: FieldToc eigendom. Ruft den Namen der Sequenzkennung ab die beim Erstellen eines Abbildungsverzeichnisses verwendet wird oder legt ihn fest.
type: docs
weight: 160
url: /de/net/aspose.words.fields/fieldtoc/tableoffigureslabel/
---
## FieldToc.TableOfFiguresLabel property

Ruft den Namen der Sequenzkennung ab, die beim Erstellen eines Abbildungsverzeichnisses verwendet wird, oder legt ihn fest.

```csharp
public string TableOfFiguresLabel { get; set; }
```

### Beispiele

Zeigt, wie ein TOC-Feld mithilfe von SEQ-Feldern mit Einträgen gefüllt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ein TOC-Feld kann einen Eintrag in seinem Inhaltsverzeichnis für jedes im Dokument gefundene SEQ-Feld erstellen.
// Jeder Eintrag enthält den Absatz, der das SEQ-Feld enthält, und die Seitennummer, auf der das Feld erscheint.
FieldToc fieldToc = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

// SEQ-Felder zeigen einen Zähler an, der sich bei jedem SEQ-Feld erhöht.
// Diese Felder verwalten auch separate Zählwerte für jede eindeutig benannte Sequenz
// identifiziert durch die "SequenceIdentifier"-Eigenschaft des SEQ-Felds.
// Verwenden Sie die Eigenschaft "TableOfFiguresLabel", um eine Hauptsequenz für das Inhaltsverzeichnis zu benennen.
// Jetzt erstellt dieses Inhaltsverzeichnis nur Einträge aus SEQ-Feldern, deren "SequenceIdentifier" auf "MySequence" gesetzt ist.
fieldToc.TableOfFiguresLabel = "MySequence";

// Wir können in der Eigenschaft "PrefixedSequenceIdentifier" eine andere SEQ-Feldsequenz benennen.
 // SEQ-Felder aus dieser Präfixsequenz erstellen keine TOC-Einträge.
// Jeder TOC-Eintrag, der aus einem SEQ-Feld der Hauptsequenz erstellt wurde, zeigt jetzt auch die Anzahl dieser an
// Die Präfixsequenz ist derzeit im SEQ-Feld der Primärsequenz aktiviert, das den Eintrag vorgenommen hat.
fieldToc.PrefixedSequenceIdentifier = "PrefixSequence";

// Jeder TOC-Eintrag zeigt die Anzahl der Präfixsequenzen unmittelbar links davon an
// der Seitennummer, auf der das SEQ-Feld der Hauptsequenz erscheint.
// Wir können ein benutzerdefiniertes Trennzeichen angeben, das zwischen diesen beiden Zahlen erscheint.
fieldToc.SequenceSeparator = ">";

Assert.AreEqual(" TOC  \\c MySequence \\s PrefixSequence \\d >", fieldToc.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);

// Es gibt zwei Möglichkeiten, SEQ-Felder zu verwenden, um dieses Inhaltsverzeichnis zu füllen.
// 1 - Einfügen eines SEQ-Felds, das zur Präfixsequenz des Inhaltsverzeichnisses gehört:
// Dieses Feld erhöht den SEQ-Sequenzzähler für die "PrefixSequence" um 1.
// Da dieses Feld nicht zur identifizierten Hauptfolge gehört
// durch die Eigenschaft "TableOfFiguresLabel" des Inhaltsverzeichnisses wird es nicht als Eintrag angezeigt.
FieldSeq fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "PrefixSequence";
builder.InsertParagraph();

Assert.AreEqual(" SEQ  PrefixSequence", fieldSeq.GetFieldCode());

// 2 - Einfügen eines SEQ-Felds, das zur Hauptsequenz des Inhaltsverzeichnisses gehört:
// Dieses SEQ-Feld erstellt einen Eintrag im Inhaltsverzeichnis.
// Der TOC-Eintrag enthält den Absatz, in dem sich das SEQ-Feld befindet, und die Nummer der Seite, auf der es erscheint.
// Dieser Eintrag zeigt auch den Zähler an, bei dem sich die Präfixsequenz derzeit befindet,
// getrennt von der Seitenzahl durch den Wert in der Eigenschaft SequenceSeparator des Inhaltsverzeichnisses.
// Der "PrefixSequence"-Zähler ist auf 1, dieses SEQ-Feld der Hauptsequenz befindet sich auf Seite 2,
// und das Trennzeichen ist ">", sodass der Eintrag "1>2" anzeigt.
builder.Write("First TOC entry, MySequence #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";

Assert.AreEqual(" SEQ  MySequence", fieldSeq.GetFieldCode());

// Eine Seite einfügen, die Präfixsequenz um 2 vorrücken und ein SEQ-Feld einfügen, um danach einen TOC-Eintrag zu erstellen.
// Die Präfixsequenz ist jetzt bei 2 und das SEQ-Feld der Hauptsequenz befindet sich auf Seite 3,
// Der TOC-Eintrag zeigt also "2>3" bei seiner Seitenzahl an.
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

### Siehe auch

* class [FieldToc](../)
* namensraum [Aspose.Words.Fields](../../fieldtoc/)
* Montage [Aspose.Words](../../../)


