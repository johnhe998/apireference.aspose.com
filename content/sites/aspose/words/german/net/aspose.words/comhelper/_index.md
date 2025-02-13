---
title: Class ComHelper
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.ComHelper klas. Stellt Methoden für COMClients bereit um ein Dokument in Aspose.Words zu laden.
type: docs
weight: 210
url: /de/net/aspose.words/comhelper/
---
## ComHelper class

Stellt Methoden für COM-Clients bereit, um ein Dokument in Aspose.Words zu laden.

```csharp
public class ComHelper
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [ComHelper](comhelper/)() | Initialisiert eine neue Instanz dieser Klasse. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [Open](../../aspose.words/comhelper/open/#open)(Stream) | Ermöglicht das Laden einer COM-Anwendung[`Document`](../document/) aus einem Stream. |
| [Open](../../aspose.words/comhelper/open/#open_1)(string) | Ermöglicht einer COM-Anwendung das Laden von a[`Document`](../document/) aus einer Datei. |
| [OpenIStream](../../aspose.words/comhelper/openistream/)(IStream) | Ermöglicht einer COM-Anwendung das Laden von a[`Document`](../document/) aus einem IStream-Objekt. |

### Bemerkungen

Verwenden Sie die`ComHelper` Klasse zum Laden eines Dokuments aus einer Datei oder einem Stream in ein [`Document`](../document/) Objekt in einer COM-Anwendung.

Das[`Document`](../document/)-Klasse bietet einen Standardkonstruktor zum Erstellen eines neuen Dokuments sowie überladene Konstruktoren zum Laden eines Dokuments aus einer Datei oder einem Stream. Wenn Sie Aspose.Words aus einer .NET-Anwendung verwenden, können Sie alle verwenden[`Document`](../document/) Konstruktoren direkt, aber wenn Sie Aspose.Words aus einer COM-Anwendung verwenden, nur die Standardeinstellung[`Document`](../document/) Konstrukteur ist vorhanden.

### Beispiele

```csharp
[VBScript]

Dim helper
Set helper = CreateObject("Aspose.Words.ComHelper")

Dim doc
Set doc = helper.Open(fileName)
```

Zeigt, wie Dokumente mit der ComHelper-Klasse geöffnet werden.

```csharp
// Die ComHelper-Klasse ermöglicht es uns, Dokumente aus COM-Clients zu laden.
ComHelper comHelper = new ComHelper();

// 1 - Verwendung eines lokalen Systemdateinamens:
Document doc = comHelper.Open(MyDir + "Document.docx");

Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", doc.GetText().Trim());

// 2 - Aus einem Stream:
using (FileStream stream = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    doc = comHelper.Open(stream);

    Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", doc.GetText().Trim());
}
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


