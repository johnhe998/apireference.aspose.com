---
title: Class FileCorruptedException
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.FileCorruptedException klas. Wird während des Ladens des Dokuments ausgelöst wenn das Dokument beschädigt zu sein scheint und nicht geladen werden kann.
type: docs
weight: 2620
url: /de/net/aspose.words/filecorruptedexception/
---
## FileCorruptedException class

Wird während des Ladens des Dokuments ausgelöst, wenn das Dokument beschädigt zu sein scheint und nicht geladen werden kann.

```csharp
public class FileCorruptedException : Exception
```

### Beispiele

Zeigt, wie eine FileCorruptedException abgefangen wird.

```csharp
try
{
    // Wenn wir beim Versuch, ein Dokument mit Microsoft Word zu öffnen, eine Fehlermeldung „Inhalt nicht lesbar“ erhalten,
    // Es besteht die Möglichkeit, dass beim Versuch, dieses Dokument mit Aspose.Words zu laden, eine Ausnahme ausgelöst wird.
    Document doc = new Document(MyDir + "Corrupted document.docx");
}
catch (FileCorruptedException e)
{
    Console.WriteLine(e.Message);
}
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


