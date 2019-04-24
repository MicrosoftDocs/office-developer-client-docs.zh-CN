---
title: ADO 系列库
TOCTitle: The ADO family of libraries
ms:assetid: 9e794509-d0a8-2e5b-02a8-65e26f059c4e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249724(v=office.15)
ms:contentKeyID: 48546656
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 296e05118054ec045c23cd92a399afdc3cddd9a1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32313970"
---
# <a name="the-ado-family-of-libraries"></a>ADO 系列库

**适用于**：Access 2013、Office 2013

ADO 系列包括三个主要库：ADO（包括 RDS）、ADO MD 和 ADOX。

## <a name="ado"></a>ADO

利用 ADO，您的客户端应用程序可以通过 OLE DB 提供程序访问和操控数据库服务器中的数据。 ADO 的主要优势在于易用、高速、低内存开销而且磁盘空间需求量小。 ADO 支持用于构建客户端/服务器和基于 web 的应用程序的关键功能。

ADO 还提供了远程数据服务 (RDS), 通过它可以将数据从服务器移动到客户端应用程序或网页, 操作客户端上的数据, 并在一次往返行程中将更新返回到服务器。

## <a name="ado-md"></a>ADO MD

使用 Microsoft ActiveX 数据对象（多维） (ADO MD) 可以通过 Microsoft Visual Basic、Microsoft Visual C++ 和 Microsoft Visual J++ 等语言轻松访问多维数据。ADO MD 对 ADO 进行了扩展以包含特定于多维数据的对象（如 **CubeDef** 和 **Cellset**）。利用 ADO MD，您可以浏览多维架构，查询多维数据集，并可以检索结果。

与 ADO 一样，ADO MD 使用基础 OLE DB 提供程序获取对数据的访问。若要使用 ADO MD，该提供程序必须是按照 OLE DB for OLAP 规范定义的多维数据提供程序 (MDP)。MDP 以多维视图显示数据，这与以表格视图显示数据的表格式数据提供程序 (TDP) 不同。有关特定语法以及您的提供程序所支持的行为的更详细信息，请参考 OLAP OLE DB 提供程序的文档。

## <a name="adox"></a>ADOX

Microsoft ActiveX Data Objects Extensions for Data Definition Language and Security (ADOX) 是 ADO 对象和编程模型的扩展。ADOX 包括用于创建和修改架构以及保证安全性的对象。由于它基于对象实现架构操作，因此可以针对各种数据源编写代码，无需考虑其本机语法的差异。

ADOX 是核心 ADO 对象的配套库。它提供了用于创建、修改、删除架构对象（如表和过程）的其他对象。它还包括安全性对象，用于维护用户和组以及授予和吊销对象权限。

