---
title: ComHelper.ComHelper
second_title: Справочник по API Aspose.Words для .NET
description: ComHelper строитель. Инициализирует новый экземпляр этого класса.
type: docs
weight: 10
url: /ru/net/aspose.words/comhelper/comhelper/
---
## ComHelper constructor

Инициализирует новый экземпляр этого класса.

```csharp
public ComHelper()
```

### Примеры

Показывает, как открывать документы с помощью класса ComHelper.

```csharp
// Класс ComHelper позволяет нам загружать документы из COM-клиентов.
ComHelper comHelper = new ComHelper();

// 1 - Использование локального системного имени файла:
Document doc = comHelper.Open(MyDir + "Document.docx");

Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", doc.GetText().Trim());

// 2 - Из потока:
using (FileStream stream = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    doc = comHelper.Open(stream);

    Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", doc.GetText().Trim());
}
```

### Смотрите также

* class [ComHelper](../)
* пространство имен [Aspose.Words](../../comhelper/)
* сборка [Aspose.Words](../../../)


