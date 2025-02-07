---
title: Class FileCorruptedException
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.FileCorruptedException 班级. 在文档加载期间抛出当文档似乎已损坏且无法加载时
type: docs
weight: 2620
url: /zh/net/aspose.words/filecorruptedexception/
---
## FileCorruptedException class

在文档加载期间抛出，当文档似乎已损坏且无法加载时。

```csharp
public class FileCorruptedException : Exception
```

### 例子

演示如何捕获 FileCorruptedException。

```csharp
try
{
    // 如果我们在尝试使用 Microsoft Word 打开文档时收到“不可读的内容”错误消息，
    // 尝试使用 Aspose.Words 加载该文档时，我们可能会抛出异常。
    Document doc = new Document(MyDir + "Corrupted document.docx");
}
catch (FileCorruptedException e)
{
    Console.WriteLine(e.Message);
}
```

### 也可以看看

* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


