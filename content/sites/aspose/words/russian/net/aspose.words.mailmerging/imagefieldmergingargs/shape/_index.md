---
title: ImageFieldMergingArgs.Shape
second_title: Справочник по API Aspose.Words для .NET
description: ImageFieldMergingArgs свойство. Указывает форму которую механизм слияния должен вставить в документ.
type: docs
weight: 60
url: /ru/net/aspose.words.mailmerging/imagefieldmergingargs/shape/
---
## ImageFieldMergingArgs.Shape property

Указывает форму, которую механизм слияния должен вставить в документ.

```csharp
public Shape Shape { get; set; }
```

### Примечания

Когда это свойство указано, механизм слияния игнорирует все другие свойства, такие как[`ImageFileName`](../imagefilename/) или же[`ImageStream`](../imagestream/) и просто вставляет фигуру в документ.

Используйте это свойство, чтобы полностью контролировать процесс слияния поля слияния изображений. Например, вы можете указать[`WrapType`](../../../aspose.words.drawing/shapebase/wraptype/)или любое другое свойство формы для точной настройки результирующего узла. Однако обратите внимание, что вы несете ответственность за предоставление содержимого формы.

### Смотрите также

* class [Shape](../../../aspose.words.drawing/shape/)
* class [ImageFieldMergingArgs](../)
* пространство имен [Aspose.Words.MailMerging](../../imagefieldmergingargs/)
* сборка [Aspose.Words](../../../)


