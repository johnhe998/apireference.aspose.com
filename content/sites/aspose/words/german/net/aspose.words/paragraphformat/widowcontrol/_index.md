---
title: ParagraphFormat.WidowControl
second_title: Aspose.Words für .NET-API-Referenz
description: ParagraphFormat eigendom. Wahr wenn die erste und letzte Zeile des Absatzes auf derselben Seite wie der Rest des Absatzes bleiben sollen.
type: docs
weight: 390
url: /de/net/aspose.words/paragraphformat/widowcontrol/
---
## ParagraphFormat.WidowControl property

Wahr, wenn die erste und letzte Zeile des Absatzes auf derselben Seite wie der Rest des Absatzes bleiben sollen.

```csharp
public bool WidowControl { get; set; }
```

### Beispiele

Zeigt, wie die Widow/Waisen-Steuerung für einen Absatz aktiviert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wenn wir den Text schreiben, der nicht auf eine Seite passt, kann eine Zeile auf die nächste Seite überlaufen.
// Die einzelne Zeile, die auf der nächsten Seite endet, wird "Orphan" genannt,
// und die vorherige Zeile, in der das Waisenkind abgebrochen wurde, heißt "Widow".
// Wir können Waisen und Witwen reparieren, indem wir Text über Schriftgröße, Abstand oder Seitenränder neu anordnen.
// Wenn wir die Abmessungen unseres Dokuments beibehalten möchten, können wir dieses Flag auf "true" setzen
 // um Witwen auf die gleiche Seite wie ihre jeweiligen Waisenkinder zu schieben.
// Belassen Sie dieses Flag auf "false", um Widow/Waisen-Paare im Text zu belassen.
// Für jeden Absatz ist diese Einstellung in Microsoft Word über Home -> Absatz -> Absatzeinstellungen
// (Schaltfläche unten rechts auf der Registerkarte "Absatz") -> "Witwen-/Waisenkontrolle".
builder.ParagraphFormat.WidowControl = widowControl; 

// Text einfügen, der ein Waisenkind und eine Witwe erzeugt.
builder.Font.Size = 68;
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "ParagraphFormat.WidowControl.docx");
```

### Siehe auch

* class [ParagraphFormat](../)
* namensraum [Aspose.Words](../../paragraphformat/)
* Montage [Aspose.Words](../../../)


