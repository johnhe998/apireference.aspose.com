---
title: Class XmlDataSource
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Reporting.XmlDataSource sınıf. Bir raporda kullanılacak bir XML dosyası veya akışının verilerine erişim sağlar.
type: docs
weight: 4490
url: /tr/net/aspose.words.reporting/xmldatasource/
---
## XmlDataSource class

Bir raporda kullanılacak bir XML dosyası veya akışının verilerine erişim sağlar.

```csharp
public class XmlDataSource
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [XmlDataSource](xmldatasource/#constructor)(Stream) | XML veri yükleme için varsayılan seçenekleri kullanarak bir XML akışından gelen verilerle yeni bir veri kaynağı oluşturur. |
| [XmlDataSource](xmldatasource/#constructor_4)(string) | XML verilerinin yüklenmesi için varsayılan seçenekleri kullanarak bir XML dosyasındaki verilerle yeni bir veri kaynağı oluşturur. |
| [XmlDataSource](xmldatasource/#constructor_2)(Stream, Stream) | Bir XML Şema Tanımı akışı kullanarak bir XML akışından gelen verilerle yeni bir veri kaynağı oluşturur. XML verilerinin yüklenmesi için varsayılan options kullanılır. |
| [XmlDataSource](xmldatasource/#constructor_1)(Stream, XmlDataLoadOptions) | Belirtilen XML veri yükleme seçeneklerini kullanarak bir XML akışındaki verilerle yeni bir veri kaynağı oluşturur. |
| [XmlDataSource](xmldatasource/#constructor_6)(string, string) | Bir XML Şema Tanımı dosyası kullanarak bir XML dosyasındaki verilerle yeni bir veri kaynağı oluşturur. XML verilerinin yüklenmesi için varsayılan options kullanılır. |
| [XmlDataSource](xmldatasource/#constructor_5)(string, XmlDataLoadOptions) | Belirtilen XML veri yükleme seçeneklerini kullanarak bir XML dosyasındaki verilerle yeni bir veri kaynağı oluşturur. |
| [XmlDataSource](xmldatasource/#constructor_3)(Stream, Stream, XmlDataLoadOptions) | Bir XML Şema Tanımı akışı kullanarak bir XML akışından gelen verilerle yeni bir veri kaynağı oluşturur. Belirtilen seçenekleri, XML verilerinin yüklenmesi için kullanılır. |
| [XmlDataSource](xmldatasource/#constructor_7)(string, string, XmlDataLoadOptions) | Bir XML Şema Tanımı dosyası kullanarak bir XML dosyasındaki verilerle yeni bir veri kaynağı oluşturur. Belirtilen seçenekleri, XML verilerinin yüklenmesi için kullanılır. |

### Notlar

Bir rapor oluştururken ilgili dosyanın veya akışın verilerine erişmek için, bu sınıfın bir örneğini veri kaynağı olarak aşağıdakilerden birine iletin:[`ReportingEngine`](../reportingengine/) .BuildReport aşırı yükleniyor.

Şablon belgelerinde, üst düzey bir XML öğesi yalnızca aynı türdeki öğelerin bir listesini içeriyorsa, an`XmlDataSource` örneğe a olduğu gibi davranılmalıdırDataTable örneği. Aksi takdirde, bir`XmlDataSource` örneğe a olduğu gibi davranılmalıdırDataRow örneği. Daha fazla bilgi için şablon sözdizimi referansına bakın (https://docs.aspose.com/display/wordsnet/Template+Syntax).

Bu sınıfın bir yapıcısına XML Schema Definition geçirildiğinde, basit XML öğelerinin değerlerinin veri türleri ve öznitelikler şemaya göre belirlenir. Böylece şablon belgelerde, yalnızca dizeler yerine yazılan değerlerle çalışabilirsiniz.

XML Schema Definition bu sınıfın bir yapıcısına iletilmediğinde, basit XML öğelerinin değerlerinin veri türleri ve öznitelikleri, dize temsillerine göre otomatik olarak belirlenir. Yani şablon belgelerde, bu durumda da yazılan değerlerle çalışabilirsiniz. Motor, aşağıdaki türlerin değerlerini otomatik olarak tanıyabilir:

* Nullable
* Nullable
* Nullable
* Nullable
* String

Veri türlerinin otomatik olarak tanınmasının çalışması için, basit XML öğelerinin değerlerinin dize temsillerinin ve değişmez kültür ayarları kullanılarak oluşturulması gerektiğini unutmayın.

XML veri yüklemesinin varsayılan davranışını geçersiz kılmak için, bir[`XmlDataLoadOptions`](../xmldataloadoptions/) örneği bu sınıfın bir yapıcısına.

### Ayrıca bakınız

* ad alanı [Aspose.Words.Reporting](../../aspose.words.reporting/)
* toplantı [Aspose.Words](../../)


