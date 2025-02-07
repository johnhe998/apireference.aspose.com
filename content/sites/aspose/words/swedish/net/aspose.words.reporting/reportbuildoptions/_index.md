---
title: Enum ReportBuildOptions
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Reporting.ReportBuildOptions uppräkning. Anger alternativ som styr beteendet förReportingEngine medan du bygger en rapport.
type: docs
weight: 4460
url: /sv/net/aspose.words.reporting/reportbuildoptions/
---
## ReportBuildOptions enumeration

Anger alternativ som styr beteendet för[`ReportingEngine`](../reportingengine/) medan du bygger en rapport.

```csharp
[Flags]
public enum ReportBuildOptions
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| None | `0` | Anger standardalternativ. |
| AllowMissingMembers | `1` | Anger att saknade objektmedlemmar ska behandlas som noll-literals av motorn. Det här alternativet påverkar endast åtkomst till instanser (det vill säga icke-statiska) objektmedlemmar och tilläggsmetoder. Om detta -alternativ inte är inställt, skapar motorn ett undantag när den stöter på en saknad objektmedlem. |
| RemoveEmptyParagraphs | `2` | Anger att motorn ska ta bort stycken som blir tomma efter att mallsyntaxtaggar har tagits bort eller ersatts med tomma värden. |
| InlineErrorMessages | `4` | Anger att motorn ska infoga mallsyntaxfelmeddelanden i utdatadokument. Om det här alternativet inte är inställt skapar motorn ett undantag när ett syntaxfel stöter på. |
| UseLegacyHeaderFooterVisiting | `8` | Anger att motorn ska besöka sektionens underordnade noder (sidhuvuden, sidfötter, kroppar) i en order som är kompatibel med Aspose.Words-versioner före 21.9. |
| RespectJpegExifOrientation | `10` | Anger att motorn ska använda EXIF-bildorienteringsvärden för att korrekt rotera infogade JPEG-bilder. |

### Se även

* namnutrymme [Aspose.Words.Reporting](../../aspose.words.reporting/)
* hopsättning [Aspose.Words](../../)


