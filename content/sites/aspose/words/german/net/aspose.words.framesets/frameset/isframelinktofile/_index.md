---
title: Frameset.IsFrameLinkToFile
second_title: Aspose.Words für .NET-API-Referenz
description: Frameset eigendom. Ruft einen Wert ab oder legt einen Wert fest der angibt ob die in the angegebene Webseite oder der Dateiname des DokumentsFrameDefaultUrl Eigenschaft ist eine externe Ressource mit der der Frame verknüpft ist.
type: docs
weight: 40
url: /de/net/aspose.words.framesets/frameset/isframelinktofile/
---
## Frameset.IsFrameLinkToFile property

Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob die in the angegebene Webseite oder der Dateiname des Dokuments[`FrameDefaultUrl`](../framedefaulturl/) Eigenschaft ist eine externe Ressource, mit der der Frame verknüpft ist.

```csharp
public bool IsFrameLinkToFile { get; set; }
```

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

* class [Frameset](../)
* namensraum [Aspose.Words.Framesets](../../frameset/)
* Montage [Aspose.Words](../../../)


