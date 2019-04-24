---
title: RefreshConflict 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 373983f7-fc0c-95f6-7665-7ed47de82e5e
description: 指示数据记录集中的行链接到的形状在数据记录集刷新后发生冲突。
ms.openlocfilehash: 2da6f98cf7b047564331aaf5a4167e392927a155
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360135"
---
# <a name="refreshconflict-element-datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="fb6ce-103">RefreshConflict 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="fb6ce-103">RefreshConflict element (DataRecordSet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="fb6ce-104">指示数据记录集中的行链接到的形状在数据记录集刷新后发生冲突。</span><span class="sxs-lookup"><span data-stu-id="fb6ce-104">Indicates a row in the data recordset linked to a shape that is in conflict after the data recordset is refreshed.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="fb6ce-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="fb6ce-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fb6ce-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="fb6ce-106">**Element type**</span></span> <br/> |[<span data-ttu-id="fb6ce-107">RefreshConflict_Type</span><span class="sxs-lookup"><span data-stu-id="fb6ce-107">RefreshConflict_Type</span></span>](refreshconflict_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="fb6ce-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="fb6ce-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="fb6ce-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="fb6ce-109">**Schema file**</span></span> <br/> |<span data-ttu-id="fb6ce-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="fb6ce-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="fb6ce-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="fb6ce-111">**Document parts**</span></span> <br/> |<span data-ttu-id="fb6ce-112">记录集 .xml</span><span class="sxs-lookup"><span data-stu-id="fb6ce-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="fb6ce-113">定义</span><span class="sxs-lookup"><span data-stu-id="fb6ce-113">Definition</span></span>

```XML
< xs:element name="RefreshConflict" type="RefreshConflict_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="fb6ce-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="fb6ce-114">Elements and attributes</span></span>

<span data-ttu-id="fb6ce-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="fb6ce-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="fb6ce-116">父元素</span><span class="sxs-lookup"><span data-stu-id="fb6ce-116">Parent elements</span></span>

|<span data-ttu-id="fb6ce-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="fb6ce-117">**Element**</span></span>|<span data-ttu-id="fb6ce-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="fb6ce-118">**Type**</span></span>|<span data-ttu-id="fb6ce-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="fb6ce-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fb6ce-120">DataRecordSet</span><span class="sxs-lookup"><span data-stu-id="fb6ce-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fb6ce-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="fb6ce-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fb6ce-122">在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。</span><span class="sxs-lookup"><span data-stu-id="fb6ce-122">Stores, formats, refreshes, and exposes data queried from a database in Microsoft Visio.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="fb6ce-123">子元素</span><span class="sxs-lookup"><span data-stu-id="fb6ce-123">Child elements</span></span>

<span data-ttu-id="fb6ce-124">无。</span><span class="sxs-lookup"><span data-stu-id="fb6ce-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="fb6ce-125">属性</span><span class="sxs-lookup"><span data-stu-id="fb6ce-125">Attributes</span></span>

|<span data-ttu-id="fb6ce-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="fb6ce-126">**Attribute**</span></span>|<span data-ttu-id="fb6ce-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="fb6ce-127">**Type**</span></span>|<span data-ttu-id="fb6ce-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="fb6ce-128">**Required**</span></span>|<span data-ttu-id="fb6ce-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="fb6ce-129">**Description**</span></span>|<span data-ttu-id="fb6ce-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="fb6ce-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fb6ce-131">PageID</span><span class="sxs-lookup"><span data-stu-id="fb6ce-131">PageID</span></span>  <br/> |<span data-ttu-id="fb6ce-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="fb6ce-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="fb6ce-133">必需</span><span class="sxs-lookup"><span data-stu-id="fb6ce-133">required</span></span>  <br/> |<span data-ttu-id="fb6ce-134">冲突中涉及的形状的页面 ID。</span><span class="sxs-lookup"><span data-stu-id="fb6ce-134">Page ID of the shape involved in the conflict.</span></span>  <br/> |<span data-ttu-id="fb6ce-135">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fb6ce-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="fb6ce-136">RowID</span><span class="sxs-lookup"><span data-stu-id="fb6ce-136">RowID</span></span>  <br/> |<span data-ttu-id="fb6ce-137">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="fb6ce-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="fb6ce-138">必需</span><span class="sxs-lookup"><span data-stu-id="fb6ce-138">required</span></span>  <br/> |<span data-ttu-id="fb6ce-139">现在, 行的原始行 ID 在刷新数据后发生冲突。</span><span class="sxs-lookup"><span data-stu-id="fb6ce-139">The original row ID of the row now in conflict after data was refreshed .</span></span>  <br/> |<span data-ttu-id="fb6ce-140">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fb6ce-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="fb6ce-141">ShapeID</span><span class="sxs-lookup"><span data-stu-id="fb6ce-141">ShapeID</span></span>  <br/> |<span data-ttu-id="fb6ce-142">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="fb6ce-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="fb6ce-143">必需</span><span class="sxs-lookup"><span data-stu-id="fb6ce-143">required</span></span>  <br/> |<span data-ttu-id="fb6ce-144">冲突中涉及的形状的形状 ID。</span><span class="sxs-lookup"><span data-stu-id="fb6ce-144">Shape ID of the shape involved in the conflict.</span></span>  <br/> |<span data-ttu-id="fb6ce-145">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fb6ce-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

