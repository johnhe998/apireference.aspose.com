---
title: HtmlSaveOptions.ExportFontResources
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlSaveOptions eigendom. Gibt an ob Schriftressourcen in HTML MHTML oder EPUB exportiert werden sollen. Standard istFALSCH .
type: docs
weight: 150
url: /de/net/aspose.words.saving/htmlsaveoptions/exportfontresources/
---
## HtmlSaveOptions.ExportFontResources property

Gibt an, ob Schriftressourcen in HTML, MHTML oder EPUB exportiert werden sollen. Standard ist`FALSCH` .

```csharp
public bool ExportFontResources { get; set; }
```

### Bemerkungen

Das Exportieren von Font-Ressourcen ermöglicht eine konsistente Dokumentwiedergabe unabhängig von den verfügbaren Fonts in der Umgebung eines bestimmten Benutzers.

Wenn`ExportFontResources` ist eingestellt auf`Stimmt` , Haupt-HTML-Dokument verweist auf jede Schriftart über das CSS 3 **@Schriftart**at-Regel und Schriftarten werden als separate Dateien ausgegeben. Beim Exportieren in die Formate IDPF EPUB oder MHTML werden Schriftarten zusammen mit anderen untergeordneten Dateien in das entsprechende Paket eingebettet.

Wenn[`ExportFontsAsBase64`](../exportfontsasbase64/) ist eingestellt auf`Stimmt` , Schriftarten werden nicht in separaten Dateien gespeichert. Stattdessen werden sie in eingebettet **@Schriftart** at-Regeln in Base64-Codierung.

**Wichtig!** Beim Exportieren von Zeichensatzressourcen sollten Probleme mit der Zeichensatzlizenzierung berücksichtigt werden. Autoren, die bestimmte Schriftarten über einen herunterladbaren -Schriftartmechanismus verwenden möchten, müssen immer sorgfältig prüfen, ob ihre beabsichtigte Verwendung im Umfang der Schriftartlizenz liegt. Viele kommerzielle Schriftarten erlauben derzeit nicht das Herunterladen ihrer Schriftarten aus dem Internet in irgendeiner Form. Lizenzvereinbarungen, die einige Schriftarten abdecken, weisen ausdrücklich darauf hin, dass die Verwendung über **@Schriftart** rules in CSS-Stylesheets ist nicht erlaubt. Schriftuntergruppen können auch gegen Lizenzbedingungen verstoßen.

### Beispiele

Zeigt, wie benutzerdefinierte Logik zum Exportieren von Schriftarten beim Speichern in HTML definiert wird.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Konfigurieren Sie ein SaveOptions-Objekt, um Schriftarten in separate Dateien zu exportieren.
    // Festlegen eines Rückrufs, der das Speichern von Schriftarten auf benutzerdefinierte Weise handhabt.
    HtmlSaveOptions options = new HtmlSaveOptions
    {
        ExportFontResources = true,
        FontSavingCallback = new HandleFontSaving()
    };

    // Der Callback exportiert .ttf-Dateien und speichert sie zusammen mit dem Ausgabedokument.
    doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveExportedFonts.html", options);

    foreach (string fontFilename in Array.FindAll(Directory.GetFiles(ArtifactsDir), s => s.EndsWith(".ttf")))
    {
        Console.WriteLine(fontFilename);
    }

/// <summary>
/// Druckt Informationen über exportierte Schriftarten und speichert sie im selben lokalen Systemordner wie ihre Ausgabe-.html.
/// </summary>
public class HandleFontSaving : IFontSavingCallback
{
    void IFontSavingCallback.FontSaving(FontSavingArgs args)
    {
        Console.Write($"Font:\t{args.FontFamilyName}");
        if (args.Bold) Console.Write(", bold");
        if (args.Italic) Console.Write(", italic");
        Console.WriteLine($"\nSource:\t{args.OriginalFileName}, {args.OriginalFileSize} bytes\n");

        // Von hier aus können wir auch auf das Quelldokument zugreifen.
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        Assert.True(args.IsExportNeeded);
        Assert.True(args.IsSubsettingNeeded);

        // Es gibt zwei Möglichkeiten, einen exportierten Font zu speichern.
        // 1 - Speichern Sie es an einem lokalen Speicherort im Dateisystem:
        args.FontFileName = args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last();

        // 2 - Speichern Sie es in einem Stream:
        args.FontStream =
            new FileStream(ArtifactsDir + args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last(), FileMode.Create);
        Assert.False(args.KeepFontStreamOpen);
    }
}
```

### Siehe auch

* class [HtmlSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlsaveoptions/)
* Montage [Aspose.Words](../../../)


