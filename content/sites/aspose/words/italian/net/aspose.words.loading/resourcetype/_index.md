---
title: Enum ResourceType
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Loading.ResourceType enum. Tipo di risorsa caricata.
type: docs
weight: 3500
url: /it/net/aspose.words.loading/resourcetype/
---
## ResourceType enumeration

Tipo di risorsa caricata.

```csharp
public enum ResourceType
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Image | `0` | Immagine. |
| CssStyleSheet | `1` | Foglio di stile CSS. |
| Document | `2` | Documento. |

### Esempi

Mostra come personalizzare il processo di caricamento di risorse esterne in un documento.

```csharp
{
    Document doc = new Document();
    doc.ResourceLoadingCallback = new ImageNameHandler();

    DocumentBuilder builder = new DocumentBuilder(doc);

    // Le immagini di solito vengono inserite utilizzando un URI o un array di byte.
    // Ogni istanza di un carico di risorse chiamerà il metodo ResourceLoading del nostro callback.
    builder.InsertImage("Google logo");
    builder.InsertImage("Aspose logo");
    builder.InsertImage("Watermark");

    Assert.AreEqual(3, doc.GetChildNodes(NodeType.Shape, true).Count);

    doc.Save(ArtifactsDir + "DocumentBase.ResourceLoadingCallback.docx");

/// <summary>
/// Ci consente di caricare immagini in un documento utilizzando abbreviazioni predefinite, al contrario degli URI.
/// Questo separerà la logica di caricamento delle immagini dal resto della costruzione del documento.
/// </summary>
private class ImageNameHandler : IResourceLoadingCallback
{
    public ResourceLoadingAction ResourceLoading(ResourceLoadingArgs args)
    {
        // Se questa richiamata incontra una delle scorciatoie dell'immagine durante il caricamento di un'immagine,
        // applicherà una logica univoca per ogni abbreviazione definita invece di trattarla come un URI.
        if (args.ResourceType == ResourceType.Image)
            switch (args.OriginalUri)
            {
                case "Google logo":
                    using (WebClient webClient = new WebClient())
                    {
                        args.SetData(webClient.DownloadData("http://www.google.com/images/logos/ps_logo2.png"));
                    }

                    return ResourceLoadingAction.UserProvided;

                case "Aspose logo":
                    args.SetData(File.ReadAllBytes(ImageDir + "Logo.jpg"));

                    return ResourceLoadingAction.UserProvided;

                case "Watermark":
                    args.SetData(File.ReadAllBytes(ImageDir + "Transparent background logo.png"));

                    return ResourceLoadingAction.UserProvided;
            }

        return ResourceLoadingAction.Default;
    }
}
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Loading](../../aspose.words.loading/)
* assemblea [Aspose.Words](../../)


