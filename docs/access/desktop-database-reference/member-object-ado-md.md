---
title: Member 对象 (ADO MD)
TOCTitle: Member object (ADO MD)
ms:assetid: d80c024a-07dc-7a35-f8f2-b4d5b19d89e4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250088(v=office.15)
ms:contentKeyID: 48548025
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 380fdf6c15f6774e27221e8500100870d22350c4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709577"
---
# <a name="member-object-ado-md"></a><span data-ttu-id="50afd-102">Member 对象 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="50afd-102">Member object (ADO MD)</span></span>


<span data-ttu-id="50afd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="50afd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="50afd-104">代表多维数据集中某个级别的某个成员、某个级别的某个成员的子级，或者单元格集的轴上某个位置的某个成员。</span><span class="sxs-lookup"><span data-stu-id="50afd-104">Represents a member of a level in a cube, the children of a member of a level, or a member of a position along an axis of a cellset.</span></span>

## <a name="remarks"></a><span data-ttu-id="50afd-105">说明</span><span class="sxs-lookup"><span data-stu-id="50afd-105">Remarks</span></span>

<span data-ttu-id="50afd-p101">每个 **Member** 的属性各有不同，具体取决于所使用的上下文。 **CubeDef** 中的 [Level](level-object-ado-md.md) 的 [Member](cubedef-object-ado-md.md) 具有一个 [Children](children-property-ado-md.md) 属性，该属性返回层次结构中比当前 **Member** 低一个级别的 **Members** 。对于 **Position** 的 [Member](position-object-ado-md.md) ， **Children** 集合始终为空。另外， [Type](type-property-ado-md.md) 属性仅应用于 **Level** 的 **Members** 。</span><span class="sxs-lookup"><span data-stu-id="50afd-p101">The properties of a **Member** differ depending on the context in which it is used. A **Member** of a [Level](level-object-ado-md.md) in a [CubeDef](cubedef-object-ado-md.md) has a [Children](children-property-ado-md.md) property that returns the **Members** on the next lower level in the hierarchy from the current **Member**. For a **Member** of a [Position](position-object-ado-md.md), the **Children** collection is always empty. Also, the [Type](type-property-ado-md.md) property applies only to **Members** of a **Level**.</span></span>

<span data-ttu-id="50afd-p102">**Position** 的 **Member** 有两个属性 - [DrilledDown](drilleddown-property-ado-md.md) 和 [ParentSameAsPrev](parentsameasprev-property-ado-md.md)，它们在显示 [Cellset](cellset-object-ado-md.md) 时很有用。如果在 **Level** 的 **Member** 上访问这些属性，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="50afd-p102">A **Member** of **Position** has two properties — [DrilledDown](drilleddown-property-ado-md.md) and [ParentSameAsPrev](parentsameasprev-property-ado-md.md) — that are useful when displaying the [Cellset](cellset-object-ado-md.md). An error will occur if these properties are accessed on a **Member** of a **Level**.</span></span>

