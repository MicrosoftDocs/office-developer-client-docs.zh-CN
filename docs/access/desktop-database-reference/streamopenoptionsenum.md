---
title: StreamOpenOptionsEnum
TOCTitle: StreamOpenOptionsEnum
ms:assetid: d4bbd6be-41f1-cdf2-9d8f-b77ce83fb88e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250069(v=office.15)
ms:contentKeyID: 48547951
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f335f8572fbade23b949abacce8dd3690d205e32
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721218"
---
# <a name="streamopenoptionsenum"></a><span data-ttu-id="31964-102">StreamOpenOptionsEnum</span><span class="sxs-lookup"><span data-stu-id="31964-102">StreamOpenOptionsEnum</span></span>


<span data-ttu-id="31964-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="31964-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="31964-p101">用于指定打开 [Stream](stream-object-ado.md) 对象的选项。可以使用 OR 运算符来组合使用这些值。</span><span class="sxs-lookup"><span data-stu-id="31964-p101">Specifies options for opening a [Stream](stream-object-ado.md) object. The values can be combined with an OR operation.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="31964-106">常量</span><span class="sxs-lookup"><span data-stu-id="31964-106">Constant</span></span></p></th>
<th><p><span data-ttu-id="31964-107">值</span><span class="sxs-lookup"><span data-stu-id="31964-107">Value</span></span></p></th>
<th><p><span data-ttu-id="31964-108">说明</span><span class="sxs-lookup"><span data-stu-id="31964-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31964-109"><strong>adOpenStreamAsync</strong></span><span class="sxs-lookup"><span data-stu-id="31964-109"><strong>adOpenStreamAsync</strong></span></span></p></td>
<td><p><span data-ttu-id="31964-110">1</span><span class="sxs-lookup"><span data-stu-id="31964-110">1</span></span></p></td>
<td><p><span data-ttu-id="31964-111">以异步模式打开 <strong>Stream</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="31964-111">Opens the <strong>Stream</strong> object in asynchronous mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31964-112"><strong>adOpenStreamFromRecord</strong></span><span class="sxs-lookup"><span data-stu-id="31964-112"><strong>adOpenStreamFromRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="31964-113">4</span><span class="sxs-lookup"><span data-stu-id="31964-113">4</span></span></p></td>
<td><p><span data-ttu-id="31964-p102">将 <em>Source</em> 参数的内容标识为某个已打开的 <a href="record-object-ado.md">Record</a> 对象。默认行为是将 <em>Source</em> 视为直接指向树结构中的某个节点的 URL。与该节点关联的默认流已打开。</span><span class="sxs-lookup"><span data-stu-id="31964-p102">Identifies the contents of the <em>Source</em> parameter to be an already open <a href="record-object-ado.md">Record</a> object. The default behavior is to treat <em>Source</em> as a URL that points directly to a node in a tree structure. The default stream associated with that node is opened.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31964-117"><strong>adOpenStreamUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="31964-117"><strong>adOpenStreamUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="31964-118">-1</span><span class="sxs-lookup"><span data-stu-id="31964-118">-1</span></span></p></td>
<td><p><span data-ttu-id="31964-p103">默认值。指定使用默认选项打开 <strong>Stream</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="31964-p103">Default. Specifies opening the <strong>Stream</strong> object with default options.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="31964-121">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="31964-121">ADO/WFC equivalent</span></span>

<span data-ttu-id="31964-122">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="31964-122">These constants do not have ADO/WFC equivalents.</span></span>

