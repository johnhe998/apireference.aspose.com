---
title: FieldSet.BookmarkName
second_title: Aspose.Words für .NET-API-Referenz
description: FieldSet eigendom. Ruft den Namen des Lesezeichens ab oder legt ihn fest.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldset/bookmarkname/
---
## FieldSet.BookmarkName property

Ruft den Namen des Lesezeichens ab oder legt ihn fest.

```csharp
public string BookmarkName { get; set; }
```

### Beispiele

Zeigt, wie Text mit Lesezeichen mit einem SET-Feld erstellt und dann mit einem REF-Feld im Dokument angezeigt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

 // Markierten Text mit einem SET-Feld benennen.
// Dieses Feld bezieht sich auf das "Lesezeichen", nicht auf eine Lesezeichenstruktur, die im Text erscheint, sondern auf eine benannte Variable.
FieldSet fieldSet = (FieldSet)builder.InsertField(FieldType.FieldSet, false);
fieldSet.BookmarkName = "MyBookmark";
fieldSet.BookmarkText = "Hello world!";
fieldSet.Update();

Assert.AreEqual(" SET  MyBookmark \"Hello world!\"", fieldSet.GetFieldCode());

// Auf das Lesezeichen nach Namen in einem REF-Feld verweisen und seinen Inhalt anzeigen.
FieldRef fieldRef = (FieldRef)builder.InsertField(FieldType.FieldRef, true);
fieldRef.BookmarkName = "MyBookmark";
fieldRef.Update();

Assert.AreEqual(" REF  MyBookmark", fieldRef.GetFieldCode());
Assert.AreEqual("Hello world!", fieldRef.Result);

doc.Save(ArtifactsDir + "Field.SET.REF.docx");
```

### Siehe auch

* class [FieldSet](../)
* namensraum [Aspose.Words.Fields](../../fieldset/)
* Montage [Aspose.Words](../../../)


