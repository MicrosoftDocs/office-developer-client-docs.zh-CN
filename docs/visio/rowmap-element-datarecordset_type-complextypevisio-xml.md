---
title: RowMap 元素 （DataRecordSet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f90dc76b-7f0b-dead-38c0-97062a7b76a6
description: 映射到形状的数据记录集行。
ms.openlocfilehash: aefae8c625f35feacd6d0fdf04f128c423db299b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781190"
---
# <a name="rowmap-element-datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="afd64-103">RowMap 元素 （DataRecordSet_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="afd64-103">RowMap element (DataRecordSet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="afd64-104">映射到形状的数据记录集行。</span><span class="sxs-lookup"><span data-stu-id="afd64-104">Maps a data-recordset row to a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="afd64-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="afd64-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="afd64-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="afd64-106">**Element type**</span></span> <br/> |[<span data-ttu-id="afd64-107">RowMap_Type</span><span class="sxs-lookup"><span data-stu-id="afd64-107">RowMap_Type</span></span>](rowmap_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="afd64-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="afd64-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="afd64-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="afd64-109">**Schema file**</span></span> <br/> |<span data-ttu-id="afd64-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="afd64-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="afd64-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="afd64-111">**Document parts**</span></span> <br/> |<span data-ttu-id="afd64-112">recordsets.xml</span><span class="sxs-lookup"><span data-stu-id="afd64-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="afd64-113">定义</span><span class="sxs-lookup"><span data-stu-id="afd64-113">Definition</span></span>

```XML
< xs:element name="RowMap" type="RowMap_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="afd64-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="afd64-114">Elements and attributes</span></span>

<span data-ttu-id="afd64-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="afd64-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="afd64-116">父元素</span><span class="sxs-lookup"><span data-stu-id="afd64-116">Parent elements</span></span>

****

|<span data-ttu-id="afd64-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="afd64-117">**Element**</span></span>|<span data-ttu-id="afd64-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="afd64-118">**Type**</span></span>|<span data-ttu-id="afd64-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="afd64-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="afd64-120">数据记录集</span><span class="sxs-lookup"><span data-stu-id="afd64-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="afd64-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="afd64-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="afd64-122">在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。</span><span class="sxs-lookup"><span data-stu-id="afd64-122">Stores, formats, refreshes, and exposes data queried from a database in Microsoft Visio.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="afd64-123">子元素</span><span class="sxs-lookup"><span data-stu-id="afd64-123">Child elements</span></span>

<span data-ttu-id="afd64-124">无。</span><span class="sxs-lookup"><span data-stu-id="afd64-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="afd64-125">属性</span><span class="sxs-lookup"><span data-stu-id="afd64-125">Attributes</span></span>

|<span data-ttu-id="afd64-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="afd64-126">**Attribute**</span></span>|<span data-ttu-id="afd64-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="afd64-127">**Type**</span></span>|<span data-ttu-id="afd64-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="afd64-128">**Required**</span></span>|<span data-ttu-id="afd64-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="afd64-129">**Description**</span></span>|<span data-ttu-id="afd64-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="afd64-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="afd64-131">PageID</span><span class="sxs-lookup"><span data-stu-id="afd64-131">PageID</span></span>  <br/> |<span data-ttu-id="afd64-132">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="afd64-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="afd64-133">必需</span><span class="sxs-lookup"><span data-stu-id="afd64-133">required</span></span>  <br/> |<span data-ttu-id="afd64-134">页面的链接到数据记录集行由**RowID**标识中数据的形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="afd64-134">Page ID of the shape linked to data in the data-recordset row identified by **RowID**.</span></span>  <br/> |<span data-ttu-id="afd64-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="afd64-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="afd64-136">RowID</span><span class="sxs-lookup"><span data-stu-id="afd64-136">RowID</span></span>  <br/> |<span data-ttu-id="afd64-137">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="afd64-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="afd64-138">必需</span><span class="sxs-lookup"><span data-stu-id="afd64-138">required</span></span>  <br/> |<span data-ttu-id="afd64-139">唯一的数据记录集内的行的行 ID。</span><span class="sxs-lookup"><span data-stu-id="afd64-139">Row ID of the row, unique within the data recordset.</span></span>  <br/> |<span data-ttu-id="afd64-140">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="afd64-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="afd64-141">ShapeID</span><span class="sxs-lookup"><span data-stu-id="afd64-141">ShapeID</span></span>  <br/> |<span data-ttu-id="afd64-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="afd64-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="afd64-143">必需</span><span class="sxs-lookup"><span data-stu-id="afd64-143">required</span></span>  <br/> |<span data-ttu-id="afd64-144">形状链接到数据记录集行由**RowID**标识中数据的形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="afd64-144">Shape ID of the shape linked to data in the data-recordset row identified by **RowID**.</span></span>  <br/> |<span data-ttu-id="afd64-145">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="afd64-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

