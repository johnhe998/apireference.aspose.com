---
title: ImageSaveOptions.UseGdiEmfRenderer
second_title: Aspose.Words für .NET-API-Referenz
description: ImageSaveOptions eigendom. Ruft einen Wert ab oder legt einen Wert fest der festlegt ob GDI oder der Aspose.WordsMetadateiRenderer beim Speichern in EMF verwendet werden soll.
type: docs
weight: 180
url: /de/net/aspose.words.saving/imagesaveoptions/usegdiemfrenderer/
---
## ImageSaveOptions.UseGdiEmfRenderer property

Ruft einen Wert ab oder legt einen Wert fest, der festlegt, ob GDI+ oder der Aspose.Words-Metadatei-Renderer beim Speichern in EMF verwendet werden soll.

```csharp
public bool UseGdiEmfRenderer { get; set; }
```

### Bemerkungen

Wenn eingestellt`Stimmt`GDI+-Metadatei-Renderer wird verwendet. Das heißt, der Inhalt wird in das GDI+-Objekt graphics geschrieben und in der Metadatei gespeichert.

Wenn eingestellt`FALSCH` Aspose.Words-Metadatei-Renderer wird verwendet. Dh Inhalte werden direkt mit Aspose.Words in das Metafile-Format geschrieben.

Wirkt sich nur beim Speichern in EMF aus.

Das GDI+-Speichern funktioniert nur unter .NET.

Der Standardwert ist`Stimmt`.

### Beispiele

Zeigt, wie Sie beim Konvertieren eines Dokuments in .emf einen Renderer auswählen.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
            builder.Writeln("Hello world!");
            builder.InsertImage(ImageDir + "Logo.jpg");

            // Wenn wir das Dokument als EMF-Bild speichern, können wir ein SaveOptions-Objekt übergeben, um einen Renderer für das Bild auszuwählen.
            // Wenn wir das Flag "UseGdiEmfRenderer" auf "true" setzen, verwendet Aspose.Words den GDI+-Renderer.
            // Wenn wir das Flag "UseGdiEmfRenderer" auf "false" setzen, verwendet Aspose.Words seinen eigenen Metafile-Renderer.
            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Emf);
            saveOptions.UseGdiEmfRenderer = useGdiEmfRenderer;

            doc.Save(ArtifactsDir + "ImageSaveOptions.Renderer.emf", saveOptions);

            // Der GDI+-Renderer erstellt normalerweise größere Dateien.
            if (useGdiEmfRenderer)
#if NET48 || JAVA
                Assert.That(300000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.Renderer.emf").Length));
#elif NET5_0_OR_GREATER
                Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.Renderer.emf").Length));
#endif
            else
                Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.Renderer.emf").Length));
```

### Siehe auch

* class [ImageSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../imagesaveoptions/)
* Montage [Aspose.Words](../../../)


