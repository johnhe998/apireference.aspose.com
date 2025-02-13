---
title: ImageFieldMergingArgs.Shape
second_title: Aspose.Words per .NET API Reference
description: ImageFieldMergingArgs proprietà. Specifica la forma che il motore di stampa unione deve inserire nel documento.
type: docs
weight: 60
url: /it/net/aspose.words.mailmerging/imagefieldmergingargs/shape/
---
## ImageFieldMergingArgs.Shape property

Specifica la forma che il motore di stampa unione deve inserire nel documento.

```csharp
public Shape Shape { get; set; }
```

### Osservazioni

Quando viene specificata questa proprietà, il motore di stampa unione ignora tutte le altre proprietà come[`ImageFileName`](../imagefilename/) o[`ImageStream`](../imagestream/) e inserisce semplicemente la forma nel documento.

Usa questa proprietà per controllare completamente il processo di unione di un campo di unione di immagini. Ad esempio, puoi specificare[`WrapType`](../../../aspose.words.drawing/shapebase/wraptype/) qualsiasi altra proprietà di forma per ottimizzare il nodo risultante. Tuttavia, tieni presente che sei responsabile della fornitura del contenuto della forma.

### Guarda anche

* class [Shape](../../../aspose.words.drawing/shape/)
* class [ImageFieldMergingArgs](../)
* spazio dei nomi [Aspose.Words.MailMerging](../../imagefieldmergingargs/)
* assemblea [Aspose.Words](../../../)


