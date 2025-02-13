---
title: Paragraph.JoinRunsWithSameFormatting
second_title: Aspose.Words für .NET-API-Referenz
description: Paragraph methode. Verbindet Läufe mit der gleichen Formatierung im Absatz.
type: docs
weight: 280
url: /de/net/aspose.words/paragraph/joinrunswithsameformatting/
---
## Paragraph.JoinRunsWithSameFormatting method

Verbindet Läufe mit der gleichen Formatierung im Absatz.

```csharp
public int JoinRunsWithSameFormatting()
```

### Rückgabewert

Anzahl der durchgeführten Joins. Wann **N** Aneinandergrenzende Läufe werden zusammengefügt, sie zählen als **N - 1** schließt sich an.

### Beispiele

Zeigt, wie Sie Absätze vereinfachen, indem Sie überflüssige Läufe zusammenführen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Vier Textfolgen in den Absatz einfügen.
builder.Write("Run 1. ");
builder.Write("Run 2. ");
builder.Write("Run 3. ");
builder.Write("Run 4. ");

// Wenn wir dieses Dokument in Microsoft Word öffnen, sieht der Absatz wie ein nahtloser Textkörper aus.
// Es wird jedoch aus vier separaten Läufen mit derselben Formatierung bestehen. Fragmentierte Absätze wie dieser
// kann auftreten, wenn wir Teile eines Absatzes mehrmals manuell in Microsoft Word bearbeiten.
Paragraph para = builder.CurrentParagraph;

Assert.AreEqual(4, para.Runs.Count);

// Ändern Sie den Stil des letzten Laufs, um ihn von den ersten drei abzuheben.
para.Runs[3].Font.StyleIdentifier = StyleIdentifier.Emphasis;

// Wir können die Methode "JoinRunsWithSameFormatting" ausführen, um den Inhalt des Dokuments zu optimieren
// durch Zusammenführen ähnlicher Läufe zu einem, wodurch ihre Gesamtzahl reduziert wird.
// Diese Methode gibt auch die Anzahl der Läufe zurück, die diese Methode zusammengeführt hat.
// Diese beiden Zusammenführungen erfolgten, um die Läufe Nr. 1, Nr. 2 und Nr. 3 zu kombinieren,
// während Lauf Nr. 4 ausgelassen wird, da er einen inkompatiblen Stil hat.
Assert.AreEqual(2, para.JoinRunsWithSameFormatting());

// Die Anzahl der verbleibenden Läufe entspricht der ursprünglichen Anzahl
// minus der Anzahl der Run-Merges, die die "JoinRunsWithSameFormatting"-Methode ausgeführt hat.
Assert.AreEqual(2, para.Runs.Count);
Assert.AreEqual("Run 1. Run 2. Run 3. ", para.Runs[0].Text);
Assert.AreEqual("Run 4. ", para.Runs[1].Text);
```

### Siehe auch

* class [Paragraph](../)
* namensraum [Aspose.Words](../../paragraph/)
* Montage [Aspose.Words](../../../)


