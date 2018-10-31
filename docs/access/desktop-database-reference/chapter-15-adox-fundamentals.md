---
title: 第 15 章：ADOX 基础知识
TOCTitle: 'Chapter 15: ADOX Fundamentals'
ms:assetid: 973d7579-4f34-3b31-a761-a951ab29e850
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249673(v=office.15)
ms:contentKeyID: 48546464
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 362fd0784ee596852af7b16fae5636330a52ed59
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25863743"
---
# <a name="chapter-15-adox-fundamentals"></a>第 15 章：ADOX 基础知识


**适用于**： Access 2013 |Office 2013

数据定义语言和安全性 Microsoft® ActiveX® 数据对象扩展 (ADOX) 是对 ADO 对象以及编程模型的扩展。ADOX 包含用于架构创建和修改的对象，以及用于安全性的对象。由于这是一种基于对象的架构处理方法，因此您可以编写可用于各种数据源的代码，而无需考虑这些数据源的特有语法。

ADOX 是核心 ADO 对象的配套库。它提供了用于创建、修改和删除架构对象（如表和过程）的附加对象，还提供了用于维护用户和组以及用于授予和撤消对象权限的安全对象。

若要将 ADOX 用于您的开发工具，应建立对 ADOX 类型库的引用。ADOX 库的描述为"Microsoft ADO Ext. for DDL and Security"。ADOX 库的文件名为 Msadox.dll，程序 ID (ProgID) 为"ADOX"。有关如何建立库引用的更多信息，请参阅您的开发工具文档。

Microsoft OLE DB Provider for Microsoft Jet Database Engine 完全支持 ADOX。ADOX 的某些功能可能不受支持，这取决于您的数据提供程序。有关 Microsoft OLE DB Provider for ODBC、Microsoft OLE DB Provider for Oracle 或 Microsoft SQL Server OLE DB Provider 支持的功能的更多信息，请参阅 MDAC 自述文件。

本文档需要对 Microsoft® Visual Basic® 编程语言的实用知识以及对 ADO 的一般性了解。 有关 ADO 的更多信息，请参阅 [ADO 程序员指南](ado-programmer-s-guide.md)。

本章包括以下主题：

- [ADOX 的提供程序支持](provider-support-for-adox.md)

有关 ADOX 的更多概述信息，请参阅下列主题：

- [ADOX 对象](adox-objects.md)

- [ADOX 集合](adox-collections.md)

- [ADOX 属性](adox-properties.md)

- [ADOX 方法](adox-methods.md)

- [ADOX 示例](adox-code-examples.md)

