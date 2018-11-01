---
title: Dimension 对象 (ADO MD)
TOCTitle: Dimension Object (ADO MD)
ms:assetid: 12f43cfc-c74e-a2e8-7f6e-75fc68472c4b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248902(v=office.15)
ms:contentKeyID: 48543355
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e3581f9bce5e2e56b341928df3415a1b9b223beb
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25872884"
---
# <a name="dimension-object-ado-md"></a><span data-ttu-id="8279e-102">Dimension 对象 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="8279e-102">Dimension Object (ADO MD)</span></span>


<span data-ttu-id="8279e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8279e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8279e-104">代表多维数据集的维度之一，包含一个或多个成员层次结构。</span><span class="sxs-lookup"><span data-stu-id="8279e-104">Represents one of the dimensions of a multidimensional cube, containing one or more hierarchies of members.</span></span>

## <a name="remarks"></a><span data-ttu-id="8279e-105">说明</span><span class="sxs-lookup"><span data-stu-id="8279e-105">Remarks</span></span>

<span data-ttu-id="8279e-106">使用 **Dimension** 对象的集合和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8279e-106">With the collections and properties of a **Dimension** object, you can do the following:</span></span>

  - <span data-ttu-id="8279e-107">使用 **Name** 和 [UniqueName](name-property-ado-md.md) 属性标识 [Dimension](uniquename-property-ado-md.md) 。</span><span class="sxs-lookup"><span data-stu-id="8279e-107">Identify the **Dimension** with the [Name](name-property-ado-md.md) and [UniqueName](uniquename-property-ado-md.md) properties.</span></span>

  - <span data-ttu-id="8279e-108">使用 **Description** 属性返回描述 [Dimension](description-property-ado-md.md) 的有意义的字符串。</span><span class="sxs-lookup"><span data-stu-id="8279e-108">Return a meaningful string that describes the **Dimension** with the [Description](description-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="8279e-109">使用 [Hierarchies](hierarchy-object-ado-md.md) 集合返回构成 **Dimension** 的 [Hierarchy](hierarchies-collection-ado-md.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="8279e-109">Return the [Hierarchy](hierarchy-object-ado-md.md) objects that make up the **Dimension** with the [Hierarchies](hierarchies-collection-ado-md.md) collection.</span></span>

  - <span data-ttu-id="8279e-110">使用标准 ADO [Properties](properties-collection-ado.md) 集合获取有关 **Dimension** 对象的附加信息。</span><span class="sxs-lookup"><span data-stu-id="8279e-110">Use the standard ADO [Properties](properties-collection-ado.md) collection to obtain additional information about the **Dimension** object.</span></span>

<span data-ttu-id="8279e-p101">**Properties** 集合包含提供程序提供的属性。下表列出了可能可用的属性。实际的属性列表可能有所不同，具体取决于提供程序的实现。有关可用属性的更完整列表，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="8279e-p101">The **Properties** collection contains provider-supplied properties. The following table lists properties that might be available. The actual property list may differ depending upon the implementation of the provider. See the documentation for your provider for a more complete list of available properties.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8279e-115">名称</span><span class="sxs-lookup"><span data-stu-id="8279e-115">Name</span></span></p></th>
<th><p><span data-ttu-id="8279e-116">说明</span><span class="sxs-lookup"><span data-stu-id="8279e-116">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8279e-117">CatalogName</span><span class="sxs-lookup"><span data-stu-id="8279e-117">CatalogName</span></span></p></td>
<td><p><span data-ttu-id="8279e-118">此多维数据集所属的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="8279e-118">The name of the catalog to which this cube belongs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8279e-119">多维数据集名称</span><span class="sxs-lookup"><span data-stu-id="8279e-119">CubeName</span></span></p></td>
<td><p><span data-ttu-id="8279e-120">多维数据集的名称。</span><span class="sxs-lookup"><span data-stu-id="8279e-120">The name of the cube.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8279e-121">DefaultHierarchy</span><span class="sxs-lookup"><span data-stu-id="8279e-121">DefaultHierarchy</span></span></p></td>
<td><p><span data-ttu-id="8279e-122">默认层次结构的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="8279e-122">The unique name of the default hierarchy.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8279e-123">说明</span><span class="sxs-lookup"><span data-stu-id="8279e-123">Description</span></span></p></td>
<td><p><span data-ttu-id="8279e-124">多维数据集的有意义的说明。</span><span class="sxs-lookup"><span data-stu-id="8279e-124">A meaningful description of the cube.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8279e-125">DimensionCaption</span><span class="sxs-lookup"><span data-stu-id="8279e-125">DimensionCaption</span></span></p></td>
<td><p><span data-ttu-id="8279e-126">与维关联的标签或标题。</span><span class="sxs-lookup"><span data-stu-id="8279e-126">A label or caption associated with the dimension.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8279e-127">DimensionCardinality</span><span class="sxs-lookup"><span data-stu-id="8279e-127">DimensionCardinality</span></span></p></td>
<td><p><span data-ttu-id="8279e-128">维中的成员数。</span><span class="sxs-lookup"><span data-stu-id="8279e-128">The number of members in the dimension.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8279e-129">DimensionGUID</span><span class="sxs-lookup"><span data-stu-id="8279e-129">DimensionGUID</span></span></p></td>
<td><p><span data-ttu-id="8279e-130">维的 GUID。</span><span class="sxs-lookup"><span data-stu-id="8279e-130">The GUID of the dimension.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8279e-131">维度</span><span class="sxs-lookup"><span data-stu-id="8279e-131">DimensionName</span></span></p></td>
<td><p><span data-ttu-id="8279e-132">维的名称。</span><span class="sxs-lookup"><span data-stu-id="8279e-132">The name of the dimension.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8279e-133">DimensionOrdinal</span><span class="sxs-lookup"><span data-stu-id="8279e-133">DimensionOrdinal</span></span></p></td>
<td><p><span data-ttu-id="8279e-134">构成多维数据集的维组中维的序号。</span><span class="sxs-lookup"><span data-stu-id="8279e-134">The ordinal number of the dimension among the group of dimensions that form the cube.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8279e-135">DimensionType</span><span class="sxs-lookup"><span data-stu-id="8279e-135">DimensionType</span></span></p></td>
<td><p><span data-ttu-id="8279e-136">维类型。</span><span class="sxs-lookup"><span data-stu-id="8279e-136">The dimension type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8279e-137">DimensionUniqueName</span><span class="sxs-lookup"><span data-stu-id="8279e-137">DimensionUniqueName</span></span></p></td>
<td><p><span data-ttu-id="8279e-138">维的明确名称。</span><span class="sxs-lookup"><span data-stu-id="8279e-138">The unambiguous name of the dimension.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8279e-139">SchemaName</span><span class="sxs-lookup"><span data-stu-id="8279e-139">SchemaName</span></span></p></td>
<td><p><span data-ttu-id="8279e-140">此多维数据集所属的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="8279e-140">The name of the schema to which this cube belongs.</span></span></p></td>
</tr>
</tbody>
</table>

