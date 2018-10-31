---
title: RecordCreateOptionsEnum
TOCTitle: RecordCreateOptionsEnum
ms:assetid: 153dc8ff-680c-1482-d386-4c4b33ffc589
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248917(v=office.15)
ms:contentKeyID: 48543405
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ff4b05f364b400c3741f690eae58d926aa9d2bad
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861511"
---
# <a name="recordcreateoptionsenum"></a><span data-ttu-id="ddca9-102">RecordCreateOptionsEnum</span><span class="sxs-lookup"><span data-stu-id="ddca9-102">RecordCreateOptionsEnum</span></span>


<span data-ttu-id="ddca9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ddca9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="ddca9-p101">指定应该打开现有的 **Record** 还是应该为 **Record** 对象 [Open](record-object-ado.md) 方法创建一个新 [Record](open-method-ado-record.md) 。可以使用 AND 运算符来组合使用这些值。</span><span class="sxs-lookup"><span data-stu-id="ddca9-p101">Specifies whether an existing **Record** should be opened or a new **Record** created for the [Record](record-object-ado.md) object [Open](open-method-ado-record.md) method. The values can be combined with an AND operator.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ddca9-106">常量</span><span class="sxs-lookup"><span data-stu-id="ddca9-106">Constant</span></span></p></th>
<th><p><span data-ttu-id="ddca9-107">值</span><span class="sxs-lookup"><span data-stu-id="ddca9-107">Value</span></span></p></th>
<th><p><span data-ttu-id="ddca9-108">说明</span><span class="sxs-lookup"><span data-stu-id="ddca9-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ddca9-109"><strong>adCreateCollection</strong></span><span class="sxs-lookup"><span data-stu-id="ddca9-109"><strong>adCreateCollection</strong></span></span></p></td>
<td><p><span data-ttu-id="ddca9-110">0x2000</span><span class="sxs-lookup"><span data-stu-id="ddca9-110">0x2000</span></span></p></td>
<td><p><span data-ttu-id="ddca9-p102">在由 <em>Source</em> 参数指定的节点创建一个新 <strong>Record</strong>，而不是打开现有的 <strong>Record</strong>。如果源指向现有节点，则发生运行时错误，除非将 <strong>adCreateCollection</strong> 与 <strong>adOpenIfExists</strong> 或 <strong>adCreateOverwrite</strong> 结合使用。</span><span class="sxs-lookup"><span data-stu-id="ddca9-p102">Creates a new <strong>Record</strong> at the node specified by <em>Source</em> parameter, instead of opening an existing <strong>Record</strong>. If the source points to an existing node, then a run-time error occurs, unless <strong>adCreateCollection</strong> is combined with <strong>adOpenIfExists</strong> or <strong>adCreateOverwrite</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddca9-113"><strong>adCreateNonCollection</strong></span><span class="sxs-lookup"><span data-stu-id="ddca9-113"><strong>adCreateNonCollection</strong></span></span></p></td>
<td><p><span data-ttu-id="ddca9-114">0</span><span class="sxs-lookup"><span data-stu-id="ddca9-114">0</span></span></p></td>
<td><p><span data-ttu-id="ddca9-115">创建一个类型为 <a href="recordtypeenum.md">adSimpleRecord</a> 的新 <strong>Record</strong>。</span><span class="sxs-lookup"><span data-stu-id="ddca9-115">Creates a new <strong>Record</strong> of type <a href="recordtypeenum.md">adSimpleRecord</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddca9-116"><strong>adCreateOverwrite</strong></span><span class="sxs-lookup"><span data-stu-id="ddca9-116"><strong>adCreateOverwrite</strong></span></span></p></td>
<td><p><span data-ttu-id="ddca9-117">0x4000000</span><span class="sxs-lookup"><span data-stu-id="ddca9-117">0x4000000</span></span></p></td>
<td><p><span data-ttu-id="ddca9-p103">修改创建标志 <strong>adCreateCollection</strong>、<strong>adCreateNonCollection</strong> 和 <strong>adCreateStructDoc</strong>。当通过 OR 使用该值以及某个创建标志值时，如果源 URL 指向现有的节点或 <strong>Record</strong>，将覆盖该现有 <strong>Record</strong>，并在其位置创建一个新记录。该值不能与 <strong>adOpenIfExists</strong> 一起使用。</span><span class="sxs-lookup"><span data-stu-id="ddca9-p103">Modifies the creation flags <strong>adCreateCollection</strong>, <strong>adCreateNonCollection</strong>, and <strong>adCreateStructDoc</strong>. When OR is used with this value and one of the creation flag values, if the source URL points to an existing node or <strong>Record</strong>, then the existing <strong>Record</strong> is overwritten and a new one is created in its place. This value cannot be used together with <strong>adOpenIfExists</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddca9-121"><strong>adCreateStructDoc</strong></span><span class="sxs-lookup"><span data-stu-id="ddca9-121"><strong>adCreateStructDoc</strong></span></span></p></td>
<td><p><span data-ttu-id="ddca9-122">0x80000000</span><span class="sxs-lookup"><span data-stu-id="ddca9-122">0x80000000</span></span></p></td>
<td><p><span data-ttu-id="ddca9-123">创建一个类型为 <a href="recordtypeenum.md">adStructDoc</a> 的新 <strong>Record</strong>，而不是打开现有 <strong>Record</strong>。</span><span class="sxs-lookup"><span data-stu-id="ddca9-123">Creates a new <strong>Record</strong> of type <a href="recordtypeenum.md">adStructDoc</a>, instead of opening an existing <strong>Record</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddca9-124"><strong>adFailIfNotExists</strong></span><span class="sxs-lookup"><span data-stu-id="ddca9-124"><strong>adFailIfNotExists</strong></span></span></p></td>
<td><p><span data-ttu-id="ddca9-125">-1</span><span class="sxs-lookup"><span data-stu-id="ddca9-125">-1</span></span></p></td>
<td><p><span data-ttu-id="ddca9-p104">默认值。如果 <em>Source</em> 指向不存在的节点，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="ddca9-p104">Default. Results in a run-time error if <em>Source</em> points to a non-existent node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddca9-128"><strong>adOpenIfExists</strong></span><span class="sxs-lookup"><span data-stu-id="ddca9-128"><strong>adOpenIfExists</strong></span></span></p></td>
<td><p><span data-ttu-id="ddca9-129">0x2000000</span><span class="sxs-lookup"><span data-stu-id="ddca9-129">0x2000000</span></span></p></td>
<td><p><span data-ttu-id="ddca9-p105">修改创建标志 <strong>adCreateCollection</strong>、<strong>adCreateNonCollection</strong> 和 <strong>adCreateStructDoc</strong>。当通过 OR 使用此值以及某个创建标志值时，如果源 URL 指向现有的节点或 <strong>Record</strong> 对象，则提供程序必须打开现有 <strong>Record</strong>，而不是创建新记录。此值不能与 <strong>adCreateOverwrite</strong> 一起使用。</span><span class="sxs-lookup"><span data-stu-id="ddca9-p105">Modifies the creation flags <strong>adCreateCollection</strong>, <strong>adCreateNonCollection</strong>, and <strong>adCreateStructDoc</strong>. When OR is used with this value and one of the creation flag values, if the source URL points to an existing node or <strong>Record</strong> object, then the provider must open the existing <strong>Record</strong> instead of creating a new one. This value cannot be used together with <strong>adCreateOverwrite</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="ddca9-133">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="ddca9-133">ADO/WFC equivalent</span></span>

<span data-ttu-id="ddca9-134">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="ddca9-134">These constants do not have ADO/WFC equivalents.</span></span>

