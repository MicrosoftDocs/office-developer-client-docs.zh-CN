---
title: Level 对象 (ADO MD)
TOCTitle: Level object (ADO MD)
ms:assetid: ddbcabce-8777-1068-98a3-be209084f497
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250121(v=office.15)
ms:contentKeyID: 48548160
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 70fb359aa4faa0bcfc99f0b1700b0eb51f665bc0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290112"
---
# <a name="level-object-ado-md"></a><span data-ttu-id="ff8d3-102">Level 对象 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="ff8d3-102">Level object (ADO MD)</span></span>


<span data-ttu-id="ff8d3-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ff8d3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ff8d3-104">包含一组成员，其中每个成员在层次结构中有相同的等级。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-104">Contains a set of members, each of which has the same rank within a hierarchy.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff8d3-105">注解</span><span class="sxs-lookup"><span data-stu-id="ff8d3-105">Remarks</span></span>

<span data-ttu-id="ff8d3-106">使用 **Level** 对象的集合和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ff8d3-106">With the collections and properties of a **Level** object, you can do the following:</span></span>

  - <span data-ttu-id="ff8d3-107">使用 **Name** 和 [UniqueName](name-property-ado-md.md) 属性标识 [Level](uniquename-property-ado-md.md) 。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-107">Identify the **Level** with the [Name](name-property-ado-md.md) and [UniqueName](uniquename-property-ado-md.md) properties.</span></span>

  - <span data-ttu-id="ff8d3-108">使用 **Caption** 属性返回在显示 [Level](caption-property-ado-md.md) 时使用的字符串。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-108">Return a string to use when displaying the **Level** with the [Caption](caption-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="ff8d3-109">使用 **Description** 属性返回描述 [Level](description-property-ado-md.md) 的有意义的字符串。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-109">Return a meaningful string that describes the **Level** with the [Description](description-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="ff8d3-110">使用 [Members](member-object-ado-md.md) 集合返回构成 **Level** 的 [Member](members-collection-ado-md.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-110">Return the [Member](member-object-ado-md.md) objects that make up the **Level** with the [Members](members-collection-ado-md.md) collection.</span></span>

  - <span data-ttu-id="ff8d3-111">使用 **Depth** 属性返回来自 [Level](depth-property-ado-md.md) 的根的级别数。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-111">Return the number of levels from the root of the **Level** with the [Depth](depth-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="ff8d3-112">使用标准 ADO [Properties](properties-collection-ado.md) 集合获取有关 **Level** 对象的附加信息。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-112">Use the standard ADO [Properties](properties-collection-ado.md) collection to obtain additional information about the **Level** object.</span></span>

<span data-ttu-id="ff8d3-p101">**Properties** 集合包含提供程序提供的属性。下表列出了可能可用的属性。实际的属性列表可能有所不同，具体取决于提供程序的实现。有关可用属性的更完整列表，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-p101">The **Properties** collection contains provider-supplied properties. The following table lists properties that might be available. The actual property list may differ depending upon the implementation of the provider. See the documentation for your provider for a more complete list of available properties.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ff8d3-117">名称</span><span class="sxs-lookup"><span data-stu-id="ff8d3-117">Name</span></span></p></th>
<th><p><span data-ttu-id="ff8d3-118">说明</span><span class="sxs-lookup"><span data-stu-id="ff8d3-118">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff8d3-119">CatalogName</span><span class="sxs-lookup"><span data-stu-id="ff8d3-119">CatalogName</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-120">此多维数据集所属的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-120">The name of the catalog to which this cube belongs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff8d3-121">CubeName</span><span class="sxs-lookup"><span data-stu-id="ff8d3-121">CubeName</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-122">多维数据集的名称。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-122">The name of the cube.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff8d3-123">说明</span><span class="sxs-lookup"><span data-stu-id="ff8d3-123">Description</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-124">级别的有意义的说明。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-124">A meaningful description of the level.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff8d3-125">DimensionUniqueName</span><span class="sxs-lookup"><span data-stu-id="ff8d3-125">DimensionUniqueName</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-126"><a href="dimension-object-ado-md.md">维度</a>的明确名称。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-126">The unambiguous name of the <a href="dimension-object-ado-md.md">dimension</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff8d3-127">HierarchyUniqueName</span><span class="sxs-lookup"><span data-stu-id="ff8d3-127">HierarchyUniqueName</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-128">层次结构的明确名称。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-128">The unambiguous name of the hierarchy.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff8d3-129">LevelCaption</span><span class="sxs-lookup"><span data-stu-id="ff8d3-129">LevelCaption</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-130">与级别关联的标签或标题。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-130">A label or caption associated with the level.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff8d3-131">LevelCardinality</span><span class="sxs-lookup"><span data-stu-id="ff8d3-131">LevelCardinality</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-132">级别中的成员数。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-132">The number of members in the level.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff8d3-133">LevelGUID</span><span class="sxs-lookup"><span data-stu-id="ff8d3-133">LevelGUID</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-134">级别的 GUID。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-134">The GUID of the level.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff8d3-135">LevelName</span><span class="sxs-lookup"><span data-stu-id="ff8d3-135">LevelName</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-136">级别的名称。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-136">Name of the level.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff8d3-137">LevelNumber</span><span class="sxs-lookup"><span data-stu-id="ff8d3-137">LevelNumber</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-138">层次结构的级别和根之间的距离。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-138">The distance between the level and the root of the hierarchy.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff8d3-139">LevelType</span><span class="sxs-lookup"><span data-stu-id="ff8d3-139">LevelType</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-140">级别的类型。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-140">The type of level.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff8d3-141">LevelUniqueName</span><span class="sxs-lookup"><span data-stu-id="ff8d3-141">LevelUniqueName</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-142">级别的明确名称。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-142">The unambiguous name of the level.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff8d3-143">SchemaName</span><span class="sxs-lookup"><span data-stu-id="ff8d3-143">SchemaName</span></span></p></td>
<td><p><span data-ttu-id="ff8d3-144">此多维数据集所属的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="ff8d3-144">The name of the schema to which this cube belongs.</span></span></p></td>
</tr>
</tbody>
</table>

