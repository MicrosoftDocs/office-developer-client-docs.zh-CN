---
title: RowMap 元素 （DataRecordSet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f90dc76b-7f0b-dead-38c0-97062a7b76a6
description: 映射到形状的数据记录集行。
ms.openlocfilehash: 2dffa49d66e8e447b4e31d771179c74eecad21da
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385310"
---
# <a name="rowmap-element-datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="92021-103">RowMap 元素 （DataRecordSet_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="92021-103">RowMap element (DataRecordSet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="92021-104">映射到形状的数据记录集行。</span><span class="sxs-lookup"><span data-stu-id="92021-104">Maps a data-recordset row to a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="92021-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="92021-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="92021-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="92021-106">**Element type**</span></span> <br/> |[<span data-ttu-id="92021-107">RowMap_Type</span><span class="sxs-lookup"><span data-stu-id="92021-107">RowMap_Type</span></span>](rowmap_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="92021-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="92021-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="92021-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="92021-109">**Schema file**</span></span> <br/> |<span data-ttu-id="92021-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="92021-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="92021-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="92021-111">**Document parts**</span></span> <br/> |<span data-ttu-id="92021-112">recordsets.xml</span><span class="sxs-lookup"><span data-stu-id="92021-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="92021-113">定义</span><span class="sxs-lookup"><span data-stu-id="92021-113">Definition</span></span>

```XML
< xs:element name="RowMap" type="RowMap_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="92021-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="92021-114">Elements and attributes</span></span>

<span data-ttu-id="92021-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="92021-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="92021-116">父元素</span><span class="sxs-lookup"><span data-stu-id="92021-116">Parent elements</span></span>

****

|<span data-ttu-id="92021-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="92021-117">**Element**</span></span>|<span data-ttu-id="92021-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="92021-118">**Type**</span></span>|<span data-ttu-id="92021-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="92021-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="92021-120">数据记录集</span><span class="sxs-lookup"><span data-stu-id="92021-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="92021-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="92021-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="92021-122">在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。</span><span class="sxs-lookup"><span data-stu-id="92021-122">Stores, formats, refreshes, and exposes data queried from a database in Microsoft Visio.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="92021-123">子元素</span><span class="sxs-lookup"><span data-stu-id="92021-123">Child elements</span></span>

<span data-ttu-id="92021-124">无。</span><span class="sxs-lookup"><span data-stu-id="92021-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="92021-125">属性</span><span class="sxs-lookup"><span data-stu-id="92021-125">Attributes</span></span>

|<span data-ttu-id="92021-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="92021-126">**Attribute**</span></span>|<span data-ttu-id="92021-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="92021-127">**Type**</span></span>|<span data-ttu-id="92021-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="92021-128">**Required**</span></span>|<span data-ttu-id="92021-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="92021-129">**Description**</span></span>|<span data-ttu-id="92021-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="92021-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="92021-131">PageID</span><span class="sxs-lookup"><span data-stu-id="92021-131">PageID</span></span>  <br/> |<span data-ttu-id="92021-132">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="92021-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="92021-133">必需</span><span class="sxs-lookup"><span data-stu-id="92021-133">required</span></span>  <br/> |<span data-ttu-id="92021-134">页面的链接到数据记录集行由**RowID**标识中数据的形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="92021-134">Page ID of the shape linked to data in the data-recordset row identified by **RowID**.</span></span>  <br/> |<span data-ttu-id="92021-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="92021-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="92021-136">RowID</span><span class="sxs-lookup"><span data-stu-id="92021-136">RowID</span></span>  <br/> |<span data-ttu-id="92021-137">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="92021-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="92021-138">必需</span><span class="sxs-lookup"><span data-stu-id="92021-138">required</span></span>  <br/> |<span data-ttu-id="92021-139">唯一的数据记录集内的行的行 ID。</span><span class="sxs-lookup"><span data-stu-id="92021-139">Row ID of the row, unique within the data recordset.</span></span>  <br/> |<span data-ttu-id="92021-140">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="92021-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="92021-141">ShapeID</span><span class="sxs-lookup"><span data-stu-id="92021-141">ShapeID</span></span>  <br/> |<span data-ttu-id="92021-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="92021-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="92021-143">必需</span><span class="sxs-lookup"><span data-stu-id="92021-143">required</span></span>  <br/> |<span data-ttu-id="92021-144">形状链接到数据记录集行由**RowID**标识中数据的形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="92021-144">Shape ID of the shape linked to data in the data-recordset row identified by **RowID**.</span></span>  <br/> |<span data-ttu-id="92021-145">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="92021-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

