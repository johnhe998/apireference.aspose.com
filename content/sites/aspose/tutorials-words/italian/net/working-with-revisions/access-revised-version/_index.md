---
title: Accedi alla versione rivista
linktitle: Accedi alla versione rivista
second_title: Aspose.Words API di elaborazione dei documenti
description: Accedi a una versione rivista di un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/access-revised-version/
---

In questa guida dettagliata, ti mostreremo come accedere alla versione rivista di un documento Word utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output del markdown.

## Passaggio 1: caricamento del documento

Il primo passo è caricare il documento contenente le revisioni.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Passaggio 2: accedere alla versione rivista

Passiamo ora alla versione riveduta del documento.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Passaggio 3: sfoglia le revisioni

Successivamente, passeremo in rassegna le revisioni presenti nel documento e visualizzeremo informazioni specifiche per i paragrafi che sono voci di elenco.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Esempio di codice sorgente per Access Revised Version utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per accedere alla versione rivista di un documento utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Passa alla versione rivista del documento.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## Conclusione

In questo tutorial, abbiamo imparato come accedere alla versione rivista di un documento Word utilizzando Aspose.Words per .NET. Caricando il documento, passando alla versione rivista e sfogliando le revisioni, siamo stati in grado di ottenere informazioni specifiche per i paragrafi che sono voci di elenco. Aspose.Words per .NET offre potenti funzionalità per la manipolazione di documenti Word, incluso l'accesso alle revisioni. Ora puoi utilizzare questa conoscenza per accedere alla versione rivista dei tuoi documenti Word utilizzando Aspose.Words per .NET.

### FAQ

#### D: Come faccio a caricare un documento con le revisioni in Aspose.Words per .NET?

 R: Usa il`Document`class di Aspose.Words per .NET per caricare un documento da un file contenente revisioni. È possibile specificare il percorso completo del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### D: Come accedo alla versione rivista di un documento in Aspose.Words per .NET?

 R: Usa il`RevisionsView`proprietà del`Document` opporsi all'accesso alla versione riveduta del documento. È possibile impostare il valore di`RevisionsView` proprietà a`RevisionsView.Final` per mostrare la versione finale senza le revisioni.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### D: Come faccio a sfogliare le revisioni dei documenti in Aspose.Words per .NET?

 R: Usa a`foreach` loop per scorrere le revisioni presenti nel documento. Puoi usare il`Revisions`proprietà del`Document` object per ottenere una raccolta di tutte le revisioni del documento.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Elabora ogni revisione qui
}
```

#### D: Come verificare se un paragrafo è una voce di elenco in Aspose.Words per .NET?

 R: Usa il`IsListItem`proprietà del`Paragraph` oggetto per controllare se un paragrafo è un elemento di elenco. IL`IsListItem` resi di proprietà`true` se il paragrafo è un elemento di elenco, altrimenti ritorna`false`.

```csharp
if (paragraph.IsListItem)
{
     // Il paragrafo è una voce di elenco
}
else
{
     // Il paragrafo non è una voce di elenco
}
```