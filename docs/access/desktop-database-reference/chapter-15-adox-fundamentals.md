---
title: 第 15 章：ADOX 基础知识
TOCTitle: 'Chapter 15: ADOX fundamentals'
ms:assetid: 973d7579-4f34-3b31-a761-a951ab29e850
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249673(v=office.15)
ms:contentKeyID: 48546464
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0e46920ba47dba018944768ff61c970781e37a02
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720973"
---
# <a name="chapter-15-adox-fundamentals"></a>第 15 章：ADOX 基础知识

**适用于**： Access 2013、 Office 2013

用于数据定义语言和安全性的 Microsoft ActiveX 数据对象扩展 (ADOX) 是 ADO 对象和编程模型的扩展。ADOX 包括用于创建和修改架构以及安全性的对象。由于它基于对象来实现对架构的操控，因此您可以编写代码来处理各类数据源，而无需考虑数据源本来的语法之间的差异。

ADOX 是核心 ADO 对象的配套库。它提供了用于创建、修改和删除架构对象（如表和过程）的附加对象，还提供了用于维护用户和组以及用于授予和撤消对象权限的安全对象。

若要将 ADOX 用于您的开发工具，应建立对 ADOX 类型库的引用。ADOX 库的描述为"Microsoft ADO Ext. for DDL and Security"。ADOX 库的文件名为 Msadox.dll，程序 ID (ProgID) 为"ADOX"。有关如何建立库引用的更多信息，请参阅您的开发工具文档。

Microsoft OLE DB Provider for Microsoft Jet Database Engine 完全支持 ADOX。ADOX 的某些功能可能不受支持，这取决于您的数据提供程序。有关 Microsoft OLE DB Provider for ODBC、Microsoft OLE DB Provider for Oracle 或 Microsoft SQL Server OLE DB Provider 支持的功能的更多信息，请参阅 MDAC 自述文件。

本文档假定使用知识的 Microsoft Visual Basic 编程语言和 ADO 的常规知识。 有关 ADO 的详细信息，请参阅[ADO 程序员指南 》](ado-programmer-s-guide.md)。

本章包括以下主题：

- [ADOX 的提供程序支持](provider-support-for-adox.md)

有关 ADOX 的更多概述信息，请参阅下列主题：

- [ADOX 对象](adox-objects.md)
- [ADOX 集合](adox-collections.md)
- [ADOX 属性](adox-properties.md)
- [ADOX 方法](adox-methods.md)
- [ADOX 示例](adox-code-examples.md)

