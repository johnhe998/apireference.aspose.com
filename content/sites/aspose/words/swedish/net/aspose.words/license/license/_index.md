---
title: License.License
second_title: Aspose.Words för .NET API Referens
description: License byggare. Initierar en ny instans av den här klassen.
type: docs
weight: 10
url: /sv/net/aspose.words/license/license/
---
## License constructor

Initierar en ny instans av den här klassen.

```csharp
public License()
```

### Exempel

Visar hur man initierar en licens för Aspose.Words med hjälp av en licensfil i det lokala filsystemet.

```csharp
// Ställ in licensen för vår Aspose.Words-produkt genom att skicka det lokala filsystemets filnamn för en giltig licensfil.
string licenseFileName = Path.Combine(LicenseDir, "Aspose.Words.NET.lic");

License license = new License();
license.SetLicense(licenseFileName);

// Skapa en kopia av vår licensfil i mappen binärer i vår applikation.
string licenseCopyFileName = Path.Combine(AssemblyDir, "Aspose.Words.NET.lic");
File.Copy(licenseFileName, licenseCopyFileName);

// Om vi skickar ett filnamn utan en sökväg,
// SetLicense kommer att söka på flera lokala filsystemplatser för denna fil.
// En av dessa platser kommer att vara mappen "bin", som innehåller en kopia av vår licensfil.
license.SetLicense("Aspose.Words.NET.lic");
```

### Se även

* class [License](../)
* namnutrymme [Aspose.Words](../../license/)
* hopsättning [Aspose.Words](../../../)


