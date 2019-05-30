---
title: RowMap 元素 (DataRecordSet_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f90dc76b-7f0b-dead-38c0-97062a7b76a6
description: 将数据记录集行映射到形状。
ms.openlocfilehash: 178ceb06d64bfc9ef50f75dd22f8bd94f09f5c33
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540768"
---
# <a name="rowmap-element-datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="97726-103">RowMap 元素 (DataRecordSet_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="97726-103">RowMap element (DataRecordSet_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="97726-104">将数据记录集行映射到形状。</span><span class="sxs-lookup"><span data-stu-id="97726-104">Maps a data-recordset row to a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="97726-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="97726-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="97726-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="97726-106">**Element type**</span></span> <br/> |[<span data-ttu-id="97726-107">RowMap_Type</span><span class="sxs-lookup"><span data-stu-id="97726-107">RowMap_Type</span></span>](rowmap_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="97726-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="97726-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="97726-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="97726-109">**Schema file**</span></span> <br/> |<span data-ttu-id="97726-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="97726-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="97726-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="97726-111">**Document parts**</span></span> <br/> |<span data-ttu-id="97726-112">记录集 .xml</span><span class="sxs-lookup"><span data-stu-id="97726-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="97726-113">定义</span><span class="sxs-lookup"><span data-stu-id="97726-113">Definition</span></span>

```XML
< xs:element name="RowMap" type="RowMap_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="97726-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="97726-114">Elements and attributes</span></span>

<span data-ttu-id="97726-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="97726-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="97726-116">父元素</span><span class="sxs-lookup"><span data-stu-id="97726-116">Parent elements</span></span>

****

|<span data-ttu-id="97726-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="97726-117">**Element**</span></span>|<span data-ttu-id="97726-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="97726-118">**Type**</span></span>|<span data-ttu-id="97726-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="97726-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="97726-120">DataRecordSet</span><span class="sxs-lookup"><span data-stu-id="97726-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="97726-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="97726-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="97726-122">在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。</span><span class="sxs-lookup"><span data-stu-id="97726-122">Stores, formats, refreshes, and exposes data queried from a database in Microsoft Visio.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="97726-123">子元素</span><span class="sxs-lookup"><span data-stu-id="97726-123">Child elements</span></span>

<span data-ttu-id="97726-124">无。</span><span class="sxs-lookup"><span data-stu-id="97726-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="97726-125">属性</span><span class="sxs-lookup"><span data-stu-id="97726-125">Attributes</span></span>

|<span data-ttu-id="97726-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="97726-126">**Attribute**</span></span>|<span data-ttu-id="97726-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="97726-127">**Type**</span></span>|<span data-ttu-id="97726-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="97726-128">**Required**</span></span>|<span data-ttu-id="97726-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="97726-129">**Description**</span></span>|<span data-ttu-id="97726-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="97726-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="97726-131">PageID</span><span class="sxs-lookup"><span data-stu-id="97726-131">PageID</span></span>  <br/> |<span data-ttu-id="97726-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="97726-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="97726-133">必需</span><span class="sxs-lookup"><span data-stu-id="97726-133">required</span></span>  <br/> |<span data-ttu-id="97726-134">链接到由**RowID**标识的数据记录集行中的数据的形状的页面 ID。</span><span class="sxs-lookup"><span data-stu-id="97726-134">Page ID of the shape linked to data in the data-recordset row identified by **RowID**.</span></span>  <br/> |<span data-ttu-id="97726-135">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="97726-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="97726-136">RowID</span><span class="sxs-lookup"><span data-stu-id="97726-136">RowID</span></span>  <br/> |<span data-ttu-id="97726-137">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="97726-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="97726-138">必需</span><span class="sxs-lookup"><span data-stu-id="97726-138">required</span></span>  <br/> |<span data-ttu-id="97726-139">行的行 ID, 在数据记录集中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="97726-139">Row ID of the row, unique within the data recordset.</span></span>  <br/> |<span data-ttu-id="97726-140">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="97726-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="97726-141">ShapeID</span><span class="sxs-lookup"><span data-stu-id="97726-141">ShapeID</span></span>  <br/> |<span data-ttu-id="97726-142">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="97726-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="97726-143">必需</span><span class="sxs-lookup"><span data-stu-id="97726-143">required</span></span>  <br/> |<span data-ttu-id="97726-144">链接到由**RowID**标识的数据记录集行中的数据的形状的形状 ID。</span><span class="sxs-lookup"><span data-stu-id="97726-144">Shape ID of the shape linked to data in the data-recordset row identified by **RowID**.</span></span>  <br/> |<span data-ttu-id="97726-145">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="97726-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

