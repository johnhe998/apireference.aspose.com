---
title: Font.Kerning
second_title: Référence de l'API Aspose.Words pour .NET
description: Font propriété. Obtient ou définit la taille de police à laquelle le crénage commence.
type: docs
weight: 180
url: /fr/net/aspose.words/font/kerning/
---
## Font.Kerning property

Obtient ou définit la taille de police à laquelle le crénage commence.

```csharp
public double Kerning { get; set; }
```

### Exemples

Montre comment spécifier la taille de police à partir de laquelle le crénage commence à prendre effet.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial Black";

// Définit la taille de police du générateur et la taille minimale à laquelle le crénage prendra effet.
// La taille de la police tombe en dessous du seuil de crénage, donc la course ci-dessous n'aura pas de crénage.
builder.Font.Size = 18;
builder.Font.Kerning = 24;

builder.Writeln("TALLY. (Kerning not applied)");

// Définit le seuil de crénage de sorte que la taille de police actuelle du générateur soit au-dessus.
// Tout texte que nous ajoutons à partir de ce point aura un crénage appliqué. Les espaces entre les caractères
// sera ajusté, ce qui se traduira normalement par une exécution de texte légèrement plus esthétique.
builder.Font.Kerning = 12;

builder.Writeln("TALLY. (Kerning applied)");

doc.Save(ArtifactsDir + "Font.Kerning.docx");
```

### Voir également

* class [Font](../)
* espace de noms [Aspose.Words](../../font/)
* Assemblée [Aspose.Words](../../../)


