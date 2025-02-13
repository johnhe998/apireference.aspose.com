---
title: OdtSaveOptions.IsStrictSchema11
second_title: Aspose.Words för .NET API Referens
description: OdtSaveOptions fast egendom. Anger om export ska motsvara ODTspecifikation 1.1 strikt. OOo 3.0 visar filer korrekt när de innehåller element och attribut för ODT 1.2. Använd false för detta ändamål eller true för strikt överensstämmelse med specifikation 1.1. Standardvärdet är falsk .
type: docs
weight: 20
url: /sv/net/aspose.words.saving/odtsaveoptions/isstrictschema11/
---
## OdtSaveOptions.IsStrictSchema11 property

Anger om export ska motsvara ODT-specifikation 1.1 strikt. OOo 3.0 visar filer korrekt när de innehåller element och attribut för ODT 1.2. Använd "false" för detta ändamål, eller "true" för strikt överensstämmelse med specifikation 1.1. Standardvärdet är **falsk** .

```csharp
public bool IsStrictSchema11 { get; set; }
```

### Exempel

Visar hur man får ett sparat dokument att överensstämma med ett äldre ODT-schema.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

OdtSaveOptions saveOptions = new OdtSaveOptions
{
    MeasureUnit = OdtSaveMeasureUnit.Centimeters,
    IsStrictSchema11 = exportToOdt11Specs
};

doc.Save(ArtifactsDir + "OdtSaveOptions.Odt11Schema.odt", saveOptions);
```

### Se även

* class [OdtSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../odtsaveoptions/)
* hopsättning [Aspose.Words](../../../)


