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
# <a name="ensuring-sufficient-tempdb-space"></a><span data-ttu-id="2eff7-102">确保有足够的 TempDB 空间</span><span class="sxs-lookup"><span data-stu-id="2eff7-102">Ensuring sufficient TempDB space</span></span>


<span data-ttu-id="2eff7-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="2eff7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2eff7-p101">如果在处理需要 Microsoft SQL Server 6.5 处理空间的 [Recordset](recordset-object-ado.md) 对象时出错，则可能需要增加 TempDB 的大小。（某些查询需要临时处理空间；例如，带 ORDER BY 子句的查询需要一种 **Recordset** ，而这需要一些临时空间。）</span><span class="sxs-lookup"><span data-stu-id="2eff7-p101">If errors occur while handling [Recordset](recordset-object-ado.md) objects that need processing space on Microsoft SQL Server 6.5, you may need to increase the size of the TempDB. (Some queries require temporary processing space; for example, a query with an ORDER BY clause requires a sort of the **Recordset**, which requires some temporary space.)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2eff7-106">[!重要信息] 请在执行操作之前阅读该步骤，因为设备一旦展开就难以折叠。</span><span class="sxs-lookup"><span data-stu-id="2eff7-106">Read through this procedure before performing the actions because it isn't as easy to shrink a device once it is expanded.</span></span>

> [!NOTE]
> <span data-ttu-id="2eff7-p102">[!注释] 在默认情况下，在 Microsoft SQL Server 7.0 和更高版本中，TempDB 会设置为根据需要自动增加大小。因此，下面的过程可能仅在运行版本低于 7.0 的 SQL Server 的服务器上是必需的。</span><span class="sxs-lookup"><span data-stu-id="2eff7-p102">By default in Microsoft SQL Server 7.0 and later, TempDB is set to automatically grow as needed. Therefore, this procedure may only be necessary on servers running versions earlier than 7.0.</span></span>



<span data-ttu-id="2eff7-109">**增加 SQL Server 6.5 上的 TempDB 空间**</span><span class="sxs-lookup"><span data-stu-id="2eff7-109">**To increase the TempDB space on SQL Server 6.5**</span></span>

1.  <span data-ttu-id="2eff7-110">启动 Microsoft SQL Server 企业管理器，打开"服务器"树，然后打开"数据库设备"树。</span><span class="sxs-lookup"><span data-stu-id="2eff7-110">Start Microsoft SQL Server Enterprise Manager, open the tree for the Server, and then open the Database Devices tree.</span></span>

2.  <span data-ttu-id="2eff7-p103">Select a (physical) device to expand, such as Master, and double-click the device to open the **Edit Database Device** dialog box. This dialog box shows how much space the current databases are using.</span><span class="sxs-lookup"><span data-stu-id="2eff7-p103">Select a (physical) device to expand, such as Master, and double-click the device to open the **Edit Database Device** dialog box. This dialog box shows how much space the current databases are using.</span></span>

3.  <span data-ttu-id="2eff7-113">In the **Size** box, increase the device to the desired amount (for example, 50 megabytes (MB) of hard disk space).</span><span class="sxs-lookup"><span data-stu-id="2eff7-113">In the **Size** box, increase the device to the desired amount (for example, 50 megabytes (MB) of hard disk space).</span></span>

4.  <span data-ttu-id="2eff7-114">单击\*\*\*\*“立即更改”以增加（逻辑）TempDB 可以扩展到的空间大小。</span><span class="sxs-lookup"><span data-stu-id="2eff7-114">Click **Change Now** to increase the amount of space to which the (logical) TempDB can expand.</span></span>

5.  <span data-ttu-id="2eff7-p104">打开服务器上的“数据库”树，然后双击\*\*\*\*“TempDB”以打开\*\*\*\*“编辑数据库”对话框。\*\*\*\*“数据库”选项卡列出了当前分配给 TempDB 的空间大小（\*\*\*\*“数据大小”）。默认情况下是 2 MB。</span><span class="sxs-lookup"><span data-stu-id="2eff7-p104">Open the Databases tree on the server, and then double-click **TempDB** to open the **Edit Database** dialog box. The **Database** tab lists the amount of space currently allocated to TempDB (**Data Size**). By default, this is 2 MB.</span></span>

6.  <span data-ttu-id="2eff7-p105">Under the **Size** group, click **Expand**. The graphs show the available and allocated space on each of the physical devices. The bars in maroon color represent available space.</span><span class="sxs-lookup"><span data-stu-id="2eff7-p105">Under the **Size** group, click **Expand**. The graphs show the available and allocated space on each of the physical devices. The bars in maroon color represent available space.</span></span>

7.  <span data-ttu-id="2eff7-121">Select a **Log Device**, such as Master, to display the available size in the **Size (MB)** box.</span><span class="sxs-lookup"><span data-stu-id="2eff7-121">Select a **Log Device**, such as Master, to display the available size in the **Size (MB)** box.</span></span>

8.  <span data-ttu-id="2eff7-p106">Click **Expand Now** to allocate that space to the TempDB database. The **Edit Database** dialog box displays the new allocated size for TempDB.</span><span class="sxs-lookup"><span data-stu-id="2eff7-p106">Click **Expand Now** to allocate that space to the TempDB database. The **Edit Database** dialog box displays the new allocated size for TempDB.</span></span>

<span data-ttu-id="2eff7-124">有关本主题的详细信息，请在 Microsoft SQL Server 企业管理器帮助文件中搜索"扩展数据库对话框"。</span><span class="sxs-lookup"><span data-stu-id="2eff7-124">For more information about this topic, search the Microsoft SQL Server Enterprise Manager Help file for "Expand Database dialog box."</span></span>

