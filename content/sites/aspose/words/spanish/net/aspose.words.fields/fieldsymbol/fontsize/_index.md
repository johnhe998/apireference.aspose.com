---
title: FieldSymbol.FontSize
second_title: Referencia de API de Aspose.Words para .NET
description: FieldSymbol propiedad. Obtiene o establece el tamaño en puntos de la fuente del carácter recuperado por el campo.
type: docs
weight: 50
url: /es/net/aspose.words.fields/fieldsymbol/fontsize/
---
## FieldSymbol.FontSize property

Obtiene o establece el tamaño en puntos de la fuente del carácter recuperado por el campo.

```csharp
public string FontSize { get; set; }
```

### Ejemplos

Muestra cómo utilizar el campo SÍMBOLO.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// A continuación se muestran tres formas de usar un campo SÍMBOLO para mostrar un solo carácter.
// 1 - Agregue un campo SÍMBOLO que muestre el símbolo © (Copyright), especificado por un código de carácter ANSI:
FieldSymbol field = (FieldSymbol)builder.InsertField(FieldType.FieldSymbol, true);

// El código de carácter ANSI "U+00A9", o "169" en formato entero, está reservado para el símbolo de copyright.
field.CharacterCode = 0x00a9.ToString();
field.IsAnsi = true;

Assert.AreEqual(" SYMBOL  169 \\a", field.GetFieldCode());

builder.Writeln(" Line 1");

// 2 - Agregue un campo SÍMBOLO que muestre el símbolo ∞ (Infinito) y modifique su apariencia:
field = (FieldSymbol)builder.InsertField(FieldType.FieldSymbol, true);

// En Unicode, el símbolo de infinito ocupa el código "221E".
field.CharacterCode = 0x221E.ToString();
field.IsUnicode = true;

// Cambiar la fuente de nuestro símbolo después de usar el Mapa de Caracteres de Windows
// para asegurarse de que la fuente pueda representar ese símbolo.
field.FontName = "Calibri";
field.FontSize = "24";

// Podemos configurar esta bandera para símbolos altos para que no empujen hacia abajo el resto del texto en su línea.
field.DontAffectsLineSpacing = true;

Assert.AreEqual(" SYMBOL  8734 \\u \\f Calibri \\s 24 \\h", field.GetFieldCode());

builder.Writeln("Line 2");

// 3 - Agregue un campo SÍMBOLO que muestre el carácter あ,
// con una fuente compatible con la página de códigos Shift-JIS (Windows-932):
field = (FieldSymbol)builder.InsertField(FieldType.FieldSymbol, true);
field.FontName = "MS Gothic";
field.CharacterCode = 0x82A0.ToString();
field.IsShiftJis = true;

Assert.AreEqual(" SYMBOL  33440 \\f \"MS Gothic\" \\j", field.GetFieldCode());

builder.Write("Line 3");

doc.Save(ArtifactsDir + "Field.SYMBOL.docx");
```

### Ver también

* class [FieldSymbol](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldsymbol/)
* asamblea [Aspose.Words](../../../)


