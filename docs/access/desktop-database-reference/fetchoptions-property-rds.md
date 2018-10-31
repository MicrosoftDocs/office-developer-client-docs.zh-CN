---
title: FetchOptions 属性 (RDS)
TOCTitle: FetchOptions Property (RDS)
ms:assetid: 0d86c5e4-9abc-5c0e-dc04-4183f4c278cc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248856(v=office.15)
ms:contentKeyID: 48543221
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b3e7251ba50b003b37cdeb0dd70fe4a98821d4c9
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861930"
---
# <a name="fetchoptions-property-rds"></a><span data-ttu-id="bad22-102">FetchOptions 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="bad22-102">FetchOptions Property (RDS)</span></span>


<span data-ttu-id="bad22-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="bad22-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="bad22-104">指示异步获取类型。</span><span class="sxs-lookup"><span data-stu-id="bad22-104">Indicates the type of asynchronous fetching.</span></span>

## <a name="setting-and-return-values"></a><span data-ttu-id="bad22-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="bad22-105">Setting and Return Values</span></span>

<span data-ttu-id="bad22-106">设置或返回下列值之一。</span><span class="sxs-lookup"><span data-stu-id="bad22-106">Sets or returns one of the following values.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bad22-107">常量</span><span class="sxs-lookup"><span data-stu-id="bad22-107">Constant</span></span></p></th>
<th><p><span data-ttu-id="bad22-108">说明</span><span class="sxs-lookup"><span data-stu-id="bad22-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bad22-109"><strong>adcFetchUpFront</strong></span><span class="sxs-lookup"><span data-stu-id="bad22-109"><strong>adcFetchUpFront</strong></span></span></p></td>
<td><p><span data-ttu-id="bad22-p101">在控制返回到应用程序之前获取 <a href="recordset-object-ado.md">Recordset</a> 的所有记录。在获取完整的 <strong>Recordset</strong> 之后才允许应用程序对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="bad22-p101">All the records of the <a href="recordset-object-ado.md">Recordset</a> are fetched before control is returned to the application. The complete <strong>Recordset</strong> is fetched before the application is allowed to do anything with it.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bad22-112"><strong>adcFetchBackground</strong></span><span class="sxs-lookup"><span data-stu-id="bad22-112"><strong>adcFetchBackground</strong></span></span></p></td>
<td><p><span data-ttu-id="bad22-p102">只要获取了首批记录，控制即可返回到应用程序。对试图访问未在首批获取的记录进行的后续读取，<strong>Recordset</strong> 将延迟到实际获取待查的记录之后，届时控制将返回到应用程序。</span><span class="sxs-lookup"><span data-stu-id="bad22-p102">Control can return to the application as soon as the first batch of records has been fetched. A subsequent read of the <strong>Recordset</strong> that attempts to access a record not fetched in the first batch will be delayed until the sought record is actually fetched, at which time control returns to the application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bad22-115"><strong>adcFetchAsync</strong></span><span class="sxs-lookup"><span data-stu-id="bad22-115"><strong>adcFetchAsync</strong></span></span></p></td>
<td><p><span data-ttu-id="bad22-p103">该值为默认值。在后台获取记录时控制将立刻返回至应用程序。如果应用程序试图读取尚未获取的记录，则将读取最接近所发现的记录的记录，且控制将立刻返回，指示已到达 <strong>Recordset</strong> 的当前末尾处。例如，尽管会有更多记录继续填充 <strong>Recordset</strong>，调用 <a href="movefirst-movelast-movenext-and-moveprevious-methods-rds.md">MoveLast</a> 会始终将当前记录位置移动到实际获取的最后一条记录。</span><span class="sxs-lookup"><span data-stu-id="bad22-p103">Default. Control returns immediately to the application while records are fetched in the background. If the application attempts to read a record that hasn't yet been fetched, the record closest to the sought record will be read and control will return immediately, indicating that the current end of the <strong>Recordset</strong> has been reached. For example, a call to <a href="movefirst-movelast-movenext-and-moveprevious-methods-rds.md">MoveLast</a> will move the current record position to the last record actually fetched, even though more records will continue to populate the <strong>Recordset</strong>.</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <span data-ttu-id="bad22-p104">[!注释] 使用这些常量的每个客户端可执行文件必须提供其声明。可从位于 C:\Program Files\Common Files\System\MSADC 文件夹中的 Adcvbs.inc 文件剪切并粘贴所需的常量声明。</span><span class="sxs-lookup"><span data-stu-id="bad22-p104">Each client-side executable file that uses these constants must provide declarations for them. You can cut and paste the constant declarations you want from the file Adcvbs.inc, located in the C:\Program Files\Common Files\System\MSADC folder.</span></span>



## <a name="remarks"></a><span data-ttu-id="bad22-122">备注</span><span class="sxs-lookup"><span data-stu-id="bad22-122">Remarks</span></span>

<span data-ttu-id="bad22-123"><<<<<<< 标头中 Web 应用程序中，将通常想要使用**adcFetchAsync** （默认值），因为它提供了更好的性能。</span><span class="sxs-lookup"><span data-stu-id="bad22-123"><<<<<<< HEAD In a Web application, you will usually want to use **adcFetchAsync** (the default value), because it provides better performance.</span></span> <span data-ttu-id="bad22-124">而在已编译的客户端应用程序中，通常会使用 **adcFetchBackground** 。</span><span class="sxs-lookup"><span data-stu-id="bad22-124">In a compiled client application, you will usually want to use **adcFetchBackground**.</span></span>
<span data-ttu-id="bad22-125">=== 在 web 应用程序，您通常需要使用**adcFetchAsync** （默认值），因为它提供了更好的性能。</span><span class="sxs-lookup"><span data-stu-id="bad22-125">======= In a web application, you will usually want to use **adcFetchAsync** (the default value), because it provides better performance.</span></span> <span data-ttu-id="bad22-126">而在已编译的客户端应用程序中，通常会使用 **adcFetchBackground** 。</span><span class="sxs-lookup"><span data-stu-id="bad22-126">In a compiled client application, you will usually want to use **adcFetchBackground**.</span></span>
>>>>>>> <span data-ttu-id="bad22-127">母版</span><span class="sxs-lookup"><span data-stu-id="bad22-127">master</span></span>

