---
title: ListLevel.CreatePictureBullet
second_title: Aspose.Words för .NET API Referens
description: ListLevel metod. Skapar bildpunktform för den aktuella listnivån.
type: docs
weight: 150
url: /sv/net/aspose.words.lists/listlevel/createpicturebullet/
---
## ListLevel.CreatePictureBullet method

Skapar bildpunktform för den aktuella listnivån.

```csharp
public void CreatePictureBullet()
```

### Anmärkningar

Observera att NumberStyle kommer att ställas in på Bullet och NumberFormat till "\xF0B7" för att korrekt visa bildpunkt. Röda korsbild kommer att ställas in som bildpunktbild vid skapande. För att ändra det, använd[`ImageData`](../imagedata/).

### Exempel

Visar hur du ställer in en anpassad bildikon för listobjektetiketter.

```csharp
Document doc = new Document();

List list = doc.Lists.Add(ListTemplate.BulletCircle);

// Skapa en bildpunkt för den aktuella listnivån och ställ in en bild från ett lokalt filsystem
// som ikonen som punkterna för denna listnivå kommer att visa.
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

### Se även

* class [ListLevel](../)
* namnutrymme [Aspose.Words.Lists](../../listlevel/)
* hopsättning [Aspose.Words](../../../)


