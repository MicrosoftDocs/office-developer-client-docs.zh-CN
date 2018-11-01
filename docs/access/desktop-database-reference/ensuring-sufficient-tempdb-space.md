---
title: 确保具有足够的 TempDB 空间
TOCTitle: Ensuring Sufficient TempDB Space
ms:assetid: 2729c118-ec8b-1fcb-4a90-56b57823b24c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249034(v=office.15)
ms:contentKeyID: 48543830
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7b08980b7bb852a497ea339f4c43d439ac16a7e5
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885764"
---
# <a name="ensuring-sufficient-tempdb-space"></a><span data-ttu-id="808b6-102">确保具有足够的 TempDB 空间</span><span class="sxs-lookup"><span data-stu-id="808b6-102">Ensuring Sufficient TempDB Space</span></span>


<span data-ttu-id="808b6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="808b6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="808b6-p101">如果在处理需要 Microsoft SQL Server 6.5 处理空间的 [Recordset](recordset-object-ado.md) 对象时出错，则可能需要增加 TempDB 的大小。（某些查询需要临时处理空间；例如，带 ORDER BY 子句的查询需要一种 **Recordset** ，而这需要一些临时空间。）</span><span class="sxs-lookup"><span data-stu-id="808b6-p101">If errors occur while handling [Recordset](recordset-object-ado.md) objects that need processing space on Microsoft SQL Server 6.5, you may need to increase the size of the TempDB. (Some queries require temporary processing space; for example, a query with an ORDER BY clause requires a sort of the **Recordset**, which requires some temporary space.)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="808b6-106">[!重要信息] 请在执行操作之前阅读该步骤，因为设备一旦展开就难以折叠。</span><span class="sxs-lookup"><span data-stu-id="808b6-106">Read through this procedure before performing the actions because it isn't as easy to shrink a device once it is expanded.</span></span>

> [!NOTE]
> <span data-ttu-id="808b6-p102">[!注释] 在默认情况下，在 Microsoft SQL Server 7.0 和更高版本中，TempDB 会设置为根据需要自动增加大小。因此，下面的过程可能仅在运行版本低于 7.0 的 SQL Server 的服务器上是必需的。</span><span class="sxs-lookup"><span data-stu-id="808b6-p102">By default in Microsoft SQL Server 7.0 and later, TempDB is set to automatically grow as needed. Therefore, this procedure may only be necessary on servers running versions earlier than 7.0.</span></span>



<span data-ttu-id="808b6-109">**增加 SQL Server 6.5 上的 TempDB 空间**</span><span class="sxs-lookup"><span data-stu-id="808b6-109">**To increase the TempDB space on SQL Server 6.5**</span></span>

1.  <span data-ttu-id="808b6-110">启动 Microsoft® SQL Server 企业管理器，打开"服务器"树，然后打开"数据库设备"树。</span><span class="sxs-lookup"><span data-stu-id="808b6-110">Start Microsoft® SQL Server Enterprise Manager, open the tree for the Server, and then open the Database Devices tree.</span></span>

2.  <span data-ttu-id="808b6-111">选择一个 （物理） 设备，以展开，如主控形状，并双击该设备以打开**编辑数据库设备**对话框。</span><span class="sxs-lookup"><span data-stu-id="808b6-111">Select a (physical) device to expand, such as Master, and double-click the device to open the **Edit Database Device** dialog box.</span></span> <span data-ttu-id="808b6-112">此对话框中显示当前数据库使用的空间大小。</span><span class="sxs-lookup"><span data-stu-id="808b6-112">This dialog box shows how much space the current databases are using.</span></span>

3.  <span data-ttu-id="808b6-113">在**大小**框中，将增加到所需量 (例如，50 mb 硬盘空间) 设备。</span><span class="sxs-lookup"><span data-stu-id="808b6-113">In the **Size** box, increase the device to the desired amount (for example, 50 megabytes (MB) of hard disk space).</span></span>

4.  <span data-ttu-id="808b6-114">单击**立即更改**以增加 （逻辑） TempDB 可以扩展到的空间量。</span><span class="sxs-lookup"><span data-stu-id="808b6-114">Click **Change Now** to increase the amount of space to which the (logical) TempDB can expand.</span></span>

5.  <span data-ttu-id="808b6-115">打开在服务器上，在数据库树，然后双击**TempDB**以打开**编辑数据库**对话框。</span><span class="sxs-lookup"><span data-stu-id="808b6-115">Open the Databases tree on the server, and then double-click **TempDB** to open the **Edit Database** dialog box.</span></span> <span data-ttu-id="808b6-116">**数据库**选项卡列出当前分配给 TempDB （**数据大小**） 的空间量。</span><span class="sxs-lookup"><span data-stu-id="808b6-116">The **Database** tab lists the amount of space currently allocated to TempDB (**Data Size**).</span></span> <span data-ttu-id="808b6-117">默认情况下，这是 2 MB。</span><span class="sxs-lookup"><span data-stu-id="808b6-117">By default, this is 2 MB.</span></span>

6.  <span data-ttu-id="808b6-118">在**大小**组中，单击**扩展**。</span><span class="sxs-lookup"><span data-stu-id="808b6-118">Under the **Size** group, click **Expand**.</span></span> <span data-ttu-id="808b6-119">关系图显示在每台物理设备上的可用且已分配的空间。</span><span class="sxs-lookup"><span data-stu-id="808b6-119">The graphs show the available and allocated space on each of the physical devices.</span></span> <span data-ttu-id="808b6-120">中褐紫红色颜色条表示可用空间。</span><span class="sxs-lookup"><span data-stu-id="808b6-120">The bars in maroon color represent available space.</span></span>

7.  <span data-ttu-id="808b6-121">选择一个**日志设备**，如，Master，在**大小 (MB)** 框中显示的可用大小。</span><span class="sxs-lookup"><span data-stu-id="808b6-121">Select a **Log Device**, such as Master, to display the available size in the **Size (MB)** box.</span></span>

8.  <span data-ttu-id="808b6-122">单击**展开现在**即可将分配给 TempDB 数据库的空间。</span><span class="sxs-lookup"><span data-stu-id="808b6-122">Click **Expand Now** to allocate that space to the TempDB database.</span></span> <span data-ttu-id="808b6-123">**编辑数据库**对话框显示 TempDB 新分配的大小。</span><span class="sxs-lookup"><span data-stu-id="808b6-123">The **Edit Database** dialog box displays the new allocated size for TempDB.</span></span>

<span data-ttu-id="808b6-124">有关本主题的详细信息，请在 Microsoft SQL Server 企业管理器帮助文件中搜索"扩展数据库对话框"。</span><span class="sxs-lookup"><span data-stu-id="808b6-124">For more information about this topic, search the Microsoft SQL Server Enterprise Manager Help file for "Expand Database dialog box."</span></span>

