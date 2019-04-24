---
title: RowMap 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f90dc76b-7f0b-dead-38c0-97062a7b76a6
description: 将数据记录集行映射到形状。
ms.openlocfilehash: 2dffa49d66e8e447b4e31d771179c74eecad21da
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332513"
---
# <a name="rowmap-element-datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="21847-103">RowMap 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="21847-103">RowMap element (DataRecordSet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="21847-104">将数据记录集行映射到形状。</span><span class="sxs-lookup"><span data-stu-id="21847-104">Maps a data-recordset row to a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="21847-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="21847-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="21847-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="21847-106">**Element type**</span></span> <br/> |[<span data-ttu-id="21847-107">RowMap_Type</span><span class="sxs-lookup"><span data-stu-id="21847-107">RowMap_Type</span></span>](rowmap_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="21847-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="21847-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="21847-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="21847-109">**Schema file**</span></span> <br/> |<span data-ttu-id="21847-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="21847-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="21847-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="21847-111">**Document parts**</span></span> <br/> |<span data-ttu-id="21847-112">记录集 .xml</span><span class="sxs-lookup"><span data-stu-id="21847-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="21847-113">定义</span><span class="sxs-lookup"><span data-stu-id="21847-113">Definition</span></span>

```XML
< xs:element name="RowMap" type="RowMap_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="21847-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="21847-114">Elements and attributes</span></span>

<span data-ttu-id="21847-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="21847-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="21847-116">父元素</span><span class="sxs-lookup"><span data-stu-id="21847-116">Parent elements</span></span>

****

|<span data-ttu-id="21847-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="21847-117">**Element**</span></span>|<span data-ttu-id="21847-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="21847-118">**Type**</span></span>|<span data-ttu-id="21847-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="21847-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="21847-120">DataRecordSet</span><span class="sxs-lookup"><span data-stu-id="21847-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="21847-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="21847-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="21847-122">在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。</span><span class="sxs-lookup"><span data-stu-id="21847-122">Stores, formats, refreshes, and exposes data queried from a database in Microsoft Visio.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="21847-123">子元素</span><span class="sxs-lookup"><span data-stu-id="21847-123">Child elements</span></span>

<span data-ttu-id="21847-124">无。</span><span class="sxs-lookup"><span data-stu-id="21847-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="21847-125">属性</span><span class="sxs-lookup"><span data-stu-id="21847-125">Attributes</span></span>

|<span data-ttu-id="21847-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="21847-126">**Attribute**</span></span>|<span data-ttu-id="21847-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="21847-127">**Type**</span></span>|<span data-ttu-id="21847-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="21847-128">**Required**</span></span>|<span data-ttu-id="21847-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="21847-129">**Description**</span></span>|<span data-ttu-id="21847-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="21847-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="21847-131">PageID</span><span class="sxs-lookup"><span data-stu-id="21847-131">PageID</span></span>  <br/> |<span data-ttu-id="21847-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="21847-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="21847-133">必需</span><span class="sxs-lookup"><span data-stu-id="21847-133">required</span></span>  <br/> |<span data-ttu-id="21847-134">链接到由**RowID**标识的数据记录集行中的数据的形状的页面 ID。</span><span class="sxs-lookup"><span data-stu-id="21847-134">Page ID of the shape linked to data in the data-recordset row identified by **RowID**.</span></span>  <br/> |<span data-ttu-id="21847-135">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="21847-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="21847-136">RowID</span><span class="sxs-lookup"><span data-stu-id="21847-136">RowID</span></span>  <br/> |<span data-ttu-id="21847-137">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="21847-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="21847-138">必需</span><span class="sxs-lookup"><span data-stu-id="21847-138">required</span></span>  <br/> |<span data-ttu-id="21847-139">行的行 ID, 在数据记录集中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="21847-139">Row ID of the row, unique within the data recordset.</span></span>  <br/> |<span data-ttu-id="21847-140">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="21847-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="21847-141">ShapeID</span><span class="sxs-lookup"><span data-stu-id="21847-141">ShapeID</span></span>  <br/> |<span data-ttu-id="21847-142">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="21847-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="21847-143">必需</span><span class="sxs-lookup"><span data-stu-id="21847-143">required</span></span>  <br/> |<span data-ttu-id="21847-144">链接到由**RowID**标识的数据记录集行中的数据的形状的形状 ID。</span><span class="sxs-lookup"><span data-stu-id="21847-144">Shape ID of the shape linked to data in the data-recordset row identified by **RowID**.</span></span>  <br/> |<span data-ttu-id="21847-145">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="21847-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

