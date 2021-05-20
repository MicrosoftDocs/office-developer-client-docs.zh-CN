---
title: 'RefreshConflict 元素 (DataRecordSet_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 373983f7-fc0c-95f6-7665-7ed47de82e5e
description: 指示数据记录集内链接到在刷新数据记录集后存在冲突的形状的行。
ms.openlocfilehash: f966ca4a9f23de7a96273615b2404041d1045652
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542833"
---
# <a name="refreshconflict-element-datarecordset_type-complextype-visio-xml"></a><span data-ttu-id="26ebc-103">RefreshConflict 元素 (DataRecordSet_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="26ebc-103">RefreshConflict element (DataRecordSet_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="26ebc-104">指示数据记录集内链接到在刷新数据记录集后存在冲突的形状的行。</span><span class="sxs-lookup"><span data-stu-id="26ebc-104">Indicates a row in the data recordset linked to a shape that is in conflict after the data recordset is refreshed.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="26ebc-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="26ebc-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="26ebc-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="26ebc-106">**Element type**</span></span> <br/> |[<span data-ttu-id="26ebc-107">RefreshConflict_Type</span><span class="sxs-lookup"><span data-stu-id="26ebc-107">RefreshConflict_Type</span></span>](refreshconflict_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="26ebc-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="26ebc-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="26ebc-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="26ebc-109">**Schema file**</span></span> <br/> |<span data-ttu-id="26ebc-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="26ebc-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="26ebc-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="26ebc-111">**Document parts**</span></span> <br/> |<span data-ttu-id="26ebc-112">recordsets.xml</span><span class="sxs-lookup"><span data-stu-id="26ebc-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="26ebc-113">定义</span><span class="sxs-lookup"><span data-stu-id="26ebc-113">Definition</span></span>

```XML
< xs:element name="RefreshConflict" type="RefreshConflict_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="26ebc-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="26ebc-114">Elements and attributes</span></span>

<span data-ttu-id="26ebc-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="26ebc-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="26ebc-116">父元素</span><span class="sxs-lookup"><span data-stu-id="26ebc-116">Parent elements</span></span>

|<span data-ttu-id="26ebc-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="26ebc-117">**Element**</span></span>|<span data-ttu-id="26ebc-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="26ebc-118">**Type**</span></span>|<span data-ttu-id="26ebc-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="26ebc-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="26ebc-120">DataRecordSet</span><span class="sxs-lookup"><span data-stu-id="26ebc-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="26ebc-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="26ebc-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="26ebc-122">在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。</span><span class="sxs-lookup"><span data-stu-id="26ebc-122">Stores, formats, refreshes, and exposes data queried from a database in Microsoft Visio.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="26ebc-123">子元素</span><span class="sxs-lookup"><span data-stu-id="26ebc-123">Child elements</span></span>

<span data-ttu-id="26ebc-124">无。</span><span class="sxs-lookup"><span data-stu-id="26ebc-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="26ebc-125">属性</span><span class="sxs-lookup"><span data-stu-id="26ebc-125">Attributes</span></span>

|<span data-ttu-id="26ebc-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="26ebc-126">**Attribute**</span></span>|<span data-ttu-id="26ebc-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="26ebc-127">**Type**</span></span>|<span data-ttu-id="26ebc-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="26ebc-128">**Required**</span></span>|<span data-ttu-id="26ebc-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="26ebc-129">**Description**</span></span>|<span data-ttu-id="26ebc-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="26ebc-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="26ebc-131">PageID</span><span class="sxs-lookup"><span data-stu-id="26ebc-131">PageID</span></span>  <br/> |<span data-ttu-id="26ebc-132">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="26ebc-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="26ebc-133">必需</span><span class="sxs-lookup"><span data-stu-id="26ebc-133">required</span></span>  <br/> |<span data-ttu-id="26ebc-134">冲突所涉及的形状的页面 ID。</span><span class="sxs-lookup"><span data-stu-id="26ebc-134">Page ID of the shape involved in the conflict.</span></span>  <br/> |<span data-ttu-id="26ebc-135">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="26ebc-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="26ebc-136">RowID</span><span class="sxs-lookup"><span data-stu-id="26ebc-136">RowID</span></span>  <br/> |<span data-ttu-id="26ebc-137">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="26ebc-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="26ebc-138">必需</span><span class="sxs-lookup"><span data-stu-id="26ebc-138">required</span></span>  <br/> |<span data-ttu-id="26ebc-139">数据刷新后，行的原始行 ID 现在发生冲突。</span><span class="sxs-lookup"><span data-stu-id="26ebc-139">The original row ID of the row now in conflict after data was refreshed .</span></span>  <br/> |<span data-ttu-id="26ebc-140">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="26ebc-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="26ebc-141">ShapeID</span><span class="sxs-lookup"><span data-stu-id="26ebc-141">ShapeID</span></span>  <br/> |<span data-ttu-id="26ebc-142">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="26ebc-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="26ebc-143">必需</span><span class="sxs-lookup"><span data-stu-id="26ebc-143">required</span></span>  <br/> |<span data-ttu-id="26ebc-144">冲突所涉及的形状的形状 ID。</span><span class="sxs-lookup"><span data-stu-id="26ebc-144">Shape ID of the shape involved in the conflict.</span></span>  <br/> |<span data-ttu-id="26ebc-145">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="26ebc-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