<span data-ttu-id="50afd-112">使用 **Level** 的 **Member** 对象的集合和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="50afd-112">With the collections and properties of a **Member** object of a **Level**, you can do the following:</span></span>

  - <span data-ttu-id="50afd-113">使用 **Name** 和 [UniqueName](name-property-ado-md.md) 属性标识 [Member](uniquename-property-ado-md.md) 。</span><span class="sxs-lookup"><span data-stu-id="50afd-113">Identify the **Member** with the [Name](name-property-ado-md.md) and [UniqueName](uniquename-property-ado-md.md) properties.</span></span>

  - <span data-ttu-id="50afd-114">使用 **Caption** 属性返回在显示 [Member](caption-property-ado-md.md) 时使用的字符串。</span><span class="sxs-lookup"><span data-stu-id="50afd-114">Return a string to use when displaying the **Member** with the [Caption](caption-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="50afd-115">使用 **Description** 属性返回描述度量或公式 [Member](description-property-ado-md.md) 的有意义的字符串。</span><span class="sxs-lookup"><span data-stu-id="50afd-115">Return a meaningful string that describes a measure or formula **Member** with the [Description](description-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="50afd-116">使用 **Type** 属性确定 [Member](type-property-ado-md.md) 的性质。</span><span class="sxs-lookup"><span data-stu-id="50afd-116">Determine the nature of the **Member** with the [Type](type-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="50afd-117">使用 **LevelDepth** 和 **LevelName** 属性获取有关 [Member](leveldepth-property-ado-md.md) 的 [Level](levelname-property-ado-md.md) 的信息。</span><span class="sxs-lookup"><span data-stu-id="50afd-117">Obtain information about the **Level** of the **Member** with the [LevelDepth](leveldepth-property-ado-md.md) and [LevelName](levelname-property-ado-md.md) properties.</span></span>

  - <span data-ttu-id="50afd-118">使用 **Parent** 和 [Children](hierarchy-object-ado-md.md) 属性获取 [Hierarchy](parent-property-ado-md.md) 中的相关 [Members](children-property-ado-md.md) 。</span><span class="sxs-lookup"><span data-stu-id="50afd-118">Obtain related **Members** in a [Hierarchy](hierarchy-object-ado-md.md) with the [Parent](parent-property-ado-md.md) and [Children](children-property-ado-md.md) properties.</span></span>

  - <span data-ttu-id="50afd-119">使用 **ChildCount** 属性对 [Member](childcount-property-ado-md.md) 的子级进行计数。</span><span class="sxs-lookup"><span data-stu-id="50afd-119">Count the children of a **Member** with the [ChildCount](childcount-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="50afd-120">使用标准 ADO [Properties](properties-collection-ado.md) 集合获取有关 **Level** 对象的附加信息。</span><span class="sxs-lookup"><span data-stu-id="50afd-120">Use the standard ADO [Properties](properties-collection-ado.md) collection to obtain additional information about the **Level** object.</span></span>

<span data-ttu-id="50afd-121">使用沿 **Axis** 的 **Position** 的 [Member](axis-object-ado-md.md) 的集合和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="50afd-121">With the collections and properties of a **Member** of a **Position** along an [Axis](axis-object-ado-md.md), you can do the following:</span></span>

  - <span data-ttu-id="50afd-122">使用 **Name** 和 [UniqueName](name-property-ado-md.md) 属性标识 [Member](uniquename-property-ado-md.md) 。</span><span class="sxs-lookup"><span data-stu-id="50afd-122">Identify the **Member** with the [Name](name-property-ado-md.md) and [UniqueName](uniquename-property-ado-md.md) properties.</span></span>

  - <span data-ttu-id="50afd-123">使用 **Caption** 属性返回在显示 [Member](caption-property-ado-md.md) 时使用的字符串。</span><span class="sxs-lookup"><span data-stu-id="50afd-123">Return a string to use when displaying the **Member** with the [Caption](caption-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="50afd-124">使用 **Description** 属性返回描述度量或公式 [Member](description-property-ado-md.md) 的有意义的字符串。</span><span class="sxs-lookup"><span data-stu-id="50afd-124">Return a meaningful string that describes a measure or formula **Member** with the [Description](description-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="50afd-125">使用 **LevelDepth** 和 **LevelName** 属性获取有关 [Member](leveldepth-property-ado-md.md) 的 [Level](levelname-property-ado-md.md) 的信息。</span><span class="sxs-lookup"><span data-stu-id="50afd-125">Obtain information about the **Level** of the **Member** with the [LevelDepth](leveldepth-property-ado-md.md) and [LevelName](levelname-property-ado-md.md) properties.</span></span>

  - <span data-ttu-id="50afd-126">使用 **ChildCount** 属性对 [Member](childcount-property-ado-md.md) 的子级进行计数。</span><span class="sxs-lookup"><span data-stu-id="50afd-126">Count the children of a **Member** with the [ChildCount](childcount-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="50afd-127">使用 [DrilledDown](drilleddown-property-ado-md.md) 属性确定此 **Member** 在 **Axis** 上是否至少有一个直接子级。</span><span class="sxs-lookup"><span data-stu-id="50afd-127">Use the [DrilledDown](drilleddown-property-ado-md.md) property to determine whether there is at least one child on the **Axis** immediately following this **Member**.</span></span>

  - <span data-ttu-id="50afd-128">使用 [ParentSameAsPrev](parentsameasprev-property-ado-md.md) 属性确定此 **Member** 的父级是否与直接父级 **Member** 的父级相同。</span><span class="sxs-lookup"><span data-stu-id="50afd-128">Use the [ParentSameAsPrev](parentsameasprev-property-ado-md.md) property to determine whether the parent of this **Member** is the same as the parent of the immediately preceding **Member**.</span></span>

  - <span data-ttu-id="50afd-129">使用标准 ADO [Properties](properties-collection-ado.md) 集合获取有关 **Level** 对象的附加信息。</span><span class="sxs-lookup"><span data-stu-id="50afd-129">Use the standard ADO [Properties](properties-collection-ado.md) collection to obtain additional information about the **Level** object.</span></span>

<span data-ttu-id="50afd-p103">**Properties** 集合包含提供程序提供的属性。下表列出了可能可用的属性。实际的属性列表可能有所不同，具体取决于提供程序的实现。有关可用属性的更完整列表，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="50afd-p103">The **Properties** collection contains provider-supplied properties. The following table lists properties that might be available. The actual property list may differ depending upon the implementation of the provider. See the documentation for your provider for a more complete list of available properties.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="50afd-134">Name</span><span class="sxs-lookup"><span data-stu-id="50afd-134">Name</span></span></p></th>
<th><p><span data-ttu-id="50afd-135">说明</span><span class="sxs-lookup"><span data-stu-id="50afd-135">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50afd-136">CatalogName</span><span class="sxs-lookup"><span data-stu-id="50afd-136">CatalogName</span></span></p></td>
<td><p><span data-ttu-id="50afd-137">此多维数据集所属的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="50afd-137">The name of the catalog to which this cube belongs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50afd-138">ChildrenCardinality</span><span class="sxs-lookup"><span data-stu-id="50afd-138">ChildrenCardinality</span></span></p></td>
<td><p><span data-ttu-id="50afd-139">成员具有的子级数目。</span><span class="sxs-lookup"><span data-stu-id="50afd-139">The number of children that the member has.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50afd-140">多维数据集名称</span><span class="sxs-lookup"><span data-stu-id="50afd-140">CubeName</span></span></p></td>
<td><p><span data-ttu-id="50afd-141">多维数据集的名称。</span><span class="sxs-lookup"><span data-stu-id="50afd-141">The name of the cube.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50afd-142">Description</span><span class="sxs-lookup"><span data-stu-id="50afd-142">Description</span></span></p></td>
<td><p><span data-ttu-id="50afd-143">成员的有意义的说明。</span><span class="sxs-lookup"><span data-stu-id="50afd-143">A meaningful description of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50afd-144">DimensionUniqueName</span><span class="sxs-lookup"><span data-stu-id="50afd-144">DimensionUniqueName</span></span></p></td>
<td><p><span data-ttu-id="50afd-145"><a href="dimension-object-ado-md.md">维度</a>的明确名称。</span><span class="sxs-lookup"><span data-stu-id="50afd-145">The unambiguous name of the <a href="dimension-object-ado-md.md">dimension</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50afd-146">HierarchyUniqueName</span><span class="sxs-lookup"><span data-stu-id="50afd-146">HierarchyUniqueName</span></span></p></td>
<td><p><span data-ttu-id="50afd-147">层次结构的明确名称。</span><span class="sxs-lookup"><span data-stu-id="50afd-147">The unambiguous name of the hierarchy.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50afd-148">LevelNumber</span><span class="sxs-lookup"><span data-stu-id="50afd-148">LevelNumber</span></span></p></td>
<td><p><span data-ttu-id="50afd-149">层次结构的级别和根之间的距离。</span><span class="sxs-lookup"><span data-stu-id="50afd-149">The distance between the level and the root of the hierarchy.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50afd-150">LevelUniqueName</span><span class="sxs-lookup"><span data-stu-id="50afd-150">LevelUniqueName</span></span></p></td>
<td><p><span data-ttu-id="50afd-151">级别的明确名称。</span><span class="sxs-lookup"><span data-stu-id="50afd-151">The unambiguous name of the level.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50afd-152">MemberCaption</span><span class="sxs-lookup"><span data-stu-id="50afd-152">MemberCaption</span></span></p></td>
<td><p><span data-ttu-id="50afd-153">与成员关联的标签或标题。</span><span class="sxs-lookup"><span data-stu-id="50afd-153">A label or caption associated with the member.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50afd-154">MemberGUID</span><span class="sxs-lookup"><span data-stu-id="50afd-154">MemberGUID</span></span></p></td>
<td><p><span data-ttu-id="50afd-155">成员的 GUID。</span><span class="sxs-lookup"><span data-stu-id="50afd-155">The GUID of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50afd-156">成员名称</span><span class="sxs-lookup"><span data-stu-id="50afd-156">MemberName</span></span></p></td>
<td><p><span data-ttu-id="50afd-157">成员的名称。</span><span class="sxs-lookup"><span data-stu-id="50afd-157">The name of the member.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50afd-158">MemberOrdinal</span><span class="sxs-lookup"><span data-stu-id="50afd-158">MemberOrdinal</span></span></p></td>
<td><p><span data-ttu-id="50afd-159">成员的序号。</span><span class="sxs-lookup"><span data-stu-id="50afd-159">The ordinal number of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50afd-160">MemberType</span><span class="sxs-lookup"><span data-stu-id="50afd-160">MemberType</span></span></p></td>
<td><p><span data-ttu-id="50afd-161">成员的类型。</span><span class="sxs-lookup"><span data-stu-id="50afd-161">The type of the member.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50afd-162">成员的唯一名称</span><span class="sxs-lookup"><span data-stu-id="50afd-162">MemberUniqueName</span></span></p></td>
<td><p><span data-ttu-id="50afd-163">成员的明确名称。</span><span class="sxs-lookup"><span data-stu-id="50afd-163">The unambiguous name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50afd-164">ParentCount</span><span class="sxs-lookup"><span data-stu-id="50afd-164">ParentCount</span></span></p></td>
<td><p><span data-ttu-id="50afd-165">此成员具有的父级数目。</span><span class="sxs-lookup"><span data-stu-id="50afd-165">The count of the number of parents that this member has.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50afd-166">ParentLevel</span><span class="sxs-lookup"><span data-stu-id="50afd-166">ParentLevel</span></span></p></td>
<td><p><span data-ttu-id="50afd-167">成员父级的级别号。</span><span class="sxs-lookup"><span data-stu-id="50afd-167">The level number of the member's parent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50afd-168">ParentUniqueName</span><span class="sxs-lookup"><span data-stu-id="50afd-168">ParentUniqueName</span></span></p></td>
<td><p><span data-ttu-id="50afd-169">成员父级的明确名称。</span><span class="sxs-lookup"><span data-stu-id="50afd-169">The unambiguous name of the member's parent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50afd-170">SchemaName</span><span class="sxs-lookup"><span data-stu-id="50afd-170">SchemaName</span></span></p></td>
<td><p><span data-ttu-id="50afd-171">此多维数据集所属的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="50afd-171">The name of the schema to which this cube belongs.</span></span></p></td>
</tr>
</tbody>
</table>

