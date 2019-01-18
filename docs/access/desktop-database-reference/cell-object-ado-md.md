---
title: Cell 对象 (ADO MD)
TOCTitle: Cell object (ADO MD)
ms:assetid: b9d00b71-1f40-5bd1-4b89-fbdb59c552ba
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249892(v=office.15)
ms:contentKeyID: 48547356
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7bb2a479789a8c5bd1825b6cb04e602e0b829dfb
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28725985"
---
# <a name="cell-object-ado-md"></a><span data-ttu-id="9ddf1-102">Cell 对象 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="9ddf1-102">Cell object (ADO MD)</span></span>


<span data-ttu-id="9ddf1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9ddf1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9ddf1-104">代表处于单元格集中包含的坐标轴交点处的数据。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-104">Represents the data at the intersection of axis coordinates contained in a cellset.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ddf1-105">说明</span><span class="sxs-lookup"><span data-stu-id="9ddf1-105">Remarks</span></span>

<span data-ttu-id="9ddf1-106">**Cell** 对象由 [Cellset](item-property-ado-md-cellset.md) 对象的 [Item](cellset-object-ado-md.md) 属性返回。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-106">A **Cell** object is returned by the [Item](item-property-ado-md-cellset.md) property of a [Cellset](cellset-object-ado-md.md) object.</span></span>

<span data-ttu-id="9ddf1-107">使用 **Cell** 对象的集合和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9ddf1-107">With the collections and properties of a **Cell** object, you can do the following:</span></span>

- <span data-ttu-id="9ddf1-108">使用 **Value** 属性返回 [Cell](value-property-ado-md.md) 中的数据。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-108">Return the data in the **Cell** with the [Value](value-property-ado-md.md) property.</span></span>

- <span data-ttu-id="9ddf1-109">使用 **FormattedValue** 属性返回代表 [Value](formattedvalue-property-ado-md.md) 属性的带格式显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-109">Return the string representing the formatted display of the **Value** property with the [FormattedValue](formattedvalue-property-ado-md.md) property.</span></span>

- <span data-ttu-id="9ddf1-110">使用 **Ordinal** 属性返回 **Cellset** 中的 [Cell](ordinal-property-ado-md-cell.md) 的序号值。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-110">Return the ordinal value of the **Cell** within the **Cellset** with the [Ordinal](ordinal-property-ado-md-cell.md) property.</span></span>

- <span data-ttu-id="9ddf1-111">使用 **Positions** 集合确定 [CubeDef](cubedef-object-ado-md.md) 中的 [Cell](positions-collection-ado-md.md) 的位置。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-111">Determine the position of the **Cell** within the [CubeDef](cubedef-object-ado-md.md) with the [Positions](positions-collection-ado-md.md) collection.</span></span>

- <span data-ttu-id="9ddf1-112">使用标准 ADO **Properties** 集合检索有关 [Cell](properties-collection-ado.md) 的其他信息。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-112">Retrieve other information about the **Cell** with the standard ADO [Properties](properties-collection-ado.md) collection.</span></span>

<span data-ttu-id="9ddf1-p101">**Properties** 集合包含提供程序提供的属性。下表列出了可能可用的属性。实际的属性列表可能有所不同，具体取决于提供程序的实现。有关可用属性的更完整列表，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-p101">The **Properties** collection contains provider-supplied properties. The following table lists properties that might be available. The actual property list may differ depending upon the implementation of the provider. See the documentation for your provider for a more complete list of available properties.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ddf1-117">Name</span><span class="sxs-lookup"><span data-stu-id="9ddf1-117">Name</span></span></p></th>
<th><p><span data-ttu-id="9ddf1-118">说明</span><span class="sxs-lookup"><span data-stu-id="9ddf1-118">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ddf1-119">BackColor</span><span class="sxs-lookup"><span data-stu-id="9ddf1-119">BackColor</span></span></p></td>
<td><p><span data-ttu-id="9ddf1-120">显示单元格时使用的背景色。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-120">Background color used when displaying the cell.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ddf1-121">FontFlags</span><span class="sxs-lookup"><span data-stu-id="9ddf1-121">FontFlags</span></span></p></td>
<td><p><span data-ttu-id="9ddf1-122">详细描述应用于字体的效果的位掩码。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-122">Bitmask detailing effects on the font.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ddf1-123">FontName</span><span class="sxs-lookup"><span data-stu-id="9ddf1-123">FontName</span></span></p></td>
<td><p><span data-ttu-id="9ddf1-124">用于显示单元格值的字体。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-124">Font used to display the cell value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ddf1-125">FontSize</span><span class="sxs-lookup"><span data-stu-id="9ddf1-125">FontSize</span></span></p></td>
<td><p><span data-ttu-id="9ddf1-126">用于显示单元格值的字号。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-126">Font size used to display the cell value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ddf1-127">ForeColor</span><span class="sxs-lookup"><span data-stu-id="9ddf1-127">ForeColor</span></span></p></td>
<td><p><span data-ttu-id="9ddf1-128">显示单元格时使用的前景色。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-128">Foreground color used when displaying the cell.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ddf1-129">FormatString</span><span class="sxs-lookup"><span data-stu-id="9ddf1-129">FormatString</span></span></p></td>
<td><p><span data-ttu-id="9ddf1-130">格式字符串中的值。</span><span class="sxs-lookup"><span data-stu-id="9ddf1-130">Value in a formatted string.</span></span></p></td>
</tr>
</tbody>
</table>

