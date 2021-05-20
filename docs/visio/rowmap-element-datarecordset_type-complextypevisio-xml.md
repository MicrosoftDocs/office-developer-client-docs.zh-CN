---
title: 'RowMap 元素 (DataRecordSet_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f90dc76b-7f0b-dead-38c0-97062a7b76a6
description: 地图数据记录集行与形状。
ms.openlocfilehash: 178ceb06d64bfc9ef50f75dd22f8bd94f09f5c33
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540768"
---
# <a name="rowmap-element-datarecordset_type-complextype-visio-xml"></a><span data-ttu-id="4a958-103">RowMap 元素 (DataRecordSet_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="4a958-103">RowMap element (DataRecordSet_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="4a958-104">地图数据记录集行与形状。</span><span class="sxs-lookup"><span data-stu-id="4a958-104">Maps a data-recordset row to a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="4a958-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="4a958-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4a958-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="4a958-106">**Element type**</span></span> <br/> |[<span data-ttu-id="4a958-107">RowMap_Type</span><span class="sxs-lookup"><span data-stu-id="4a958-107">RowMap_Type</span></span>](rowmap_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="4a958-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4a958-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="4a958-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4a958-109">**Schema file**</span></span> <br/> |<span data-ttu-id="4a958-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="4a958-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="4a958-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="4a958-111">**Document parts**</span></span> <br/> |<span data-ttu-id="4a958-112">recordsets.xml</span><span class="sxs-lookup"><span data-stu-id="4a958-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4a958-113">定义</span><span class="sxs-lookup"><span data-stu-id="4a958-113">Definition</span></span>

```XML
< xs:element name="RowMap" type="RowMap_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4a958-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4a958-114">Elements and attributes</span></span>

<span data-ttu-id="4a958-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4a958-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="4a958-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4a958-116">Parent elements</span></span>

****

|<span data-ttu-id="4a958-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="4a958-117">**Element**</span></span>|<span data-ttu-id="4a958-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4a958-118">**Type**</span></span>|<span data-ttu-id="4a958-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4a958-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4a958-120">DataRecordSet</span><span class="sxs-lookup"><span data-stu-id="4a958-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4a958-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="4a958-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4a958-122">在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。</span><span class="sxs-lookup"><span data-stu-id="4a958-122">Stores, formats, refreshes, and exposes data queried from a database in Microsoft Visio.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="4a958-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4a958-123">Child elements</span></span>

<span data-ttu-id="4a958-124">无。</span><span class="sxs-lookup"><span data-stu-id="4a958-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="4a958-125">属性</span><span class="sxs-lookup"><span data-stu-id="4a958-125">Attributes</span></span>

|<span data-ttu-id="4a958-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="4a958-126">**Attribute**</span></span>|<span data-ttu-id="4a958-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="4a958-127">**Type**</span></span>|<span data-ttu-id="4a958-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="4a958-128">**Required**</span></span>|<span data-ttu-id="4a958-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="4a958-129">**Description**</span></span>|<span data-ttu-id="4a958-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4a958-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4a958-131">PageID</span><span class="sxs-lookup"><span data-stu-id="4a958-131">PageID</span></span>  <br/> |<span data-ttu-id="4a958-132">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4a958-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4a958-133">必需</span><span class="sxs-lookup"><span data-stu-id="4a958-133">required</span></span>  <br/> |<span data-ttu-id="4a958-134">链接到由 RowID 标识的数据记录集行中数据的形状的页面 **ID。**</span><span class="sxs-lookup"><span data-stu-id="4a958-134">Page ID of the shape linked to data in the data-recordset row identified by **RowID**.</span></span>  <br/> |<span data-ttu-id="4a958-135">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4a958-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4a958-136">RowID</span><span class="sxs-lookup"><span data-stu-id="4a958-136">RowID</span></span>  <br/> |<span data-ttu-id="4a958-137">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4a958-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4a958-138">必需</span><span class="sxs-lookup"><span data-stu-id="4a958-138">required</span></span>  <br/> |<span data-ttu-id="4a958-139">行的行 ID，在数据记录集内是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4a958-139">Row ID of the row, unique within the data recordset.</span></span>  <br/> |<span data-ttu-id="4a958-140">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4a958-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4a958-141">ShapeID</span><span class="sxs-lookup"><span data-stu-id="4a958-141">ShapeID</span></span>  <br/> |<span data-ttu-id="4a958-142">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4a958-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4a958-143">必需</span><span class="sxs-lookup"><span data-stu-id="4a958-143">required</span></span>  <br/> |<span data-ttu-id="4a958-144">链接到由 RowID 标识的数据记录集行中数据的形状 **的形状 ID。**</span><span class="sxs-lookup"><span data-stu-id="4a958-144">Shape ID of the shape linked to data in the data-recordset row identified by **RowID**.</span></span>  <br/> |<span data-ttu-id="4a958-145">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4a958-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

