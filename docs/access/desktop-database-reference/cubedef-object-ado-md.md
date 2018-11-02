---
title: CubeDef 对象 (ADO MD)
TOCTitle: CubeDef object (ADO MD)
ms:assetid: 199235b7-3d98-f655-27bc-94f66e994e06
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248941(v=office.15)
ms:contentKeyID: 48543502
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9f48b3ea16e45b3bde12ed9f8584c3218f955eba
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922389"
---
# <a name="cubedef-object-ado-md"></a><span data-ttu-id="3f09d-102">CubeDef 对象 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="3f09d-102">CubeDef object (ADO MD)</span></span>


<span data-ttu-id="3f09d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3f09d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3f09d-104">代表多维架构中的多维数据集，包含一组相关的维度。</span><span class="sxs-lookup"><span data-stu-id="3f09d-104">Represents a cube from a multidimensional schema, containing a set of related dimensions.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f09d-105">说明</span><span class="sxs-lookup"><span data-stu-id="3f09d-105">Remarks</span></span>

<span data-ttu-id="3f09d-106">使用 **CubeDef** 对象的集合和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3f09d-106">With the collections and properties of a **CubeDef** object, you can do the following:</span></span>

  - <span data-ttu-id="3f09d-107">使用 **Name** 属性标识 [CubeDef](name-property-ado-md.md) 。</span><span class="sxs-lookup"><span data-stu-id="3f09d-107">Identify a **CubeDef** with the [Name](name-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="3f09d-108">使用 [Description](description-property-ado-md.md) 属性返回描述多维数据集的字符串。</span><span class="sxs-lookup"><span data-stu-id="3f09d-108">Return a string that describes the cube with the [Description](description-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="3f09d-109">使用 [Dimensions](dimensions-collection-ado-md.md) 集合返回构成多维数据集的维。</span><span class="sxs-lookup"><span data-stu-id="3f09d-109">Return the dimensions that make up the cube with the [Dimensions](dimensions-collection-ado-md.md) collection.</span></span>

  - <span data-ttu-id="3f09d-110">使用标准 ADO **Properties** 集合获取有关 [CubeDef](properties-collection-ado.md) 的附加信息。</span><span class="sxs-lookup"><span data-stu-id="3f09d-110">Obtain additional information about the **CubeDef** with the standard ADO [Properties](properties-collection-ado.md) collection.</span></span>

<span data-ttu-id="3f09d-p101">**Properties** 集合包含提供程序提供的属性。下表列出了可能可用的属性。实际的属性列表可能有所不同，具体取决于提供程序的实现。有关可用属性的更完整列表，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="3f09d-p101">The **Properties** collection contains provider-supplied properties. The following table lists properties that might be available. The actual property list may differ depending upon the implementation of the provider. See the documentation for your provider for a more complete list of available properties.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3f09d-115">名称</span><span class="sxs-lookup"><span data-stu-id="3f09d-115">Name</span></span></p></th>
<th><p><span data-ttu-id="3f09d-116">说明</span><span class="sxs-lookup"><span data-stu-id="3f09d-116">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f09d-117">CatalogName</span><span class="sxs-lookup"><span data-stu-id="3f09d-117">CatalogName</span></span></p></td>
<td><p><span data-ttu-id="3f09d-118">此多维数据集所属的目录的名称。</span><span class="sxs-lookup"><span data-stu-id="3f09d-118">The name of the catalog to which this cube belongs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f09d-119">CreatedOn</span><span class="sxs-lookup"><span data-stu-id="3f09d-119">CreatedOn</span></span></p></td>
<td><p><span data-ttu-id="3f09d-120">多维数据集的创建日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3f09d-120">Date and time of cube creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f09d-121">CubeGUID</span><span class="sxs-lookup"><span data-stu-id="3f09d-121">CubeGUID</span></span></p></td>
<td><p><span data-ttu-id="3f09d-122">多维数据集 GUID。</span><span class="sxs-lookup"><span data-stu-id="3f09d-122">Cube GUID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f09d-123">多维数据集名称</span><span class="sxs-lookup"><span data-stu-id="3f09d-123">CubeName</span></span></p></td>
<td><p><span data-ttu-id="3f09d-124">多维数据集的名称。</span><span class="sxs-lookup"><span data-stu-id="3f09d-124">The name of the cube.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f09d-125">CubeType</span><span class="sxs-lookup"><span data-stu-id="3f09d-125">CubeType</span></span></p></td>
<td><p><span data-ttu-id="3f09d-126">多维数据集的类型。</span><span class="sxs-lookup"><span data-stu-id="3f09d-126">The type of the cube.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f09d-127">DataUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="3f09d-127">DataUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="3f09d-128">执行上一次数据更新的用户的用户 ID。</span><span class="sxs-lookup"><span data-stu-id="3f09d-128">User ID of the person doing the last data update.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f09d-129">Description</span><span class="sxs-lookup"><span data-stu-id="3f09d-129">Description</span></span></p></td>
<td><p><span data-ttu-id="3f09d-130">多维数据集的有意义的说明。</span><span class="sxs-lookup"><span data-stu-id="3f09d-130">A meaningful description of the cube.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f09d-131">LastSchemaUpdate</span><span class="sxs-lookup"><span data-stu-id="3f09d-131">LastSchemaUpdate</span></span></p></td>
<td><p><span data-ttu-id="3f09d-132">上次更新架构的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3f09d-132">Date and time of last schema update.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f09d-133">SchemaName</span><span class="sxs-lookup"><span data-stu-id="3f09d-133">SchemaName</span></span></p></td>
<td><p><span data-ttu-id="3f09d-134">此多维数据集所属的架构的名称。</span><span class="sxs-lookup"><span data-stu-id="3f09d-134">The name of the schema to which this cube belongs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f09d-135">SchemaUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="3f09d-135">SchemaUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="3f09d-136">执行上一次架构更新的用户的用户 ID。</span><span class="sxs-lookup"><span data-stu-id="3f09d-136">User ID of the person doing the last schema update.</span></span></p></td>
</tr>
</tbody>
</table>

