---
title: Fill.Solid
second_title: Aspose.Words per .NET API Reference
description: Fill metodo. Imposta il riempimento su un colore uniforme.
type: docs
weight: 200
url: /it/net/aspose.words.drawing/fill/solid/
---
## Solid() {#solid}

Imposta il riempimento su un colore uniforme.

```csharp
public void Solid()
```

### Osservazioni

Utilizzare questo metodo per riconvertire qualsiasi riempimento in riempimento solido.

### Guarda anche

* class [Fill](../)
* spazio dei nomi [Aspose.Words.Drawing](../../fill/)
* assemblea [Aspose.Words](../../../)

---

## Solid(Color) {#solid_1}

Imposta il riempimento su un colore uniforme specificato.

```csharp
public void Solid(Color color)
```

### Osservazioni

Utilizzare questo metodo per riconvertire qualsiasi riempimento in riempimento solido.

### Esempi

Mostra come riconvertire qualsiasi riempimento in riempimento solido.

```csharp
Document doc = new Document(MyDir + "Two color gradient.docx");

// Ottieni l'oggetto Fill per il carattere della prima esecuzione.
Fill fill = doc.FirstSection.Body.Paragraphs[0].Runs[0].Font.Fill;

// Controlla le proprietà di riempimento del carattere.
Console.WriteLine("The type of the fill is: {0}", fill.FillType);
Console.WriteLine("The foreground color of the fill is: {0}", fill.ForeColor);
Console.WriteLine("The fill is transparent at {0}%", fill.Transparency * 100);

// Cambia il tipo di riempimento in Solido con un colore verde uniforme.
fill.Solid(Color.Green);
Console.WriteLine("\nThe fill is changed:");
Console.WriteLine("The type of the fill is: {0}", fill.FillType);
Console.WriteLine("The foreground color of the fill is: {0}", fill.ForeColor);
Console.WriteLine("The fill transparency is {0}%", fill.Transparency * 100);

doc.Save(ArtifactsDir + "Drawing.FillSolid.docx");
```

### Guarda anche

* class [Fill](../)
* spazio dei nomi [Aspose.Words.Drawing](../../fill/)
* assemblea [Aspose.Words](../../../)


