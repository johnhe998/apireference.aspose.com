---
title: Interface IDocumentSavingCallback
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Saving.IDocumentSavingCallback interface. Implémentez cette interface si vous souhaitez que votre propre méthode personnalisée soit appelée lors de lenregistrement dun document.
type: docs
weight: 4890
url: /fr/net/aspose.words.saving/idocumentsavingcallback/
---
## IDocumentSavingCallback interface

Implémentez cette interface si vous souhaitez que votre propre méthode personnalisée soit appelée lors de l'enregistrement d'un document.

```csharp
public interface IDocumentSavingCallback
```

## Méthodes

| Nom | La description |
| --- | --- |
| [Notify](../../aspose.words.saving/idocumentsavingcallback/notify/)(DocumentSavingArgs) | Ceci est appelé pour notifier la progression de l'enregistrement du document. |

### Exemples

Montre comment gérer un document lors de l'enregistrement au format HTML.

```csharp
public void ProgressCallback(SaveFormat saveFormat, string ext)
{
    Document doc = new Document(MyDir + "Big document.docx");

    // Les formats suivants sont pris en charge : Html, Mhtml, Epub.
    HtmlSaveOptions saveOptions = new HtmlSaveOptions(saveFormat)
    {
        ProgressCallback = new SavingProgressCallback()
    };

    var exception = Assert.Throws<OperationCanceledException>(() =>
        doc.Save(ArtifactsDir + $"HtmlSaveOptions.ProgressCallback.{ext}", saveOptions));
    Assert.True(exception?.Message.Contains("EstimatedProgress"));
}

/// <summary>
/// Enregistrement du rappel de progression. Annulez l'enregistrement d'un document après les secondes "MaxDuration".
/// </summary>
public class SavingProgressCallback : IDocumentSavingCallback
{
    /// <summary>
    /// Ctr.
    /// </summary>
    public SavingProgressCallback()
    {
        mSavingStartedAt = DateTime.Now;
    }

    /// <summary>
    /// Méthode de rappel appelée lors de l'enregistrement du document.
    /// </summary>
    /// <param name="args">Enregistrement des arguments.</param>
    public void Notify(DocumentSavingArgs args)
    {
        DateTime canceledAt = DateTime.Now;
        double ellapsedSeconds = (canceledAt - mSavingStartedAt).TotalSeconds;
        if (ellapsedSeconds > MaxDuration)
            throw new OperationCanceledException($"EstimatedProgress = {args.EstimatedProgress}; CanceledAt = {canceledAt}");
    }

    /// <summary>
    /// Date et heure de début de l'enregistrement du document.
    /// </summary>
    private readonly DateTime mSavingStartedAt;

    /// <summary>
    /// Durée maximale autorisée en sec.
    /// </summary>
    private const double MaxDuration = 0.1d;
}
```

Montre comment gérer un document lors de l'enregistrement au format docx.

```csharp
public void ProgressCallback(SaveFormat saveFormat, string ext)
{
    Document doc = new Document(MyDir + "Big document.docx");

    // Les formats suivants sont pris en charge : Docx, FlatOpc, Docm, Dotm, Dotx.
    OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(saveFormat)
    {
        ProgressCallback = new SavingProgressCallback()
    };

    var exception = Assert.Throws<OperationCanceledException>(() =>
        doc.Save(ArtifactsDir + $"OoxmlSaveOptions.ProgressCallback.{ext}", saveOptions));
    Assert.True(exception?.Message.Contains("EstimatedProgress"));
}

/// <summary>
/// Enregistrement du rappel de progression. Annulez l'enregistrement d'un document après les secondes "MaxDuration".
/// </summary>
public class SavingProgressCallback : IDocumentSavingCallback
{
    /// <summary>
    /// Ctr.
    /// </summary>
    public SavingProgressCallback()
    {
        mSavingStartedAt = DateTime.Now;
    }

    /// <summary>
    /// Méthode de rappel appelée lors de l'enregistrement du document.
    /// </summary>
    /// <param name="args">Enregistrement des arguments.</param>
    public void Notify(DocumentSavingArgs args)
    {
        DateTime canceledAt = DateTime.Now;
        double ellapsedSeconds = (canceledAt - mSavingStartedAt).TotalSeconds;
        if (ellapsedSeconds > MaxDuration)
            throw new OperationCanceledException($"EstimatedProgress = {args.EstimatedProgress}; CanceledAt = {canceledAt}");
    }

    /// <summary>
    /// Date et heure de début de l'enregistrement du document.
    /// </summary>
    private readonly DateTime mSavingStartedAt;

    /// <summary>
    /// Durée maximale autorisée en sec.
    /// </summary>
    private const double MaxDuration = 0.01d;
}
```

Montre comment gérer un document lors de l'enregistrement dans xamlflow.

```csharp
public void ProgressCallback(SaveFormat saveFormat, string ext)
{
    Document doc = new Document(MyDir + "Big document.docx");

    // Les formats suivants sont pris en charge : XamlFlow, XamlFlowPack.
    XamlFlowSaveOptions saveOptions = new XamlFlowSaveOptions(saveFormat)
    {
        ProgressCallback = new SavingProgressCallback()
    };

    var exception = Assert.Throws<OperationCanceledException>(() =>
        doc.Save(ArtifactsDir + $"XamlFlowSaveOptions.ProgressCallback.{ext}", saveOptions));
    Assert.True(exception?.Message.Contains("EstimatedProgress"));
}

/// <summary>
/// Enregistrement du rappel de progression. Annulez l'enregistrement d'un document après les secondes "MaxDuration".
/// </summary>
public class SavingProgressCallback : IDocumentSavingCallback
{
    /// <summary>
    /// Ctr.
    /// </summary>
    public SavingProgressCallback()
    {
        mSavingStartedAt = DateTime.Now;
    }

    /// <summary>
    /// Méthode de rappel appelée lors de l'enregistrement du document.
    /// </summary>
    /// <param name="args">Enregistrement des arguments.</param>
    public void Notify(DocumentSavingArgs args)
    {
        DateTime canceledAt = DateTime.Now;
        double ellapsedSeconds = (canceledAt - mSavingStartedAt).TotalSeconds;
        if (ellapsedSeconds > MaxDuration)
            throw new OperationCanceledException($"EstimatedProgress = {args.EstimatedProgress}; CanceledAt = {canceledAt}");
    }

    /// <summary>
    /// Date et heure de début de l'enregistrement du document.
    /// </summary>
    private readonly DateTime mSavingStartedAt;

    /// <summary>
    /// Durée maximale autorisée en sec.
    /// </summary>
    private const double MaxDuration = 0.01d;
}
```

### Voir également

* espace de noms [Aspose.Words.Saving](../../aspose.words.saving/)
* Assemblée [Aspose.Words](../../)


