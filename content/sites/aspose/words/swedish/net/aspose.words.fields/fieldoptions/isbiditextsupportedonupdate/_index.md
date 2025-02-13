---
title: FieldOptions.IsBidiTextSupportedOnUpdate
second_title: Aspose.Words för .NET API Referens
description: FieldOptions fast egendom. Hämtar eller ställer in värdet som anger om dubbelriktad text stöds fullt ut under fältuppdatering eller inte.
type: docs
weight: 130
url: /sv/net/aspose.words.fields/fieldoptions/isbiditextsupportedonupdate/
---
## FieldOptions.IsBidiTextSupportedOnUpdate property

Hämtar eller ställer in värdet som anger om dubbelriktad text stöds fullt ut under fältuppdatering eller inte.

```csharp
public bool IsBidiTextSupportedOnUpdate { get; set; }
```

### Anmärkningar

När den här egenskapen är inställd på **Sann**, utförs ytterligare steg för att producera Right-To-Left language (dvs. arabiska eller hebreiska) kompatibla fältresultat under dess uppdatering.

När den här egenskapen är inställd på **falsk** och höger-till-vänster-språket används, korrektheten av fältresultat efter dess uppdatering garanteras inte.

Standardvärdet är **falsk**.

### Exempel

Visar hur man använder FieldOptions för att säkerställa att fältuppdatering fullt ut stöder dubbelriktad text.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Se till att alla fältoperationer som involverar text från höger till vänster fungerar som förväntat. 
doc.FieldOptions.IsBidiTextSupportedOnUpdate = true;

// Använd en dokumentbyggare för att infoga ett fält som innehåller texten från höger till vänster.
FormField comboBox = builder.InsertComboBox("MyComboBox", new[] { "עֶשְׂרִים", "שְׁלוֹשִׁים", "אַרְבָּעִים", "חֲמִשִּׁים", "שִׁשִּׁים" }, 0);
comboBox.CalculateOnExit = true;

doc.UpdateFields();
doc.Save(ArtifactsDir + "FieldOptions.Bidi.docx");
```

### Se även

* class [FieldOptions](../)
* namnutrymme [Aspose.Words.Fields](../../fieldoptions/)
* hopsättning [Aspose.Words](../../../)


