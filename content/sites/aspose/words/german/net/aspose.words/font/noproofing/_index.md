---
title: Font.NoProofing
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Wahr wenn die Rechtschreibung der formatierten Zeichen nicht geprüft werden soll.
type: docs
weight: 280
url: /de/net/aspose.words/font/noproofing/
---
## Font.NoProofing property

Wahr, wenn die Rechtschreibung der formatierten Zeichen nicht geprüft werden soll.

```csharp
public bool NoProofing { get; set; }
```

### Beispiele

Zeigt, wie verhindert wird, dass Text von Microsoft Word auf Rechtschreibprüfung geprüft wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Normalerweise hebt Microsoft Word Rechtschreibfehler mit einer gezackten roten Unterstreichung hervor.
// Wir können das "NoProofing"-Flag deaktivieren, um einen Textabschnitt zu erstellen, der
// umgeht die Rechtschreibprüfung, während sie vollständig deaktiviert wird.
builder.Font.NoProofing = true;

builder.Writeln("Proofing has been disabled, so these spelking errrs will not display red lines underneath.");

doc.Save(ArtifactsDir + "Font.NoProofing.docx");
```

### Siehe auch

* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


