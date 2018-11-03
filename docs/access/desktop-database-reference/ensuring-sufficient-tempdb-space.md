---
title: 确保有足够的 TempDB 空间
TOCTitle: Ensuring sufficient TempDB space
ms:assetid: 2729c118-ec8b-1fcb-4a90-56b57823b24c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249034(v=office.15)
ms:contentKeyID: 48543830
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 09671570865d25738b7d4ba9358754c62da6f24e
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946347"
---
# <a name="ensuring-sufficient-tempdb-space"></a>确保有足够的 TempDB 空间


**适用于**： Access 2013、 Office 2013

如果在处理需要 Microsoft SQL Server 6.5 处理空间的 [Recordset](recordset-object-ado.md) 对象时出错，则可能需要增加 TempDB 的大小。（某些查询需要临时处理空间；例如，带 ORDER BY 子句的查询需要一种 **Recordset** ，而这需要一些临时空间。）

> [!IMPORTANT]
> [!重要信息] 请在执行操作之前阅读该步骤，因为设备一旦展开就难以折叠。

> [!NOTE]
> [!注释] 在默认情况下，在 Microsoft SQL Server 7.0 和更高版本中，TempDB 会设置为根据需要自动增加大小。因此，下面的过程可能仅在运行版本低于 7.0 的 SQL Server 的服务器上是必需的。



**增加 SQL Server 6.5 上的 TempDB 空间**

1.  启动 Microsoft SQL Server 企业管理器，打开"服务器"树，然后打开"数据库设备"树。

2.  选择一个 （物理） 设备，以展开，如主控形状，并双击该设备以打开**编辑数据库设备**对话框。 此对话框中显示当前数据库使用的空间大小。

3.  在**大小**框中，将增加到所需量 (例如，50 mb 硬盘空间) 设备。

4.  单击**立即更改**以增加 （逻辑） TempDB 可以扩展到的空间量。

5.  打开在服务器上，在数据库树，然后双击**TempDB**以打开**编辑数据库**对话框。 **数据库**选项卡列出当前分配给 TempDB （**数据大小**） 的空间量。 默认情况下，这是 2 MB。

6.  在**大小**组中，单击**扩展**。 关系图显示在每台物理设备上的可用且已分配的空间。 中褐紫红色颜色条表示可用空间。

7.  选择一个**日志设备**，如，Master，在**大小 (MB)** 框中显示的可用大小。

8.  单击**展开现在**即可将分配给 TempDB 数据库的空间。 **编辑数据库**对话框显示 TempDB 新分配的大小。

有关本主题的详细信息，请在 Microsoft SQL Server 企业管理器帮助文件中搜索"扩展数据库对话框"。

