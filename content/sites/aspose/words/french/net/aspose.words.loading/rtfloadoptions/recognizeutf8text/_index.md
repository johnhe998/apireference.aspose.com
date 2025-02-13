---
title: RtfLoadOptions.RecognizeUtf8Text
second_title: Référence de l'API Aspose.Words pour .NET
description: RtfLoadOptions propriété. Lorsquil est défini sur vraiCharsetDetectoressaiera de détecter les caractères UTF8 ils seront conservés lors de limportation.
type: docs
weight: 20
url: /fr/net/aspose.words.loading/rtfloadoptions/recognizeutf8text/
---
## RtfLoadOptions.RecognizeUtf8Text property

Lorsqu'il est défini sur vrai,CharsetDetectoressaiera de détecter les caractères UTF8, ils seront conservés lors de l'importation.

La valeur par défaut est false.

```csharp
public bool RecognizeUtf8Text { get; set; }
```

### Exemples

Montre comment détecter les caractères UTF-8 lors du chargement d'un document RTF.

```csharp
// Crée un objet "RtfLoadOptions" pour modifier la façon dont nous chargeons un document RTF.
RtfLoadOptions loadOptions = new RtfLoadOptions();

// Définissez la propriété "RecognizeUtf8Text" sur "false" pour supposer que le document utilise le jeu de caractères ISO 8859-1
// et charge chaque caractère du document.
// Définissez la propriété "RecognizeUtf8Text" sur "true" pour analyser tous les caractères de longueur variable pouvant apparaître dans le texte.
loadOptions.RecognizeUtf8Text = recognizeUtf8Text;

Document doc = new Document(MyDir + "UTF-8 characters.rtf", loadOptions);

Assert.AreEqual(
    recognizeUtf8Text
        ? "“John Doe´s list of currency symbols”™\r" +
          "€, ¢, £, ¥, ¤"
        : "â€œJohn DoeÂ´s list of currency symbolsâ€\u009dâ„¢\r" +
          "â‚¬, Â¢, Â£, Â¥, Â¤",
    doc.FirstSection.Body.GetText().Trim());
```

### Voir également

* class [RtfLoadOptions](../)
* espace de noms [Aspose.Words.Loading](../../rtfloadoptions/)
* Assemblée [Aspose.Words](../../../)


