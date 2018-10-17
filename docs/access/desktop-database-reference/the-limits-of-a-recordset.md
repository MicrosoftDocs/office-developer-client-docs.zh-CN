---
title: 记录集的限制
TOCTitle: The Limits of a Recordset
ms:assetid: 51e27c95-e0c3-7fdc-ac11-891553620376
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249266(v=office.15)
ms:contentKeyID: 48544833
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e13e907c27fa6f764aae6ee499f0bd2854f9640b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465806"
---
# <a name="the-limits-of-a-recordset"></a><span data-ttu-id="305c7-102">记录集的限制</span><span class="sxs-lookup"><span data-stu-id="305c7-102">The Limits of a Recordset</span></span>


<span data-ttu-id="305c7-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="305c7-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="305c7-p101">使用 **BOF** 和 **EOF** 属性，可以确定 **Recordset** 对象是否包含记录，或者在记录之间移动时是否超出了 **Recordset** 对象的限制。将 **BOF** 和 **EOF** 视为位于 **Recordset** 开头和末尾的"幻影"记录。基于 **检查数据**的示例 [Recordset](chapter-3-examining-data.md) 构建的对象如下所示：</span><span class="sxs-lookup"><span data-stu-id="305c7-p101">Use the **BOF** and **EOF** properties to determine whether a **Recordset** object contains records or whether you've gone beyond the limits of a **Recordset** object when you move from record to record. Think of **BOF** and **EOF** as "phantom" records that are positioned at the beginning and end of the **Recordset**. Building on the sample **Recordset** from [Examining Data](chapter-3-examining-data.md), it would now look like this:</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="305c7-107">ProductID</span><span class="sxs-lookup"><span data-stu-id="305c7-107">ProductID</span></span></p></th>
<th><p><span data-ttu-id="305c7-108">ProductName</span><span class="sxs-lookup"><span data-stu-id="305c7-108">ProductName</span></span></p></th>
<th><p><span data-ttu-id="305c7-109">单价</span><span class="sxs-lookup"><span data-stu-id="305c7-109">UnitPrice</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="305c7-110">BOF</span><span class="sxs-lookup"><span data-stu-id="305c7-110">BOF</span></span></p></td>
<td><p><br />
</p></td>
<td><p><br />
</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305c7-111">7</span><span class="sxs-lookup"><span data-stu-id="305c7-111">7</span></span></p></td>
<td><p><span data-ttu-id="305c7-112">海鲜粉</span><span class="sxs-lookup"><span data-stu-id="305c7-112">Uncle Bob's Organic Dried Pears</span></span></p></td>
<td><p><span data-ttu-id="305c7-113">30.0000</span><span class="sxs-lookup"><span data-stu-id="305c7-113">30.0000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305c7-114">14</span><span class="sxs-lookup"><span data-stu-id="305c7-114">14</span></span></p></td>
<td><p><span data-ttu-id="305c7-115">沙茶</span><span class="sxs-lookup"><span data-stu-id="305c7-115">Tofu</span></span></p></td>
<td><p><span data-ttu-id="305c7-116">23.2500</span><span class="sxs-lookup"><span data-stu-id="305c7-116">23.2500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305c7-117">28</span><span class="sxs-lookup"><span data-stu-id="305c7-117">28</span></span></p></td>
<td><p><span data-ttu-id="305c7-118">烤肉酱</span><span class="sxs-lookup"><span data-stu-id="305c7-118">Rssle Sauerkraut</span></span></p></td>
<td><p><span data-ttu-id="305c7-119">45.6000</span><span class="sxs-lookup"><span data-stu-id="305c7-119">45.6000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305c7-120">51</span><span class="sxs-lookup"><span data-stu-id="305c7-120">51</span></span></p></td>
<td><p><span data-ttu-id="305c7-121">猪肉干</span><span class="sxs-lookup"><span data-stu-id="305c7-121">Manjimup Dried Apples</span></span></p></td>
<td><p><span data-ttu-id="305c7-122">53.0000</span><span class="sxs-lookup"><span data-stu-id="305c7-122">53.0000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305c7-123">74</span><span class="sxs-lookup"><span data-stu-id="305c7-123">74</span></span></p></td>
<td><p><span data-ttu-id="305c7-124">鸡精</span><span class="sxs-lookup"><span data-stu-id="305c7-124">Longlife Tofu</span></span></p></td>
<td><p><span data-ttu-id="305c7-125">10.0000</span><span class="sxs-lookup"><span data-stu-id="305c7-125">10.0000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305c7-126">EOF</span><span class="sxs-lookup"><span data-stu-id="305c7-126">EOF</span></span></p></td>
<td><p><br />
</p></td>
<td><p><br />
</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="305c7-127">如果当前记录位于第一个记录之前，则 **BOF** 属性返回 **True** (-1)，如果当前记录就是第一个记录或者位于第一个记录之后，则返回 **False** (0)。</span><span class="sxs-lookup"><span data-stu-id="305c7-127">The **BOF** property returns **True** (-1) if the current record position is before the first record and **False** (0) if the current record position is on or after the first record.</span></span>

<span data-ttu-id="305c7-128">如果当前记录位于最后一个记录之后，则 **EOF** 属性返回 **True** ，如果当前记录就是最后一个记录或者位于最后一个记录之前，则返回 **False** 。</span><span class="sxs-lookup"><span data-stu-id="305c7-128">The **EOF** property returns **True** if the current record position is after the last record and **False** if the current record position is on or before the last record.</span></span>

<span data-ttu-id="305c7-129">如果 **BOF** 或 **EOF** 属性为 **True** ，则说明当前无记录，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="305c7-129">If either the **BOF** or **EOF** property is **True**, there is no current record, as shown in the following code:</span></span>

```vb 
 
If oRs.BOF And oRs.EOF Then 
 ' Command returned no records. 
End If 
```

<span data-ttu-id="305c7-130">如果打开不包含任何记录的 **Recordset** 对象，则 **BOF** 和 **EOF** 属性均设置为 **True** ，而 **Recordset** 对象的 **RecordCount** 属性设置的值取决于游标的类型。</span><span class="sxs-lookup"><span data-stu-id="305c7-130">If you open a **Recordset** object containing no records, the **BOF** and **EOF** properties are both set to **True** and the value of the **Recordset** object's **RecordCount** property setting depends on the cursor type.</span></span> <span data-ttu-id="305c7-131">对于动态游标将返回-1 (**CursorType** = **adOpenDynamic**) 的其他游标，则返回 0。</span><span class="sxs-lookup"><span data-stu-id="305c7-131">-1 will be returned for dynamic cursors (**CursorType** = **adOpenDynamic**) and 0 will be returned for other cursors.</span></span>

<span data-ttu-id="305c7-132">如果打开至少包含一个记录的 **Recordset** 对象，则第一个记录是当前记录， **BOF** 和 **EOF** 属性均为 **False** 。</span><span class="sxs-lookup"><span data-stu-id="305c7-132">When you open a **Recordset** object that contains at least one record, the first record is the current record and the **BOF** and **EOF** properties are **False**.</span></span>

<span data-ttu-id="305c7-p103">如果删除 **Recordset** 对象中最后一个剩余的记录，则游标将保留在未定状态。 **BOF** 和 **EOF** 属性可能一直保留在 **False** ，直到您尝试重新定位当前的记录，具体情况取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="305c7-p103">If you delete the last remaining record in the **Recordset** object, the cursor is left in an indeterminate state. The **BOF** and **EOF** properties may remain **False** until you attempt to reposition the current record, depending upon the provider.</span></span>
