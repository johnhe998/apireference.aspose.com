---
title: SaveOptions.CreateSaveOptions
second_title: Aspose.Words för .NET API Referens
description: SaveOptions metod. Skapar ett sparalternativobjekt av en klass som är lämplig för det angivna lagringsformatet.
type: docs
weight: 10
url: /sv/net/aspose.words.saving/saveoptions/createsaveoptions/
---
## CreateSaveOptions(SaveFormat) {#createsaveoptions}

Skapar ett sparalternativobjekt av en klass som är lämplig för det angivna lagringsformatet.

```csharp
public static SaveOptions CreateSaveOptions(SaveFormat saveFormat)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| saveFormat | SaveFormat | Sparningsformatet för vilket ett objekt för sparaalternativ skapas. |

### Returvärde

Ett objekt av en klass som härrör från[`SaveOptions`](../).

### Exempel

Visar ett alternativ för att optimera minnesförbrukningen vid rendering av stora dokument till PDF.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
SaveOptions saveOptions = SaveOptions.CreateSaveOptions(SaveFormat.Pdf);

// Ställ in egenskapen "MemoryOptimization" till "true" för att minska minnesutrymmet för stora dokuments lagringsåtgärder
// till priset av att operationens varaktighet ökar.
// Ställ in egenskapen "MemoryOptimization" till "false" för att spara dokumentet som en PDF-fil normalt.
saveOptions.MemoryOptimization = memoryOptimization;

doc.Save(ArtifactsDir + "PdfSaveOptions.MemoryOptimization.pdf", saveOptions);
```

### Se även

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [SaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../saveoptions/)
* hopsättning [Aspose.Words](../../../)

---

## CreateSaveOptions(string) {#createsaveoptions_1}

Skapar ett sparaalternativobjekt av en klass som är lämplig för filtillägget som anges i det angivna filnamnet.

```csharp
public static SaveOptions CreateSaveOptions(string fileName)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| fileName | String | Förlängningen av det här filnamnet bestämmer klassen för objektet spara alternativ som ska skapas. |

### Returvärde

Ett objekt av en klass som härrör från[`SaveOptions`](../).

### Exempel

Visar hur man ställer in en standardmall för dokument som inte har bifogade mallar.

```csharp
Document doc = new Document();

// Aktivera automatisk stiluppdatering, men bifoga inte ett malldokument.
doc.AutomaticallyUpdateStyles = true;

Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// Eftersom det inte finns något malldokument hade dokumentet ingenstans att spåra stiländringar.
// Använd ett SaveOptions-objekt för att automatiskt ställa in en mall
// om ett dokument som vi sparar inte har ett.
SaveOptions options = SaveOptions.CreateSaveOptions("Document.DefaultTemplate.docx");
options.DefaultTemplate = MyDir + "Business brochure.dotx";

doc.Save(ArtifactsDir + "Document.DefaultTemplate.docx", options);
```

### Se även

* class [SaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../saveoptions/)
* hopsättning [Aspose.Words](../../../)


