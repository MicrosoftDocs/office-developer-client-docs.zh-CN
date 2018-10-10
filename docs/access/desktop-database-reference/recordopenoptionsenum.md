---
title: RecordOpenOptionsEnum
TOCTitle: RecordOpenOptionsEnum
ms:assetid: 44a69719-0789-a084-fb96-21468e270205
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249207(v=office.15)
ms:contentKeyID: 48544534
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d9538e1fb4a712b109e021512a3d28d299deaeb3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467004"
---
# <a name="recordopenoptionsenum"></a><span data-ttu-id="82dec-102">RecordOpenOptionsEnum</span><span class="sxs-lookup"><span data-stu-id="82dec-102">RecordOpenOptionsEnum</span></span>


<span data-ttu-id="82dec-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="82dec-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="82dec-p101">用于指定打开 [Record](record-object-ado.md) 的选项。可以通过 OR 来组合使用这些值。</span><span class="sxs-lookup"><span data-stu-id="82dec-p101">Specifies options for opening a [Record](record-object-ado.md). These values may be combined by using OR.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="82dec-106">常量</span><span class="sxs-lookup"><span data-stu-id="82dec-106">Constant</span></span></p></th>
<th><p><span data-ttu-id="82dec-107">值</span><span class="sxs-lookup"><span data-stu-id="82dec-107">Value</span></span></p></th>
<th><p><span data-ttu-id="82dec-108">说明</span><span class="sxs-lookup"><span data-stu-id="82dec-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82dec-109"><strong>adDelayFetchFields</strong></span><span class="sxs-lookup"><span data-stu-id="82dec-109"><strong>adDelayFetchFields</strong></span></span></p></td>
<td><p><span data-ttu-id="82dec-110">0x8000</span><span class="sxs-lookup"><span data-stu-id="82dec-110">0x8000</span></span></p></td>
<td><p><span data-ttu-id="82dec-p102">向提供程序指示：最初不需要检索与 <strong>Record</strong> 关联的字段，而是可以在第一次尝试访问字段时进行检索。缺少此标志时指示执行默认行为，即检索所有 <strong>Record</strong> 对象字段。</span><span class="sxs-lookup"><span data-stu-id="82dec-p102">Indicates to the provider that the fields associated with the <strong>Record</strong> need not be retrieved initially, but can be retrieved at the first attempt to access the field. The default behavior, indicated by the absence of this flag, is to retrieve all the <strong>Record</strong> object fields.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82dec-113"><strong>adDelayFetchStream</strong></span><span class="sxs-lookup"><span data-stu-id="82dec-113"><strong>adDelayFetchStream</strong></span></span></p></td>
<td><p><span data-ttu-id="82dec-114">0x4000</span><span class="sxs-lookup"><span data-stu-id="82dec-114">0x4000</span></span></p></td>
<td><p><span data-ttu-id="82dec-p103">向提供程序指示：最初不需要检索与 <strong>Record</strong> 关联的默认流。缺少此标志时指示执行默认行为，即检索与 <strong>Record</strong> 对象关联的默认流。</span><span class="sxs-lookup"><span data-stu-id="82dec-p103">Indicates to the provider that the default stream associated with the <strong>Record</strong> need not be retrieved initially. The default behavior, indicated by the absence of this flag, is to retrieve the default stream associated with the <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82dec-117"><strong>adOpenAsync</strong></span><span class="sxs-lookup"><span data-stu-id="82dec-117"><strong>adOpenAsync</strong></span></span></p></td>
<td><p><span data-ttu-id="82dec-118">0x1000</span><span class="sxs-lookup"><span data-stu-id="82dec-118">0x1000</span></span></p></td>
<td><p><span data-ttu-id="82dec-119">指示 <strong>Record</strong> 对象以异步模式打开。</span><span class="sxs-lookup"><span data-stu-id="82dec-119">Indicates that the <strong>Record</strong> object is opened in asynchronous mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82dec-120"><strong>adOpenExecuteCommand</strong></span><span class="sxs-lookup"><span data-stu-id="82dec-120"><strong>adOpenExecuteCommand</strong></span></span></p></td>
<td><p><span data-ttu-id="82dec-121">0x10000</span><span class="sxs-lookup"><span data-stu-id="82dec-121">0x10000</span></span></p></td>
<td><p><span data-ttu-id="82dec-p104">指示源字符串包含应执行的命令文本。此值与 <strong>Recordset.Open</strong> 上的 <strong>adCmdText</strong> 选项等同。</span><span class="sxs-lookup"><span data-stu-id="82dec-p104">Indicates that the Source string contains command text that should be executed. This value is equivalent to the <strong>adCmdText</strong> option on <strong>Recordset.Open</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82dec-124"><strong>adOpenRecordUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="82dec-124"><strong>adOpenRecordUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="82dec-125">-1</span><span class="sxs-lookup"><span data-stu-id="82dec-125">-1</span></span></p></td>
<td><p><span data-ttu-id="82dec-p105">默认值。指示未指定选项。</span><span class="sxs-lookup"><span data-stu-id="82dec-p105">Default. Indicates no options are specified.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82dec-128"><strong>adOpenOutput</strong></span><span class="sxs-lookup"><span data-stu-id="82dec-128"><strong>adOpenOutput</strong></span></span></p></td>
<td><p><span data-ttu-id="82dec-129">0x800000</span><span class="sxs-lookup"><span data-stu-id="82dec-129">0x800000</span></span></p></td>
<td><p><span data-ttu-id="82dec-p106">指示如果源指向的节点包含可执行脚本（如 .ASP 页），则打开的 <strong>Record</strong> 将包含执行后的脚本的结果。此值仅对于非集合记录有效。</span><span class="sxs-lookup"><span data-stu-id="82dec-p106">Indicates that if the source points to a node that contains an executable script (such as an .ASP page), then the opened <strong>Record</strong> will contain the results of the executed script. This value is only valid with non-collection records.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82dec-132">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="82dec-132">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="82dec-133">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="82dec-133">These constants do not have ADO/WFC equivalents.</span></span>

