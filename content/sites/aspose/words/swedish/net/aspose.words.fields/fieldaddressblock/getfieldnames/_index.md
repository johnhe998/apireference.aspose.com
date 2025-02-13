---
title: FieldAddressBlock.GetFieldNames
second_title: Aspose.Words för .NET API Referens
description: FieldAddressBlock metod. Returnerar en samling av kopplingsfältnamn som används av fältet.
type: docs
weight: 70
url: /sv/net/aspose.words.fields/fieldaddressblock/getfieldnames/
---
## FieldAddressBlock.GetFieldNames method

Returnerar en samling av kopplingsfältnamn som används av fältet.

```csharp
public string[] GetFieldNames()
```

### Exempel

Visar hur man får kopplingsfältnamn som används av ett fält.

```csharp
Document doc = new Document(MyDir + "Field sample - ADDRESSBLOCK.docx");

string[] addressFieldsExpect =
{
    "Company", "First Name", "Middle Name", "Last Name", "Suffix", "Address 1", "City", "State",
    "Country or Region", "Postal Code"
};

FieldAddressBlock addressBlockField = (FieldAddressBlock) doc.Range.Fields[0];
string[] addressBlockFieldNames = addressBlockField.GetFieldNames();
```

### Se även

* class [FieldAddressBlock](../)
* namnutrymme [Aspose.Words.Fields](../../fieldaddressblock/)
* hopsättning [Aspose.Words](../../../)


