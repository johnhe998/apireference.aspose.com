---
title: ListLevel.DeletePictureBullet
second_title: Aspose.Words für .NET-API-Referenz
description: ListLevel methode. Löscht Bildaufzählungszeichen für die aktuelle Listenebene.
type: docs
weight: 160
url: /de/net/aspose.words.lists/listlevel/deletepicturebullet/
---
## ListLevel.DeletePictureBullet method

Löscht Bildaufzählungszeichen für die aktuelle Listenebene.

```csharp
public void DeletePictureBullet()
```

### Bemerkungen

Nach dem Löschen wird das Standard-Aufzählungszeichen angezeigt.

### Beispiele

Zeigt, wie Sie ein benutzerdefiniertes Bildsymbol für Beschriftungen von Listenelementen festlegen.

```csharp
Document doc = new Document();

List list = doc.Lists.Add(ListTemplate.BulletCircle);

// Erstellen Sie ein Bild-Aufzählungszeichen für die aktuelle Listenebene und legen Sie ein Bild aus einem lokalen Dateisystem fest
// als das Symbol, das die Aufzählungszeichen für diese Listenebene anzeigen.
list.ListLevels[0].CreatePictureBullet();
list.ListLevels[0].ImageData.SetImage(ImageDir + "Logo icon.ico");

Assert.IsTrue(list.ListLevels[0].ImageData.HasImage);

DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.List = list;
builder.Writeln("Hello world!");
builder.Write("Hello again!");

doc.Save(ArtifactsDir + "Lists.CreatePictureBullet.docx");

list.ListLevels[0].DeletePictureBullet();

Assert.IsNull(list.ListLevels[0].ImageData);
```

### Siehe auch

* class [ListLevel](../)
* namensraum [Aspose.Words.Lists](../../listlevel/)
* Montage [Aspose.Words](../../../)


