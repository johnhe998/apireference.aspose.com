---
title: StyleCollection.AddCopy
second_title: Aspose.Words für .NET-API-Referenz
description: StyleCollection methode. Kopiert einen Stil in diese Sammlung.
type: docs
weight: 70
url: /de/net/aspose.words/stylecollection/addcopy/
---
## StyleCollection.AddCopy method

Kopiert einen Stil in diese Sammlung.

```csharp
public Style AddCopy(Style style)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| style | Style | Zu kopierender Stil. |

### Rückgabewert

Kopierter Stil, gebrauchsfertig.

### Bemerkungen

Der zu kopierende Stil kann sowohl zum selben Dokument als auch zu einem anderen Dokument gehören.

Verknüpfter Stil wird kopiert.

Diese Methode kopiert keine Basisstile.

Wenn die Sammlung bereits einen Stil mit demselben Namen enthält, wird der neue Name automatisch generiert, indem das Suffix "_number" beginnend mit 0 hinzugefügt wird, z. B. "Normal_0", "Überschrift 1_1" usw. Verwenden[`Name`](../../style/name/) setter zum Ändern des Namens des importierten Stils.

### Beispiele

Zeigt, wie Sie einen Stil aus einem Dokument in ein anderes Dokument importieren.

```csharp
Document srcDoc = new Document();

// Erstellen Sie einen benutzerdefinierten Stil für das Quelldokument.
Style srcStyle = srcDoc.Styles.Add(StyleType.Paragraph, "MyStyle");
srcStyle.Font.Color = Color.Red;

// Den benutzerdefinierten Stil des Quelldokuments in das Zieldokument importieren.
Document dstDoc = new Document();
Style newStyle = dstDoc.Styles.AddCopy(srcStyle);

// Der importierte Stil sieht genauso aus wie sein Quellstil.
Assert.AreEqual("MyStyle", newStyle.Name);
Assert.AreEqual(Color.Red.ToArgb(), newStyle.Font.Color.ToArgb());
```

Zeigt, wie Sie den Stil eines Dokuments klonen.

```csharp
Document doc = new Document();

// Die AddCopy-Methode erstellt eine Kopie des angegebenen Stils und
// generiert automatisch einen neuen Namen für den Stil, z. B. "Überschrift 1_0".
Style newStyle = doc.Styles.AddCopy(doc.Styles["Heading 1"]);

// Verwenden Sie die "Name"-Eigenschaft des Stils, um den identifizierenden Namen des Stils zu ändern.
newStyle.Name = "My Heading 1";

// Unser Dokument hat jetzt zwei identisch aussehende Stile mit unterschiedlichen Namen.
// Das Ändern der Einstellungen eines der Stile wirkt sich nicht auf den anderen aus.
newStyle.Font.Color = Color.Red;

Assert.AreEqual("My Heading 1", newStyle.Name);
Assert.AreEqual("Heading 1", doc.Styles["Heading 1"].Name);

Assert.AreEqual(doc.Styles["Heading 1"].Type, newStyle.Type);
Assert.AreEqual(doc.Styles["Heading 1"].Font.Name, newStyle.Font.Name);
Assert.AreEqual(doc.Styles["Heading 1"].Font.Size, newStyle.Font.Size);
Assert.AreNotEqual(doc.Styles["Heading 1"].Font.Color, newStyle.Font.Color);
```

### Siehe auch

* class [Style](../../style/)
* class [StyleCollection](../)
* namensraum [Aspose.Words](../../stylecollection/)
* Montage [Aspose.Words](../../../)


