---
title: RevisionOptions.ShowInBalloons
second_title: Aspose.Words för .NET API Referens
description: RevisionOptions fast egendom. Gör det möjligt att ange om revisionerna ska återges i ballongerna. Standardvärdet ärNone .
type: docs
weight: 160
url: /sv/net/aspose.words.layout/revisionoptions/showinballoons/
---
## RevisionOptions.ShowInBalloons property

Gör det möjligt att ange om revisionerna ska återges i ballongerna. Standardvärdet ärNone .

```csharp
public ShowInBalloons ShowInBalloons { get; set; }
```

### Anmärkningar

Observera att revisioner inte återges i ballonger förShowInAnnotations .

### Exempel

Visar hur man visar ändringar i ballonger.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Som standard har text som är en revision en annan färg för att skilja den från den andra icke-revisionstexten.
// Ställ in ett revisionsalternativ för att visa mer information om varje revision i en ballong på sidans högra marginal.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.Save(ArtifactsDir + "Revision.ShowRevisionBalloons.pdf");
```

Visar hur man ändrar utseendet på revisioner.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Hämta RevisionOptions-objektet som styr utseendet på revisioner.
RevisionOptions revisionOptions = doc.LayoutOptions.RevisionOptions;

// Gör insättningsrevisioner i grönt och kursivt.
revisionOptions.InsertedTextColor = RevisionColor.Green;
revisionOptions.InsertedTextEffect = RevisionTextEffect.Italic;

// Gör raderingsrevisioner i rött och fetstil.
revisionOptions.DeletedTextColor = RevisionColor.Red;
revisionOptions.DeletedTextEffect = RevisionTextEffect.Bold;

// Samma text kommer att visas två gånger i en rörelserevision:
// en gång vid avgångsplatsen och en gång vid ankomstdestinationen.
// Gör texten vid den flyttade från revisionen gul med dubbel genomstrykning
// och dubbelt understruket blått vid den flyttade till revisionen.
revisionOptions.MovedFromTextColor = RevisionColor.Yellow;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleStrikeThrough;
revisionOptions.MovedToTextColor = RevisionColor.Blue;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleUnderline;

// Gör formatrevisioner i mörkrött och fetstil.
revisionOptions.RevisedPropertiesColor = RevisionColor.DarkRed;
revisionOptions.RevisedPropertiesEffect = RevisionTextEffect.Bold;

// Placera en tjock mörkblå stapel till vänster på sidan bredvid rader som påverkas av ändringar.
revisionOptions.RevisionBarsColor = RevisionColor.DarkBlue;
revisionOptions.RevisionBarsWidth = 15.0f;

// Visa revisionsmärken och originaltext.
revisionOptions.ShowOriginalRevision = true;
revisionOptions.ShowRevisionMarks = true;

// Få rörelse, radering, formateringsrevisioner och kommentarer att dyka upp i gröna ballonger
// till höger på sidan.
revisionOptions.ShowInBalloons = ShowInBalloons.Format;
revisionOptions.CommentColor = RevisionColor.BrightGreen;

// Dessa funktioner är endast tillämpliga på format som .pdf eller .jpg.
doc.Save(ArtifactsDir + "Revision.RevisionOptions.pdf");
```

### Se även

* enum [ShowInBalloons](../../showinballoons/)
* class [RevisionOptions](../)
* namnutrymme [Aspose.Words.Layout](../../revisionoptions/)
* hopsättning [Aspose.Words](../../../)


