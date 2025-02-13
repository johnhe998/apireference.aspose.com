---
title: License.License
second_title: Aspose.Words for .NET API 参考
description: License 构造函数. 初始化这个类的一个新实例
type: docs
weight: 10
url: /zh/net/aspose.words/license/license/
---
## License constructor

初始化这个类的一个新实例。

```csharp
public License()
```

### 例子

展示如何使用本地文件系统中的许可证文件为 Aspose.Words 初始化许可证。

```csharp
// 通过传递有效许可证文件的本地文件系统文件名，为我们的 Aspose.Words 产品设置许可证。
string licenseFileName = Path.Combine(LicenseDir, "Aspose.Words.NET.lic");

License license = new License();
license.SetLicense(licenseFileName);

// 在应用程序的二进制文件夹中创建许可证文件的副本。
string licenseCopyFileName = Path.Combine(AssemblyDir, "Aspose.Words.NET.lic");
File.Copy(licenseFileName, licenseCopyFileName);

// 如果我们传递一个没有路径的文件名，
// SetLicense 将为此文件搜索多个本地文件系统位置。
// 其中一个位置是“bin”文件夹，其中包含我们的许可证文件的副本。
license.SetLicense("Aspose.Words.NET.lic");
```

### 也可以看看

* class [License](../)
* 命名空间 [Aspose.Words](../../license/)
* 部件 [Aspose.Words](../../../)


