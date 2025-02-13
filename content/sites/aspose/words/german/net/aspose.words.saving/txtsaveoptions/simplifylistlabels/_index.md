---
title: TxtSaveOptions.SimplifyListLabels
second_title: Aspose.Words für .NET-API-Referenz
description: TxtSaveOptions eigendom. Gibt an ob das Programm Listenbeschriftungen vereinfachen soll falls komplexe Beschriftungsformatierungen nicht angemessen durch einfachen Text dargestellt werden.
type: docs
weight: 70
url: /de/net/aspose.words.saving/txtsaveoptions/simplifylistlabels/
---
## TxtSaveOptions.SimplifyListLabels property

Gibt an, ob das Programm Listenbeschriftungen vereinfachen soll, falls komplexe Beschriftungsformatierungen nicht angemessen durch einfachen Text dargestellt werden.

Wenn eingestellt **Stimmt** , nummerierte Listenbeschriftungen werden im einfachen numerischen Format und aufgeschlüsselte Listenbeschriftungen als einfache ASCII-Zeichen geschrieben. Der Standardwert ist **FALSCH**.

```csharp
public bool SimplifyListLabels { get; set; }
```

### Beispiele

Zeigt, wie Sie die Darstellung von Listen ändern, wenn Sie ein Dokument als Klartext speichern.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie eine Aufzählungsliste mit fünf Einrückungsebenen.
builder.ListFormat.ApplyBulletDefault();
builder.Writeln("Item 1");
builder.ListFormat.ListIndent();
builder.Writeln("Item 2");
builder.ListFormat.ListIndent();
builder.Writeln("Item 3");
builder.ListFormat.ListIndent();
builder.Writeln("Item 4");
builder.ListFormat.ListIndent();
builder.Write("Item 5");

// Erstellen Sie ein "TxtSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie wir das Dokument im Klartext speichern.
TxtSaveOptions txtSaveOptions = new TxtSaveOptions();

// Setzen Sie die Eigenschaft "SimplifyListLabels" auf "true", um eine Liste zu konvertieren
// Symbole in einfachere ASCII-Zeichen wie '*', 'o', '+', '>' usw.
// Setzen Sie die Eigenschaft "SimplifyListLabels" auf "false", um so viele ursprüngliche Listensymbole wie möglich beizubehalten.
txtSaveOptions.SimplifyListLabels = simplifyListLabels;

doc.Save(ArtifactsDir + "TxtSaveOptions.SimplifyListLabels.txt", txtSaveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.SimplifyListLabels.txt");

if (simplifyListLabels)
    Assert.AreEqual("* Item 1\r\n" +
                    "  > Item 2\r\n" +
                    "    + Item 3\r\n" +
                    "      - Item 4\r\n" +
                    "        o Item 5\r\n", docText);
else
    Assert.AreEqual("· Item 1\r\n" +
                    "o Item 2\r\n" +
                    "§ Item 3\r\n" +
                    "· Item 4\r\n" +
                    "o Item 5\r\n", docText);
```

### Siehe auch

* class [TxtSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../txtsaveoptions/)
* Montage [Aspose.Words](../../../)


