---
title: 层次结构对象 (ADO MD)
TOCTitle: Hierarchy object (ADO MD)
ms:assetid: 26e4e690-59ad-fb87-66b0-f3310df42d0c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249031(v=office.15)
ms:contentKeyID: 48543825
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c6668dfd40f7d0d26bcfa2ca4149acdc713e14c6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291927"
---
# <a name="hierarchy-object-ado-md"></a><span data-ttu-id="1be85-102">层次结构对象 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="1be85-102">Hierarchy object (ADO MD)</span></span>


<span data-ttu-id="1be85-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="1be85-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1be85-p101">代表可将某个 [Dimension](dimension-object-ado-md.md) 的成员进行聚合或"汇总"的一种方式。可以在一个或多个层次结构上聚合一个维度。</span><span class="sxs-lookup"><span data-stu-id="1be85-p101">Represents one way in which the members of a [dimension](dimension-object-ado-md.md) can be aggregated or "rolled up." A dimension can be aggregated along one or more hierarchies.</span></span>

## <a name="remarks"></a><span data-ttu-id="1be85-106">注解</span><span class="sxs-lookup"><span data-stu-id="1be85-106">Remarks</span></span>

<span data-ttu-id="1be85-107">使用 **Hierarchy** 对象的集合和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1be85-107">With the collections and properties of a **Hierarchy** object, you can do the following:</span></span>

  - <span data-ttu-id="1be85-108">使用 **Name** 和 [UniqueName](name-property-ado-md.md) 属性标识 [Hierarchy](uniquename-property-ado-md.md) 。</span><span class="sxs-lookup"><span data-stu-id="1be85-108">Identify the **Hierarchy** with the [Name](name-property-ado-md.md) and [UniqueName](uniquename-property-ado-md.md) properties.</span></span>

  - <span data-ttu-id="1be85-109">使用 **Description** 属性返回描述 [Hierarchy](description-property-ado-md.md) 的有意义的字符串。</span><span class="sxs-lookup"><span data-stu-id="1be85-109">Return a meaningful string that describes the **Hierarchy** with the [Description](description-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="1be85-110">使用 [Levels](level-object-ado-md.md) 集合返回构成 **Hierarchy** 的 [Level](levels-collection-ado-md.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="1be85-110">Return the [Level](level-object-ado-md.md) objects that make up the **Hierarchy** with the [Levels](levels-collection-ado-md.md) collection.</span></span>

  - <span data-ttu-id="1be85-111">使用标准 ADO [Properties](properties-collection-ado.md) 集合获取有关 **Hierarchy** 对象的附加信息。</span><span class="sxs-lookup"><span data-stu-id="1be85-111">Use the standard ADO [Properties](properties-collection-ado.md) collection to obtain additional information about the **Hierarchy** object.</span></span>

<span data-ttu-id="1be85-p102">**Properties** 集合包含提供程序提供的属性。下表列出了可能可用的属性。实际的属性列表可能有所不同，具体取决于提供程序的实现。有关可用属性的更完整列表，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="1be85-p102">The **Properties** collection contains provider-supplied properties. The following table lists properties that might be available. The actual property list may differ depending upon the implementation of the provider. See the documentation for your provider for a more complete list of available properties.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1be85-116">名称</span><span class="sxs-lookup"><span data-stu-id="1be85-116">Name</span></span></p></th>
<th><p><span data-ttu-id="1be85-117">说明</span><span class="sxs-lookup"><span data-stu-id="1be85-117">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1be85-118">AllMember</span><span class="sxs-lookup"><span data-stu-id="1be85-118">AllMember</span></span></p></td>
<td><p><span data-ttu-id="1be85-119">位于此层次结构中最高汇总级别的成员。</span><span class="sxs-lookup"><span data-stu-id="1be85-119">The member at the highest level of rollup in the hierarchy.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be85-120">CatalogName</span><span class="sxs-lookup"><span data-stu-id="1be85-120">CatalogName</span></span></p></td>
<td><p><span data-ttu-id="1be85-121">此多维数据集所属的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="1be85-121">The name of the catalog to which this cube belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be85-122">CubeName</span><span class="sxs-lookup"><span data-stu-id="1be85-122">CubeName</span></span></p></td>
<td><p><span data-ttu-id="1be85-123">多维数据集的名称。</span><span class="sxs-lookup"><span data-stu-id="1be85-123">The name of the cube.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be85-124">DefaultMember</span><span class="sxs-lookup"><span data-stu-id="1be85-124">DefaultMember</span></span></p></td>
<td><p><span data-ttu-id="1be85-125">此层次结构的默认成员的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="1be85-125">The unique name of the default member for this hierarchy.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be85-126">说明</span><span class="sxs-lookup"><span data-stu-id="1be85-126">Description</span></span></p></td>
<td><p><span data-ttu-id="1be85-127">层次结构的有意义的说明。</span><span class="sxs-lookup"><span data-stu-id="1be85-127">A meaningful description of the hierarchy.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be85-128">DimensionType</span><span class="sxs-lookup"><span data-stu-id="1be85-128">DimensionType</span></span></p></td>
<td><p><span data-ttu-id="1be85-129">此层次结构所属的维的类型。</span><span class="sxs-lookup"><span data-stu-id="1be85-129">The type of dimension to which this hierarchy belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be85-130">DimensionUniqueName</span><span class="sxs-lookup"><span data-stu-id="1be85-130">DimensionUniqueName</span></span></p></td>
<td><p><span data-ttu-id="1be85-131">维的明确名称。</span><span class="sxs-lookup"><span data-stu-id="1be85-131">The unambiguous name of the dimension.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be85-132">HierarchyCaption</span><span class="sxs-lookup"><span data-stu-id="1be85-132">HierarchyCaption</span></span></p></td>
<td><p><span data-ttu-id="1be85-133">与层次结构关联的标签或标题。</span><span class="sxs-lookup"><span data-stu-id="1be85-133">A label or caption associated with the hierarchy.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be85-134">HierarchyCardinality</span><span class="sxs-lookup"><span data-stu-id="1be85-134">HierarchyCardinality</span></span></p></td>
<td><p><span data-ttu-id="1be85-135">层次结构中的成员数。</span><span class="sxs-lookup"><span data-stu-id="1be85-135">The number of members in the hierarchy.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be85-136">HierarchyGUID</span><span class="sxs-lookup"><span data-stu-id="1be85-136">HierarchyGUID</span></span></p></td>
<td><p><span data-ttu-id="1be85-137">层次结构的 GUID。</span><span class="sxs-lookup"><span data-stu-id="1be85-137">The GUID of the hierarchy.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be85-138">HierarchyName</span><span class="sxs-lookup"><span data-stu-id="1be85-138">HierarchyName</span></span></p></td>
<td><p><span data-ttu-id="1be85-139">层次结构的名称。</span><span class="sxs-lookup"><span data-stu-id="1be85-139">The name of the hierarchy.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1be85-140">HierarchyUniqueName</span><span class="sxs-lookup"><span data-stu-id="1be85-140">HierarchyUniqueName</span></span></p></td>
<td><p><span data-ttu-id="1be85-141">层次结构的明确名称。</span><span class="sxs-lookup"><span data-stu-id="1be85-141">The unambiguous name of the hierarchy.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1be85-142">SchemaName</span><span class="sxs-lookup"><span data-stu-id="1be85-142">SchemaName</span></span></p></td>
<td><p><span data-ttu-id="1be85-143">此多维数据集所属的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="1be85-143">The name of the schema to which this cube belongs.</span></span></p></td>
</tr>
</tbody>
</table>

