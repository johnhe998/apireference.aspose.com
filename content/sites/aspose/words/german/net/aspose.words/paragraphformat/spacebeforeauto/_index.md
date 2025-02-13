---
title: ParagraphFormat.SpaceBeforeAuto
second_title: Aspose.Words für .NET-API-Referenz
description: ParagraphFormat eigendom. Wahr wenn der Abstand vor dem Absatz automatisch festgelegt wird.
type: docs
weight: 320
url: /de/net/aspose.words/paragraphformat/spacebeforeauto/
---
## ParagraphFormat.SpaceBeforeAuto property

Wahr, wenn der Abstand vor dem Absatz automatisch festgelegt wird.

```csharp
public bool SpaceBeforeAuto { get; set; }
```

### Bemerkungen

Wenn auf „true“ gesetzt, wird der Effekt von überschrieben[`SpaceBefore`](../spacebefore/).

Wenn Sie Absatzabstand davor und Abstand danach auf Automatisch setzen, Microsoft Word fügt automatisch 14 Punkt Abstand zwischen den Absätzen ein gemäß den folgenden Regeln:

* Normalerweise werden Leerzeichen nach allen Absätzen hinzugefügt.
* In einer Aufzählungs- oder nummerierten Liste wird der Abstand nur nach dem letzten Element in der Liste hinzugefügt. Zwischen den Listenelementen wird kein Abstand hinzugefügt.
* In einer verschachtelten Aufzählung oder nummerierten Liste wird kein Abstand hinzugefügt.
* Abstand wird normalerweise nach einer Tabelle hinzugefügt.
* Der Abstand wird nach einer Tabelle nicht hinzugefügt, wenn es sich um den letzten Block in einer Tabellenzelle handelt.
* Nach dem letzten Absatz in einer Tabellenzelle wird kein Abstand hinzugefügt.

### Beispiele

Zeigt, wie Sie den automatischen Absatzabstand festlegen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Einen großen Abstand vor und nach Absätzen anwenden, die dieser Builder erstellt.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// Setzen Sie diese Flags auf "true", um automatische Abstände anzuwenden,
// Ignoriert effektiv den Abstand in den Eigenschaften, die wir oben festgelegt haben.
// Lassen Sie sie auf "false", um unseren benutzerdefinierten Absatzabstand anzuwenden.
builder.ParagraphFormat.SpaceAfterAuto = autoSpacing;
builder.ParagraphFormat.SpaceBeforeAuto = autoSpacing;

// Fügen Sie zwei Absätze ein, die darüber und darunter einen Abstand haben, und speichern Sie das Dokument.
builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingAuto.docx");
```

### Siehe auch

* class [ParagraphFormat](../)
* namensraum [Aspose.Words](../../paragraphformat/)
* Montage [Aspose.Words](../../../)


