---
title: RDS 对象模型摘要
TOCTitle: RDS object model summary
ms:assetid: 0355d62a-dabb-8643-5c43-1e98ccf7f3b0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248800(v=office.15)
ms:contentKeyID: 48542981
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 33cbdc6de644592d87b7d49e65a5c5674ad94d5b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300873"
---
# <a name="rds-object-model-summary"></a><span data-ttu-id="865b1-102">RDS 对象模型摘要</span><span class="sxs-lookup"><span data-stu-id="865b1-102">RDS object model summary</span></span>


<span data-ttu-id="865b1-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="865b1-103">**Applies to**: Access 2013, Office 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="865b1-104">Object</span><span class="sxs-lookup"><span data-stu-id="865b1-104">Object</span></span></p></th>
<th><p><span data-ttu-id="865b1-105">说明</span><span class="sxs-lookup"><span data-stu-id="865b1-105">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="865b1-106"><a href="dataspace-object-rds.md">RDS.DataSpace</a></span><span class="sxs-lookup"><span data-stu-id="865b1-106"><a href="dataspace-object-rds.md">RDS.DataSpace</a></span></span></p></td>
<td><p><span data-ttu-id="865b1-p101">此对象包含一个用于获取服务器代理的方法。代理可以是默认的服务器程序或自定义服务器程序（业务对象）。该服务器程序可以在 Internet、Intranet、局域网或本地动态链接库上调用。</span><span class="sxs-lookup"><span data-stu-id="865b1-p101">This object contains a method to obtain a server proxy. The proxy may be the default or a custom server program (business object). The server program may be invoked on the Internet, an intranet, a local area network, or be a local dynamic-link library.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="865b1-110"><a href="datafactory-object-rdsserver.md">rdsserver.datafactory。 DataFactory</a></span><span class="sxs-lookup"><span data-stu-id="865b1-110"><a href="datafactory-object-rdsserver.md">RDSServer.DataFactory</a></span></span></p></td>
<td><p><span data-ttu-id="865b1-111">此对象表示默认的服务器程序。</span><span class="sxs-lookup"><span data-stu-id="865b1-111">This object represents the default server program.</span></span> <span data-ttu-id="865b1-112">用于执行默认的 RDS 数据检索和更新行为。</span><span class="sxs-lookup"><span data-stu-id="865b1-112">It executes the default RDS data retrieval and update behavior.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="865b1-113"><a href="datacontrol-object-rds.md">RDS.rds.datacontrol</a></span><span class="sxs-lookup"><span data-stu-id="865b1-113"><a href="datacontrol-object-rds.md">RDS.DataControl</a></span></span></p></td>
<td><p><span data-ttu-id="865b1-114">此对象可以自动调用 <strong>RDS.DataSpace</strong> 和 <strong>RDSServer.DataFactory</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="865b1-114">This object can automatically invoke the <strong>RDS.DataSpace</strong> and <strong>RDSServer.DataFactory</strong> objects.</span></span> <span data-ttu-id="865b1-115">此对象可用于调用默认的 RDS 数据检索或更新行为。</span><span class="sxs-lookup"><span data-stu-id="865b1-115">Use this object to invoke the default RDS data retrieval or update behavior.</span></span> <span data-ttu-id="865b1-116">此对象还提供了多种方法，以供可视控件访问返回的 <strong>Recordset</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="865b1-116">This object also provides the means for visual controls to access the returned <strong>Recordset</strong> object.</span></span></p></td>
</tr>
</tbody>
</table>

