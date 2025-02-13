---
title: Class Frameset
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Framesets.Frameset klas. Repräsentiert eine FramesSeite oder einen einzelnen Frame auf einer FramesSeite.
type: docs
weight: 2900
url: /de/net/aspose.words.framesets/frameset/
---
## Frameset class

Repräsentiert eine Frames-Seite oder einen einzelnen Frame auf einer Frames-Seite.

```csharp
public class Frameset
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [Frameset](frameset/)() | Default_Constructor |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [ChildFramesets](../../aspose.words.framesets/frameset/childframesets/) { get; } | Ruft die Sammlung von untergeordneten Frames und Frameseiten ab. |
| [FrameDefaultUrl](../../aspose.words.framesets/frameset/framedefaulturl/) { get; set; } | Ruft die Webseiten-URL oder den Namen der Dokumentdatei ab oder legt sie fest, die/der in diesem Frame angezeigt werden soll. |
| [IsFrameLinkToFile](../../aspose.words.framesets/frameset/isframelinktofile/) { get; set; } | Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob die in the angegebene Webseite oder der Dateiname des Dokuments[`FrameDefaultUrl`](./framedefaulturl/) Eigenschaft ist eine externe Ressource, mit der der Frame verknüpft ist. |

### Bemerkungen

Wenn die[`ChildFramesets`](./childframesets/) -Eigenschaft Elemente enthält, ist diese Instanz eine Frames-Seite, andernfalls ist es ein einzelner Frame.

### Beispiele

Zeigt, wie auf Frames auf der Seite zugegriffen wird.

```csharp
// Dokument enthält mehrere Frames mit Links zu anderen Dokumenten.
Document doc = new Document(MyDir + "Frameset.docx");

// Wir können die Standard-URL (eine Webseiten-URL oder ein lokales Dokument) prüfen oder ob der Frame eine externe Ressource ist.
Assert.AreEqual("https://file-examples-com.github.io/uploads/2017/02/file-sample_100kB.docx",
    doc.Frameset.ChildFramesets[0].ChildFramesets[0].FrameDefaultUrl);
Assert.True(doc.Frameset.ChildFramesets[0].ChildFramesets[0].IsFrameLinkToFile);

Assert.AreEqual("Document.docx", doc.Frameset.ChildFramesets[1].FrameDefaultUrl);
Assert.False(doc.Frameset.ChildFramesets[1].IsFrameLinkToFile);

// Eigenschaften für einen unserer Frames ändern.
doc.Frameset.ChildFramesets[0].ChildFramesets[0].FrameDefaultUrl =
    "https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Absolute%20position%20tab.docx";
doc.Frameset.ChildFramesets[0].ChildFramesets[0].IsFrameLinkToFile = false;
```

### Siehe auch

* namensraum [Aspose.Words.Framesets](../../aspose.words.framesets/)
* Montage [Aspose.Words](../../)


