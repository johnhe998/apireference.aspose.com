---
title: Class DigitalSignatureUtil
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.DigitalSignatures.DigitalSignatureUtil klass. Tillhandahåller metoder för att signera dokument.
type: docs
weight: 400
url: /sv/net/aspose.words.digitalsignatures/digitalsignatureutil/
---
## DigitalSignatureUtil class

Tillhandahåller metoder för att signera dokument.

```csharp
public static class DigitalSignatureUtil
```

## Metoder

| namn | Beskrivning |
| --- | --- |
| static [LoadSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/loadsignatures/#loadsignatures)(Stream) | Laddar digitala signaturer från dokument med stream. |
| static [LoadSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/loadsignatures/#loadsignatures_1)(string) | Laddar digitala signaturer från dokument. |
| static [RemoveAllSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/removeallsignatures/#removeallsignatures)(Stream, Stream) | Tar bort alla digitala signaturer från dokumentet i källströmmen och skriver osignerat dokument till målströmmen. |
| static [RemoveAllSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/removeallsignatures/#removeallsignatures_1)(string, string) | Tar bort alla digitala signaturer från källfilen och skriver osignerad fil till målfilen. |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign)(Stream, Stream, CertificateHolder) | Signerar källdokument med given[`CertificateHolder`](../certificateholder/)med digital signatur och skriver signerat dokument till destinationsströmmen. |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign_2)(string, string, CertificateHolder) | Signerar källdokument med given[`CertificateHolder`](../certificateholder/) med digital signatur och skriver signerat dokument till destinationsfilen. |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign_1)(Stream, Stream, CertificateHolder, SignOptions) | Signerar källdokument med given[`CertificateHolder`](../certificateholder/) och[`SignOptions`](../signoptions/) med digital signatur och skriver signerat dokument till destinationsströmmen. |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign_3)(string, string, CertificateHolder, SignOptions) | Signerar källdokument med given[`CertificateHolder`](../certificateholder/) och[`SignOptions`](../signoptions/) med digital signatur och skriver signerat dokument till destinationsfilen. |

### Anmärkningar

Eftersom digital signatur fungerar med filinnehåll snarare än Document Object Model placeras dessa metoder i en separat klass.

Format som stöds ärDoc ochDocx.

### Exempel

Visar hur man laddar signaturer från ett digitalt signerat dokument.

```csharp
// Det finns två sätt att ladda ett signerat dokuments samling av digitala signaturer med klassen DigitalSignatureUtil.
// 1 - Ladda från ett dokument från ett lokalt filsystem filnamn:
DigitalSignatureCollection digitalSignatures = 
    DigitalSignatureUtil.LoadSignatures(MyDir + "Digitally signed.docx");

// Om denna samling inte är tom kan vi verifiera att dokumentet är digitalt signerat.
Assert.AreEqual(1, digitalSignatures.Count);

// 2 - Ladda från ett dokument från en FileStream:
using (Stream stream = new FileStream(MyDir + "Digitally signed.docx", FileMode.Open))
{
    digitalSignatures = DigitalSignatureUtil.LoadSignatures(stream);
    Assert.AreEqual(1, digitalSignatures.Count);
}
```

Visar hur du tar bort digitala signaturer från ett digitalt signerat dokument.

```csharp
// Det finns två sätt att använda klassen DigitalSignatureUtil för att ta bort digitala signaturer
// från ett signerat dokument genom att spara en osignerad kopia av det någon annanstans i det lokala filsystemet.
// 1 - Bestäm platserna för både det signerade dokumentet och den osignerade kopian med filnamnssträngar:
DigitalSignatureUtil.RemoveAllSignatures(MyDir + "Digitally signed.docx",
    ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromString.docx");

// 2 - Bestäm platserna för både det signerade dokumentet och den osignerade kopian av filströmmar:
using (Stream streamIn = new FileStream(MyDir + "Digitally signed.docx", FileMode.Open))
{
    using (Stream streamOut = new FileStream(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromStream.docx", FileMode.Create))
    {
        DigitalSignatureUtil.RemoveAllSignatures(streamIn, streamOut);
    }
}

// Verifiera att båda våra utdatadokument inte har några digitala signaturer.
Assert.That(DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromString.docx"), Is.Empty);
Assert.That(DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromStream.docx"), Is.Empty);
```

### Se även

* namnutrymme [Aspose.Words.DigitalSignatures](../../aspose.words.digitalsignatures/)
* hopsättning [Aspose.Words](../../)


