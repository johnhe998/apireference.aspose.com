---
title: Comment.Done
second_title: Aspose.Words für .NET-API-Referenz
description: Comment eigendom. Ruft oder setzt Flag das anzeigt dass der Kommentar als erledigt markiert wurde.
type: docs
weight: 50
url: /de/net/aspose.words/comment/done/
---
## Comment.Done property

Ruft oder setzt Flag, das anzeigt, dass der Kommentar als erledigt markiert wurde.

```csharp
public bool Done { get; set; }
```

### Beispiele

Zeigt, wie Sie einen Kommentar als „erledigt“ markieren.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Helo world!");

// Fügen Sie einen Kommentar ein, um auf einen Fehler hinzuweisen. 
Comment comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("Fix the spelling error!");
doc.FirstSection.Body.FirstParagraph.AppendChild(comment);

// Kommentare haben ein "Done"-Flag, das standardmäßig auf "false" gesetzt ist. 
// Wenn ein Kommentar darauf hindeutet, dass wir eine Änderung innerhalb des Dokuments vornehmen,
// Wir können die Änderung anwenden und anschließend auch das "Fertig"-Flag setzen, um die Korrektur anzuzeigen.
Assert.False(comment.Done);

doc.FirstSection.Body.FirstParagraph.Runs[0].Text = "Hello world!";
comment.Done = true;

// Kommentare, die "fertig" sind, unterscheiden sich
// von denen, die mit einer verblassten Textfarbe nicht "fertig" sind.
comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("Add text to this paragraph.");
builder.CurrentParagraph.AppendChild(comment);

doc.Save(ArtifactsDir + "Comment.Done.docx");
```

Zeigt, wie der Inhalt aller Kommentare und ihre Kommentarbereiche mithilfe eines Dokumentbesuchers gedruckt werden.

```csharp
public void CreateCommentsAndPrintAllInfo()
{
    Document doc = new Document();

    Comment newComment = new Comment(doc)
    {
        Author = "VDeryushev",
        Initial = "VD",
        DateTime = DateTime.Now
    };

    newComment.SetText("Comment regarding text.");

    // Fügen Sie dem Dokument Text hinzu, verzerren Sie es in einen Kommentarbereich und fügen Sie dann Ihren Kommentar hinzu.
    Paragraph para = doc.FirstSection.Body.FirstParagraph;
    para.AppendChild(new CommentRangeStart(doc, newComment.Id));
    para.AppendChild(new Run(doc, "Commented text."));
    para.AppendChild(new CommentRangeEnd(doc, newComment.Id));
    para.AppendChild(newComment); 

    // Dem Kommentar zwei Antworten hinzufügen.
    newComment.AddReply("John Doe", "JD", DateTime.Now, "New reply.");
    newComment.AddReply("John Doe", "JD", DateTime.Now, "Another reply.");

    PrintAllCommentInfo(doc.GetChildNodes(NodeType.Comment, true));
}

/// <summary>
/// Iteriert über jeden Kommentar der obersten Ebene und gibt dessen Kommentarbereich, Inhalt und Antworten aus.
/// </summary>
private static void PrintAllCommentInfo(NodeCollection comments)
{
    CommentInfoPrinter commentVisitor = new CommentInfoPrinter();

    // Über alle Kommentare der obersten Ebene iterieren. Im Gegensatz zu Kommentaren vom Antworttyp haben Kommentare auf oberster Ebene keinen Vorfahren.
    foreach (Comment comment in comments.Where(c => ((Comment)c).Ancestor == null))
    {
        // Besuchen Sie zuerst den Anfang des Kommentarbereichs.
        CommentRangeStart commentRangeStart = (CommentRangeStart)comment.PreviousSibling.PreviousSibling.PreviousSibling;
        commentRangeStart.Accept(commentVisitor);

        // Besuchen Sie dann den Kommentar und alle Antworten, die er möglicherweise enthält.
        comment.Accept(commentVisitor);

        foreach (Comment reply in comment.Replies)
            reply.Accept(commentVisitor);

        // Besuchen Sie schließlich das Ende des Kommentarbereichs und drucken Sie dann den Textinhalt des Besuchers aus.
        CommentRangeEnd commentRangeEnd = (CommentRangeEnd)comment.PreviousSibling;
        commentRangeEnd.Accept(commentVisitor);

        Console.WriteLine(commentVisitor.GetText());
    }
}

/// <summary>
/// Gibt Informationen und Inhalte aller Kommentare und Kommentarbereiche aus, die im Dokument vorkommen.
/// </summary>
public class CommentInfoPrinter : DocumentVisitor
{
    public CommentInfoPrinter()
    {
        mBuilder = new StringBuilder();
        mVisitorIsInsideComment = false;
    }

    /// <summary>
    /// Ruft den Klartext des Dokuments ab, das vom Besucher angesammelt wurde.
    /// </summary>
    public string GetText()
    {
        return mBuilder.ToString();
    }

    /// <summary>
    /// Wird aufgerufen, wenn im Dokument ein Run-Knoten gefunden wird.
    /// </summary>
    public override VisitorAction VisitRun(Run run)
    {
        if (mVisitorIsInsideComment) IndentAndAppendLine("[Run] \"" + run.Text + "\"");

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Wird aufgerufen, wenn im Dokument ein CommentRangeStart-Knoten gefunden wird.
    /// </summary>
    public override VisitorAction VisitCommentRangeStart(CommentRangeStart commentRangeStart)
    {
        IndentAndAppendLine("[Comment range start] ID: " + commentRangeStart.Id);
        mDocTraversalDepth++;
        mVisitorIsInsideComment = true;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Wird aufgerufen, wenn im Dokument ein CommentRangeEnd-Knoten gefunden wird.
    /// </summary>
    public override VisitorAction VisitCommentRangeEnd(CommentRangeEnd commentRangeEnd)
    {
        mDocTraversalDepth--;
        IndentAndAppendLine("[Comment range end] ID: " + commentRangeEnd.Id + "\n");
        mVisitorIsInsideComment = false;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Wird aufgerufen, wenn im Dokument ein Kommentarknoten gefunden wird.
    /// </summary>
    public override VisitorAction VisitCommentStart(Comment comment)
    {
        IndentAndAppendLine(
            $"[Comment start] For comment range ID {comment.Id}, By {comment.Author} on {comment.DateTime}");
        mDocTraversalDepth++;
        mVisitorIsInsideComment = true;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Wird aufgerufen, wenn der Besuch eines Kommentarknotens im Dokument beendet wird.
    /// </summary>
    public override VisitorAction VisitCommentEnd(Comment comment)
    {
        mDocTraversalDepth--;
        IndentAndAppendLine("[Comment end]");
        mVisitorIsInsideComment = false;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Eine Zeile an den StringBuilder anhängen und einrücken, je nachdem, wie tief der Besucher in den Dokumentenbaum eindringt.
    /// </summary>
    /// <param name="text"></param>
    private void IndentAndAppendLine(string text)
    {
        for (int i = 0; i < mDocTraversalDepth; i++)
        {
            mBuilder.Append("|  ");
        }

        mBuilder.AppendLine(text);
    }

    private bool mVisitorIsInsideComment;
    private int mDocTraversalDepth;
    private readonly StringBuilder mBuilder;
}
```

### Siehe auch

* class [Comment](../)
* namensraum [Aspose.Words](../../comment/)
* Montage [Aspose.Words](../../../)


