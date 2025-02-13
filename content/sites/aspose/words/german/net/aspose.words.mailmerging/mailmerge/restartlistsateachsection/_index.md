---
title: MailMerge.RestartListsAtEachSection
second_title: Aspose.Words für .NET-API-Referenz
description: MailMerge eigendom. Ruft einen Wert ab oder legt einen Wert fest der angibt ob Listen in jedem Abschnitt nach der Ausführung eines Seriendrucks neu gestartet werden.
type: docs
weight: 110
url: /de/net/aspose.words.mailmerging/mailmerge/restartlistsateachsection/
---
## MailMerge.RestartListsAtEachSection property

Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob Listen in jedem Abschnitt nach der Ausführung eines Seriendrucks neu gestartet werden.

```csharp
public bool RestartListsAtEachSection { get; set; }
```

### Bemerkungen

Der Standardwert ist **Stimmt** .

### Beispiele

Zeigt, wie gesteuert wird, ob die Listennummerierung bei jedem Abschnitt neu gestartet wird, wenn der Seriendruck durchgeführt wird.

```csharp
Document doc = new Document(MyDir + "Section breaks with numbering.docx");

doc.MailMerge.RestartListsAtEachSection = false;
doc.MailMerge.Execute(new string[0], new object[0]);

doc.Save(ArtifactsDir + "MailMerge.RestartListsAtEachSection.pdf");
```

### Siehe auch

* class [MailMerge](../)
* namensraum [Aspose.Words.MailMerging](../../mailmerge/)
* Montage [Aspose.Words](../../../)


