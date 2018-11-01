---
title: Hierarchy 对象 (ADO MD)
TOCTitle: Hierarchy Object (ADO MD)
ms:assetid: 26e4e690-59ad-fb87-66b0-f3310df42d0c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249031(v=office.15)
ms:contentKeyID: 48543825
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ad6eb40873d0cd88b441adaa5568ad57dced83c6
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869783"
---
# <a name="hierarchy-object-ado-md"></a><span data-ttu-id="7d43c-102">Hierarchy 对象 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="7d43c-102">Hierarchy Object (ADO MD)</span></span>


<span data-ttu-id="7d43c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7d43c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7d43c-p101">代表可将某个 [Dimension](dimension-object-ado-md.md) 的成员进行聚合或"汇总"的一种方式。可以在一个或多个层次结构上聚合一个维度。</span><span class="sxs-lookup"><span data-stu-id="7d43c-p101">Represents one way in which the members of a [dimension](dimension-object-ado-md.md) can be aggregated or "rolled up." A dimension can be aggregated along one or more hierarchies.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d43c-106">说明</span><span class="sxs-lookup"><span data-stu-id="7d43c-106">Remarks</span></span>

<span data-ttu-id="7d43c-107">使用 **Hierarchy** 对象的集合和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7d43c-107">With the collections and properties of a **Hierarchy** object, you can do the following:</span></span>

  - <span data-ttu-id="7d43c-108">使用 **Name** 和 [UniqueName](name-property-ado-md.md) 属性标识 [Hierarchy](uniquename-property-ado-md.md) 。</span><span class="sxs-lookup"><span data-stu-id="7d43c-108">Identify the **Hierarchy** with the [Name](name-property-ado-md.md) and [UniqueName](uniquename-property-ado-md.md) properties.</span></span>

  - <span data-ttu-id="7d43c-109">使用 **Description** 属性返回描述 [Hierarchy](description-property-ado-md.md) 的有意义的字符串。</span><span class="sxs-lookup"><span data-stu-id="7d43c-109">Return a meaningful string that describes the **Hierarchy** with the [Description](description-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="7d43c-110">使用 [Levels](level-object-ado-md.md) 集合返回构成 **Hierarchy** 的 [Level](levels-collection-ado-md.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="7d43c-110">Return the [Level](level-object-ado-md.md) objects that make up the **Hierarchy** with the [Levels](levels-collection-ado-md.md) collection.</span></span>

  - <span data-ttu-id="7d43c-111">使用标准 ADO [Properties](properties-collection-ado.md) 集合获取有关 **Hierarchy** 对象的附加信息。</span><span class="sxs-lookup"><span data-stu-id="7d43c-111">Use the standard ADO [Properties](properties-collection-ado.md) collection to obtain additional information about the **Hierarchy** object.</span></span>

<span data-ttu-id="7d43c-p102">**Properties** 集合包含提供程序提供的属性。下表列出了可能可用的属性。实际的属性列表可能有所不同，具体取决于提供程序的实现。有关可用属性的更完整列表，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="7d43c-p102">The **Properties** collection contains provider-supplied properties. The following table lists properties that might be available. The actual property list may differ depending upon the implementation of the provider. See the documentation for your provider for a more complete list of available properties.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7d43c-116">名称</span><span class="sxs-lookup"><span data-stu-id="7d43c-116">Name</span></span></p></th>
<th><p><span data-ttu-id="7d43c-117">说明</span><span class="sxs-lookup"><span data-stu-id="7d43c-117">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d43c-118">AllMember</span><span class="sxs-lookup"><span data-stu-id="7d43c-118">AllMember</span></span></p></td>
<td><p><span data-ttu-id="7d43c-119">位于此层次结构中最高汇总级别的成员。</span><span class="sxs-lookup"><span data-stu-id="7d43c-119">The member at the highest level of rollup in the hierarchy.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d43c-120">CatalogName</span><span class="sxs-lookup"><span data-stu-id="7d43c-120">CatalogName</span></span></p></td>
<td><p><span data-ttu-id="7d43c-121">此多维数据集所属的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="7d43c-121">The name of the catalog to which this cube belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d43c-122">多维数据集名称</span><span class="sxs-lookup"><span data-stu-id="7d43c-122">CubeName</span></span></p></td>
<td><p><span data-ttu-id="7d43c-123">多维数据集的名称。</span><span class="sxs-lookup"><span data-stu-id="7d43c-123">The name of the cube.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d43c-124">DefaultMember</span><span class="sxs-lookup"><span data-stu-id="7d43c-124">DefaultMember</span></span></p></td>
<td><p><span data-ttu-id="7d43c-125">此层次结构的默认成员的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="7d43c-125">The unique name of the default member for this hierarchy.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d43c-126">Description</span><span class="sxs-lookup"><span data-stu-id="7d43c-126">Description</span></span></p></td>
<td><p><span data-ttu-id="7d43c-127">层次结构的有意义的说明。</span><span class="sxs-lookup"><span data-stu-id="7d43c-127">A meaningful description of the hierarchy.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d43c-128">DimensionType</span><span class="sxs-lookup"><span data-stu-id="7d43c-128">DimensionType</span></span></p></td>
<td><p><span data-ttu-id="7d43c-129">此层次结构所属的维的类型。</span><span class="sxs-lookup"><span data-stu-id="7d43c-129">The type of dimension to which this hierarchy belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d43c-130">DimensionUniqueName</span><span class="sxs-lookup"><span data-stu-id="7d43c-130">DimensionUniqueName</span></span></p></td>
<td><p><span data-ttu-id="7d43c-131">维的明确名称。</span><span class="sxs-lookup"><span data-stu-id="7d43c-131">The unambiguous name of the dimension.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d43c-132">HierarchyCaption</span><span class="sxs-lookup"><span data-stu-id="7d43c-132">HierarchyCaption</span></span></p></td>
<td><p><span data-ttu-id="7d43c-133">与层次结构关联的标签或标题。</span><span class="sxs-lookup"><span data-stu-id="7d43c-133">A label or caption associated with the hierarchy.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d43c-134">HierarchyCardinality</span><span class="sxs-lookup"><span data-stu-id="7d43c-134">HierarchyCardinality</span></span></p></td>
<td><p><span data-ttu-id="7d43c-135">层次结构中的成员数。</span><span class="sxs-lookup"><span data-stu-id="7d43c-135">The number of members in the hierarchy.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d43c-136">HierarchyGUID</span><span class="sxs-lookup"><span data-stu-id="7d43c-136">HierarchyGUID</span></span></p></td>
<td><p><span data-ttu-id="7d43c-137">层次结构的 GUID。</span><span class="sxs-lookup"><span data-stu-id="7d43c-137">The GUID of the hierarchy.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d43c-138">HierarchyName</span><span class="sxs-lookup"><span data-stu-id="7d43c-138">HierarchyName</span></span></p></td>
<td><p><span data-ttu-id="7d43c-139">层次结构的名称。</span><span class="sxs-lookup"><span data-stu-id="7d43c-139">The name of the hierarchy.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d43c-140">HierarchyUniqueName</span><span class="sxs-lookup"><span data-stu-id="7d43c-140">HierarchyUniqueName</span></span></p></td>
<td><p><span data-ttu-id="7d43c-141">层次结构的明确名称。</span><span class="sxs-lookup"><span data-stu-id="7d43c-141">The unambiguous name of the hierarchy.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d43c-142">SchemaName</span><span class="sxs-lookup"><span data-stu-id="7d43c-142">SchemaName</span></span></p></td>
<td><p><span data-ttu-id="7d43c-143">此多维数据集所属的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="7d43c-143">The name of the schema to which this cube belongs.</span></span></p></td>
</tr>
</tbody>
</table>

