---
title: 确保有足够的 TempDB 空间
TOCTitle: Ensuring sufficient TempDB space
ms:assetid: 2729c118-ec8b-1fcb-4a90-56b57823b24c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249034(v=office.15)
ms:contentKeyID: 48543830
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6414c9dd4c3218c2c2bf90f39d0cfb950e6e1018
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293572"
---
# <a name="ensuring-sufficient-tempdb-space"></a>确保有足够的 TempDB 空间


**适用于**：Access 2013、Office 2013

如果在处理需要 Microsoft SQL Server 6.5 处理空间的 [Recordset](recordset-object-ado.md) 对象时出错，则可能需要增加 TempDB 的大小。（某些查询需要临时处理空间；例如，带 ORDER BY 子句的查询需要一种 **Recordset** ，而这需要一些临时空间。）

> [!IMPORTANT]
> [!重要信息] 请在执行操作之前阅读该步骤，因为设备一旦展开就难以折叠。

> [!NOTE]
> [!注释] 在默认情况下，在 Microsoft SQL Server 7.0 和更高版本中，TempDB 会设置为根据需要自动增加大小。因此，下面的过程可能仅在运行版本低于 7.0 的 SQL Server 的服务器上是必需的。



**增加 SQL Server 6.5 上的 TempDB 空间**

1.  启动 Microsoft SQL Server 企业管理器，打开"服务器"树，然后打开"数据库设备"树。

2.  Select a (physical) device to expand, such as Master, and double-click the device to open the **Edit Database Device** dialog box. This dialog box shows how much space the current databases are using.

3.  In the **Size** box, increase the device to the desired amount (for example, 50 megabytes (MB) of hard disk space).

4.  单击****“立即更改”以增加（逻辑）TempDB 可以扩展到的空间大小。

5.  打开服务器上的“数据库”树，然后双击****“TempDB”以打开****“编辑数据库”对话框。****“数据库”选项卡列出了当前分配给 TempDB 的空间大小（****“数据大小”）。默认情况下是 2 MB。

6.  Under the **Size** group, click **Expand**. The graphs show the available and allocated space on each of the physical devices. The bars in maroon color represent available space.

7.  Select a **Log Device**, such as Master, to display the available size in the **Size (MB)** box.

8.  Click **Expand Now** to allocate that space to the TempDB database. The **Edit Database** dialog box displays the new allocated size for TempDB.

有关本主题的详细信息，请在 Microsoft SQL Server 企业管理器帮助文件中搜索"扩展数据库对话框"。

