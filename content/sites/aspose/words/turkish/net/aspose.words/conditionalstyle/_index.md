---
title: Class ConditionalStyle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.ConditionalStyle sınıf. Tablo stili atanmış bir tablonun bazı alanlarına uygulanan özel biçimlendirmeyi temsil eder.
type: docs
weight: 300
url: /tr/net/aspose.words/conditionalstyle/
---
## ConditionalStyle class

Tablo stili atanmış bir tablonun bazı alanlarına uygulanan özel biçimlendirmeyi temsil eder.

```csharp
public sealed class ConditionalStyle
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Borders](../../aspose.words/conditionalstyle/borders/) { get; } | Koşullu stil için varsayılan hücre kenarlıkları koleksiyonunu alır. |
| [BottomPadding](../../aspose.words/conditionalstyle/bottompadding/) { get; set; } | Tablo hücrelerinin içeriğinin altına eklenecek boşluk miktarını (puan olarak) alır veya ayarlar. |
| [Font](../../aspose.words/conditionalstyle/font/) { get; } | Koşullu stilin karakter biçimlendirmesini alır. |
| [LeftPadding](../../aspose.words/conditionalstyle/leftpadding/) { get; set; } | Tablo hücrelerinin içeriğinin soluna eklenecek boşluk miktarını (puan olarak) alır veya ayarlar. |
| [ParagraphFormat](../../aspose.words/conditionalstyle/paragraphformat/) { get; } | Koşullu stilin paragraf biçimlendirmesini alır. |
| [RightPadding](../../aspose.words/conditionalstyle/rightpadding/) { get; set; } | Tablo hücrelerinin içeriğinin sağına eklenecek boşluk miktarını (puan olarak) alır veya ayarlar. |
| [Shading](../../aspose.words/conditionalstyle/shading/) { get; } | [`Shading`](../shading/) bu koşullu stil için gölgeleme biçimlendirmesine başvuran nesne. |
| [TopPadding](../../aspose.words/conditionalstyle/toppadding/) { get; set; } | Tablo hücrelerinin içeriğinin üzerine eklenecek boşluk miktarını (puan olarak) alır veya ayarlar. |
| [Type](../../aspose.words/conditionalstyle/type/) { get; } | Bu koşullu stilin ilgili olduğu tablo alanını alır. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [ClearFormatting](../../aspose.words/conditionalstyle/clearformatting/)() | Bu koşullu stilin biçimlendirmesini temizler. |
| override [Equals](../../aspose.words/conditionalstyle/equals/)(object) |  |
| override [GetHashCode](../../aspose.words/conditionalstyle/gethashcode/)() | Bu nesne için karma kodu hesaplar. |

### Örnekler

Bir tablonun belirli alan stilleriyle nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Cell 1");
builder.InsertCell();
builder.Write("Cell 2");
builder.EndRow();
builder.InsertCell();
builder.Write("Cell 3");
builder.InsertCell();
builder.Write("Cell 4");
builder.EndTable();

// Özel bir tablo stili oluşturun.
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");

// Koşullu stiller, tablo hücrelerinin yalnızca bazılarını etkileyen biçimlendirme değişiklikleridir.
// hücrelerin son satırda olması gibi bir yüklemi temel alır.
// Aşağıda, "ConditionalStyles" koleksiyonundan bir tablo stilinin koşullu stillerine erişmenin üç yolu bulunmaktadır.
// 1 - Stil türüne göre:
tableStyle.ConditionalStyles[ConditionalStyleType.FirstRow].Shading.BackgroundPatternColor = Color.AliceBlue;

// 2 - Dizine göre:
tableStyle.ConditionalStyles[0].Borders.Color = Color.Black;
tableStyle.ConditionalStyles[0].Borders.LineStyle = LineStyle.DotDash;
Assert.AreEqual(ConditionalStyleType.FirstRow, tableStyle.ConditionalStyles[0].Type);

// 3 - Özellik olarak:
tableStyle.ConditionalStyles.FirstRow.ParagraphFormat.Alignment = ParagraphAlignment.Center;

// Koşullu stillere dolgu ve metin biçimlendirme uygulayın.
tableStyle.ConditionalStyles.LastRow.BottomPadding = 10;
tableStyle.ConditionalStyles.LastRow.LeftPadding = 10;
tableStyle.ConditionalStyles.LastRow.RightPadding = 10;
tableStyle.ConditionalStyles.LastRow.TopPadding = 10;
tableStyle.ConditionalStyles.LastColumn.Font.Bold = true;

// Tüm olası stil koşullarını listeleyin.
using (IEnumerator<ConditionalStyle> enumerator = tableStyle.ConditionalStyles.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        ConditionalStyle currentStyle = enumerator.Current;
        if (currentStyle != null) Console.WriteLine(currentStyle.Type);
    }
}

// Tüm koşullu stilleri içeren özel stili tabloya uygulayın.
table.Style = tableStyle;

// Stilimiz, varsayılan olarak bazı koşullu stilleri uygular.
Assert.AreEqual(TableStyleOptions.FirstRow | TableStyleOptions.FirstColumn | TableStyleOptions.RowBands, 
    table.StyleOptions);

// "StyleOptions" özelliği aracılığıyla diğer tüm stilleri kendimiz etkinleştirmemiz gerekecek.
table.StyleOptions = table.StyleOptions | TableStyleOptions.LastRow | TableStyleOptions.LastColumn;

doc.Save(ArtifactsDir + "Table.ConditionalStyles.docx");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


