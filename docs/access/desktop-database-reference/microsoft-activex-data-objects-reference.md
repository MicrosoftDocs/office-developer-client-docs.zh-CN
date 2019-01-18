---
title: Microsoft ActiveX 数据对象引用
TOCTitle: Microsoft ActiveX Data Objects Reference
ms:assetid: 235fc575-8a2e-913c-fa3d-bb86256733f9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249010(v=office.15)
ms:contentKeyID: 48543728
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: c1fee657c0d6ecd319157f704df2b1c5a900be3b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698881"
---
# <a name="microsoft-activex-data-objects-reference"></a>Microsoft ActiveX 数据对象引用

**适用于**： Access 2013、 Office 2013

## <a name="purpose"></a>目的

Microsoft ActiveX 数据对象 (ADO) 使您的客户端应用程序可以通过 OLE DB 提供程序访问和操控数据库服务器中的数据。 它的主要优点是简单易用、高速、内存开销低和磁盘占用小。 ADO 支持用于生成客户端/服务器和基于 web 的应用程序的主要功能。

## <a name="rds"></a>RDS

ADO 还提供了远程数据服务 (RDS)，可以通过其移动数据从服务器到客户端应用程序或网页，操作在客户端上的数据和往返返回到在单个服务器的更新。

## <a name="ado-md"></a>ADO MD

使用 Microsoft ActiveX 数据对象（多维）(ADO MD) 可以通过如 Microsoft Visual Basic、Microsoft Visual C++ 和 Microsoft Visual J++ 这样的语言轻松访问多维数据。ADO MD 扩展了 Microsoft ActiveX 数据对象 (ADO)，将特定于多维数据的对象（如 CubeDef 和 Cellset 对象）包括在其中。利用 ADO MD，您可以浏览多维架构，查询多维数据集，并检索结果。

与 ADO 相仿，ADO MD 也使用基础 OLE DB 提供程序来获得对数据的访问。为了使用 ADO MD，您的提供程序必须是 OLE DB for OLAP 规范所定义的多维数据提供程序 (MDP)。MDP 以多维视图显示数据，与此相对，表格式数据提供程序 (TDP) 则以表格式视图显示数据。有关您的提供程序所支持的特定语法和行为的更多详细信息，请参考您的 OLAP OLE DB 提供程序的文档。

## <a name="adox"></a>ADOX

用于数据定义语言和安全性的 Microsoft ActiveX 数据对象扩展 (ADOX) 是 ADO 对象和编程模型的扩展。ADOX 包括用于创建和修改架构以及安全性的对象。由于它基于对象来实现对架构的操控，因此您可以编写代码来处理各类数据源，而无需考虑数据源本来的语法之间的差异。

ADOX 是核心 ADO 对象的配套库。它提供了用于创建、修改和删除架构对象（如表和过程）的附加对象，还提供了用于维护用户和组以及用于授予和撤消对象权限的安全对象。

## <a name="ado-25-main-components"></a>ADO 2.5 主要组件

- [程序员指南](ado-programmer-s-guide.md)： 使用 ADO、 RDS、 ADO MD 和 ADOX 的介绍。

- [程序员参考](ado-programmer-s-reference-topics.md)： ADO 文档中的此部分包含的每个 ADO、 RDS、 ADO MD 和 ADOX 对象的集合、 属性、 动态属性、 方法、 事件和枚举的主题。

## <a name="feedback"></a>反馈

可以直接向 ADO 文档工作组发送关于 ADO 文档或示例的反馈。

