---
title: FindReplaceOptions.FindWholeWordsOnly
second_title: Aspose.Words for .NET API Referansı
description: FindReplaceOptions mülk. True eskiDeğerin bağımsız bir sözcük olması gerektiğini belirtir.
type: docs
weight: 50
url: /tr/net/aspose.words.replacing/findreplaceoptions/findwholewordsonly/
---
## FindReplaceOptions.FindWholeWordsOnly property

True, eskiDeğerin bağımsız bir sözcük olması gerektiğini belirtir.

```csharp
public bool FindWholeWordsOnly { get; set; }
```

### Örnekler

Yalnızca sözcükten oluşan bağımsız bul ve değiştir işlemlerinin nasıl değiştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jackson will meet you in Jacksonville.");

// Bul ve değiştir işlemini değiştirmek için bir "FindReplaceOptions" nesnesi kullanabiliriz.
FindReplaceOptions options = new FindReplaceOptions();

// Bulunan metni başka bir kelimenin parçası değilse değiştirmek için "FindWholeWordsOnly" bayrağını "true" olarak ayarlayın.
// Çevresinden bağımsız olarak tüm metni değiştirmek için "FindWholeWordsOnly" bayrağını "false" olarak ayarlayın.
options.FindWholeWordsOnly = findWholeWordsOnly;

doc.Range.Replace("Jackson", "Louis", options);

Assert.AreEqual(
    findWholeWordsOnly ? "Louis will meet you in Jacksonville." : "Louis will meet you in Louisville.",
    doc.GetText().Trim());
```

### Ayrıca bakınız

* class [FindReplaceOptions](../)
* ad alanı [Aspose.Words.Replacing](../../findreplaceoptions/)
* toplantı [Aspose.Words](../../../)


