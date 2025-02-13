---
title: DigitalSignatureUtil.LoadSignatures
second_title: Aspose.Words för .NET API Referens
description: DigitalSignatureUtil metod. Laddar digitala signaturer från dokument.
type: docs
weight: 10
url: /sv/net/aspose.words.digitalsignatures/digitalsignatureutil/loadsignatures/
---
## LoadSignatures(string) {#loadsignatures_1}

Laddar digitala signaturer från dokument.

```csharp
public static DigitalSignatureCollection LoadSignatures(string fileName)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| fileName | String | Sökväg till dokumentet. |

### Returvärde

Samling av digitala signaturer. Returnerar tom samling om filen inte är signerad.

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

* class [DigitalSignatureCollection](../../digitalsignaturecollection/)
* class [DigitalSignatureUtil](../)
* namnutrymme [Aspose.Words.DigitalSignatures](../../digitalsignatureutil/)
* hopsättning [Aspose.Words](../../../)

---

## LoadSignatures(Stream) {#loadsignatures}

Laddar digitala signaturer från dokument med stream.

```csharp
public static DigitalSignatureCollection LoadSignatures(Stream stream)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| stream | Stream | Streama med dokumentet. |

### Returvärde

Samling av digitala signaturer. Returnerar tom samling om filen inte är signerad.

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

### Se även

* class [DigitalSignatureCollection](../../digitalsignaturecollection/)
* class [DigitalSignatureUtil](../)
* namnutrymme [Aspose.Words.DigitalSignatures](../../digitalsignatureutil/)
* hopsättning [Aspose.Words](../../../)


