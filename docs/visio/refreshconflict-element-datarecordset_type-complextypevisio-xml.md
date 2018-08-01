---
title: RefreshConflict 元素 （DataRecordSet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 373983f7-fc0c-95f6-7665-7ed47de82e5e
description: 指示链接到形状的数据记录集刷新后存在冲突的数据记录集中的行。
ms.openlocfilehash: 0bcfb38c1a9ef84fc8581476fcce13b0de32c308
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781039"
---
# <a name="refreshconflict-element-datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="604b4-103">RefreshConflict 元素 （DataRecordSet_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="604b4-103">RefreshConflict element (DataRecordSet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="604b4-104">指示链接到形状的数据记录集刷新后存在冲突的数据记录集中的行。</span><span class="sxs-lookup"><span data-stu-id="604b4-104">Indicates a row in the data recordset linked to a shape that is in conflict after the data recordset is refreshed.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="604b4-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="604b4-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="604b4-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="604b4-106">**Element type**</span></span> <br/> |[<span data-ttu-id="604b4-107">RefreshConflict_Type</span><span class="sxs-lookup"><span data-stu-id="604b4-107">RefreshConflict_Type</span></span>](refreshconflict_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="604b4-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="604b4-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="604b4-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="604b4-109">**Schema file**</span></span> <br/> |<span data-ttu-id="604b4-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="604b4-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="604b4-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="604b4-111">**Document parts**</span></span> <br/> |<span data-ttu-id="604b4-112">recordsets.xml</span><span class="sxs-lookup"><span data-stu-id="604b4-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="604b4-113">定义</span><span class="sxs-lookup"><span data-stu-id="604b4-113">Definition</span></span>

```XML
< xs:element name="RefreshConflict" type="RefreshConflict_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="604b4-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="604b4-114">Elements and attributes</span></span>

<span data-ttu-id="604b4-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="604b4-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="604b4-116">父元素</span><span class="sxs-lookup"><span data-stu-id="604b4-116">Parent elements</span></span>

|<span data-ttu-id="604b4-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="604b4-117">**Element**</span></span>|<span data-ttu-id="604b4-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="604b4-118">**Type**</span></span>|<span data-ttu-id="604b4-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="604b4-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="604b4-120">数据记录集</span><span class="sxs-lookup"><span data-stu-id="604b4-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="604b4-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="604b4-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="604b4-122">在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。</span><span class="sxs-lookup"><span data-stu-id="604b4-122">Stores, formats, refreshes, and exposes data queried from a database in Microsoft Visio.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="604b4-123">子元素</span><span class="sxs-lookup"><span data-stu-id="604b4-123">Child elements</span></span>

<span data-ttu-id="604b4-124">无。</span><span class="sxs-lookup"><span data-stu-id="604b4-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="604b4-125">属性</span><span class="sxs-lookup"><span data-stu-id="604b4-125">Attributes</span></span>

|<span data-ttu-id="604b4-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="604b4-126">**Attribute**</span></span>|<span data-ttu-id="604b4-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="604b4-127">**Type**</span></span>|<span data-ttu-id="604b4-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="604b4-128">**Required**</span></span>|<span data-ttu-id="604b4-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="604b4-129">**Description**</span></span>|<span data-ttu-id="604b4-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="604b4-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="604b4-131">PageID</span><span class="sxs-lookup"><span data-stu-id="604b4-131">PageID</span></span>  <br/> |<span data-ttu-id="604b4-132">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="604b4-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="604b4-133">必需</span><span class="sxs-lookup"><span data-stu-id="604b4-133">required</span></span>  <br/> |<span data-ttu-id="604b4-134">页面冲突中涉及的形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="604b4-134">Page ID of the shape involved in the conflict.</span></span>  <br/> |<span data-ttu-id="604b4-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="604b4-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="604b4-136">RowID</span><span class="sxs-lookup"><span data-stu-id="604b4-136">RowID</span></span>  <br/> |<span data-ttu-id="604b4-137">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="604b4-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="604b4-138">必需</span><span class="sxs-lookup"><span data-stu-id="604b4-138">required</span></span>  <br/> |<span data-ttu-id="604b4-139">现在中后，刷新数据的冲突的行的原始的行 ID。</span><span class="sxs-lookup"><span data-stu-id="604b4-139">The original row ID of the row now in conflict after data was refreshed .</span></span>  <br/> |<span data-ttu-id="604b4-140">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="604b4-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="604b4-141">ShapeID</span><span class="sxs-lookup"><span data-stu-id="604b4-141">ShapeID</span></span>  <br/> |<span data-ttu-id="604b4-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="604b4-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="604b4-143">必需</span><span class="sxs-lookup"><span data-stu-id="604b4-143">required</span></span>  <br/> |<span data-ttu-id="604b4-144">冲突中涉及的形状的形状 ID。</span><span class="sxs-lookup"><span data-stu-id="604b4-144">Shape ID of the shape involved in the conflict.</span></span>  <br/> |<span data-ttu-id="604b4-145">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="604b4-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

