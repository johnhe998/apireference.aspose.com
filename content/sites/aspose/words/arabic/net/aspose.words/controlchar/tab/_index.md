---
title: ControlChar.Tab
second_title: Aspose.Words لمراجع .NET API
description: ControlChar مجال. حرف الجدولة  x0009 أو  t .
type: docs
weight: 270
url: /ar/net/aspose.words/controlchar/tab/
---
## ControlChar.Tab field

حرف الجدولة: "\ x0009" أو "\ t" .

```csharp
public static readonly string Tab;
```

### أمثلة

يوضح كيفية تعيين فاصل زمني مخصص لمواضع علامات الجدولة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// تعيين علامات الجدولة لتظهر كل 72 نقطة (1 بوصة).
builder.Document.DefaultTabStop = 72;

// يقوم كل حرف جدولة بمحاذاة النص بعده إلى أقرب موضع علامة جدولة تالية.
builder.Writeln("Hello" + ControlChar.Tab + "World!");
builder.Writeln("Hello" + ControlChar.TabChar + "World!");
```

### أنظر أيضا

* class [ControlChar](../)
* مساحة الاسم [Aspose.Words](../../controlchar/)
* المجسم [Aspose.Words](../../../)


