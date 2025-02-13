---
title: ComHelper.Open
second_title: Справочник по API Aspose.Words для .NET
description: ComHelper метод. Позволяет приложению COM загружатьDocument из файла .
type: docs
weight: 20
url: /ru/net/aspose.words/comhelper/open/
---
## Open(string) {#open_1}

Позволяет приложению COM загружать[`Document`](../../document/) из файла .

```csharp
public Document Open(string fileName)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| fileName | String | Имя файла документа для загрузки. |

### Возвращаемое значение

А[`Document`](../../document/) объект, представляющий документ Word.

### Примечания

Этот метод аналогичен вызову[`Document`](../../document/) конструктор с параметром имени файла.

### Примеры

```csharp
[VBScript]

Dim helper
Set helper = CreateObject("Aspose.Words.ComHelper")

Dim doc
Set doc = helper.Open(fileName)
```

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

* class [Document](../../document/)
* class [ComHelper](../)
* пространство имен [Aspose.Words](../../comhelper/)
* сборка [Aspose.Words](../../../)

---

## Open(Stream) {#open}

Разрешает загрузку приложения COM[`Document`](../../document/) из потока.

```csharp
public Document Open(Stream stream)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| stream | Stream | Объект потока .NET, содержащий загружаемый документ. |

### Возвращаемое значение

А[`Document`](../../document/) объект, представляющий документ Word.

### Примечания

Этот метод аналогичен вызову[`Document`](../../document/) конструктор с параметром потока.

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

* class [Document](../../document/)
* class [ComHelper](../)
* пространство имен [Aspose.Words](../../comhelper/)
* сборка [Aspose.Words](../../../)


