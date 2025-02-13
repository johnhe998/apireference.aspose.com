---
title: TxtSaveOptionsBase.Encoding
second_title: Aspose.Words per .NET API Reference
description: TxtSaveOptionsBase proprietà. Specifica la codifica da utilizzare durante lesportazione nei formati di testo. Il valore predefinito è Codifica.UTF8 .
type: docs
weight: 10
url: /it/net/aspose.words.saving/txtsaveoptionsbase/encoding/
---
## TxtSaveOptionsBase.Encoding property

Specifica la codifica da utilizzare durante l'esportazione nei formati di testo. Il valore predefinito è **Codifica.UTF8** .

```csharp
public Encoding Encoding { get; set; }
```

### Esempi

Mostra come impostare la codifica per un documento di output .txt.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aggiunge del testo con caratteri al di fuori del set di caratteri ASCII.
builder.Write("À È Ì Ò Ù.");

// Crea un oggetto "TxtSaveOptions", che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui salviamo il documento come testo normale.
TxtSaveOptions txtSaveOptions = new TxtSaveOptions();

// Verifica che la proprietà "Encoding" contenga la codifica appropriata per il contenuto del nostro documento.
Assert.AreEqual(System.Text.Encoding.UTF8, txtSaveOptions.Encoding);

doc.Save(ArtifactsDir + "TxtSaveOptions.Encoding.UTF8.txt", txtSaveOptions);

string docText = System.Text.Encoding.UTF8.GetString(File.ReadAllBytes(ArtifactsDir + "TxtSaveOptions.Encoding.UTF8.txt"));

Assert.AreEqual("\uFEFFÀ È Ì Ò Ù.\r\n", docText);

// L'utilizzo di una codifica non adatta può comportare la perdita del contenuto del documento.
txtSaveOptions.Encoding = System.Text.Encoding.ASCII;
doc.Save(ArtifactsDir + "TxtSaveOptions.Encoding.ASCII.txt", txtSaveOptions);
docText = System.Text.Encoding.ASCII.GetString(File.ReadAllBytes(ArtifactsDir + "TxtSaveOptions.Encoding.ASCII.txt"));

Assert.AreEqual("? ? ? ? ?.\r\n", docText);
```

### Guarda anche

* class [TxtSaveOptionsBase](../)
* spazio dei nomi [Aspose.Words.Saving](../../txtsaveoptionsbase/)
* assemblea [Aspose.Words](../../../)


