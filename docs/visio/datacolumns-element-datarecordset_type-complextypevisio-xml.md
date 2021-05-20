---
title: 'DataColumns 元素 (DataRecordSet_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 34e25349-d0fa-b3a0-425b-778184e9f58f
description: 包含数据记录集内的所有 DataColumn 元素。
ms.openlocfilehash: e42354076c5e3e34c118145e7ec7fcdbd4977372
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541195"
---
# <a name="datacolumns-element-datarecordset_type-complextype-visio-xml"></a><span data-ttu-id="e44e1-103">DataColumns 元素 (DataRecordSet_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="e44e1-103">DataColumns element (DataRecordSet_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="e44e1-104">包含数据记录集内的所有 **DataColumn** 元素。</span><span class="sxs-lookup"><span data-stu-id="e44e1-104">Contains all the **DataColumn** elements in a data recordset.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="e44e1-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="e44e1-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e44e1-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="e44e1-106">**Element type**</span></span> <br/> |[<span data-ttu-id="e44e1-107">DataColumns_Type</span><span class="sxs-lookup"><span data-stu-id="e44e1-107">DataColumns_Type</span></span>](datacolumns_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="e44e1-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e44e1-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="e44e1-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e44e1-109">**Schema file**</span></span> <br/> |<span data-ttu-id="e44e1-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="e44e1-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="e44e1-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="e44e1-111">**Document parts**</span></span> <br/> |<span data-ttu-id="e44e1-112">recordsets.xml</span><span class="sxs-lookup"><span data-stu-id="e44e1-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e44e1-113">定义</span><span class="sxs-lookup"><span data-stu-id="e44e1-113">Definition</span></span>

```XML
< xs:element name="DataColumns" type="DataColumns_Type" minOccurs="1" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e44e1-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e44e1-114">Elements and attributes</span></span>

<span data-ttu-id="e44e1-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="e44e1-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="e44e1-116">父元素</span><span class="sxs-lookup"><span data-stu-id="e44e1-116">Parent elements</span></span>

|<span data-ttu-id="e44e1-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="e44e1-117">**Element**</span></span>|<span data-ttu-id="e44e1-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="e44e1-118">**Type**</span></span>|<span data-ttu-id="e44e1-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="e44e1-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e44e1-120">DataRecordSet</span><span class="sxs-lookup"><span data-stu-id="e44e1-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e44e1-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="e44e1-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e44e1-122">在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。</span><span class="sxs-lookup"><span data-stu-id="e44e1-122">Stores, formats, refreshes, and exposes data queried from a database in Microsoft Visio.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="e44e1-123">子元素</span><span class="sxs-lookup"><span data-stu-id="e44e1-123">Child elements</span></span>

|<span data-ttu-id="e44e1-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="e44e1-124">**Element**</span></span>|<span data-ttu-id="e44e1-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="e44e1-125">**Type**</span></span>|<span data-ttu-id="e44e1-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="e44e1-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e44e1-127">DataColumn</span><span class="sxs-lookup"><span data-stu-id="e44e1-127">DataColumn</span></span>](datacolumn-element-datacolumns_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e44e1-128">DataColumn_Type</span><span class="sxs-lookup"><span data-stu-id="e44e1-128">DataColumn_Type</span></span>](datacolumn_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e44e1-129">定义数据列在 Visio 用户界面的"外部数据"窗口中的显示方式，并定义数据列的数据类型和格式。</span><span class="sxs-lookup"><span data-stu-id="e44e1-129">Defines how a data column appears in the **External Data** window in the Visio user interface and qualifies the data in the column by defining its data type and formatting.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="e44e1-130">属性</span><span class="sxs-lookup"><span data-stu-id="e44e1-130">Attributes</span></span>

|<span data-ttu-id="e44e1-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="e44e1-131">**Attribute**</span></span>|<span data-ttu-id="e44e1-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="e44e1-132">**Type**</span></span>|<span data-ttu-id="e44e1-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="e44e1-133">**Required**</span></span>|<span data-ttu-id="e44e1-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="e44e1-134">**Description**</span></span>|<span data-ttu-id="e44e1-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e44e1-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e44e1-136">SortAsc</span><span class="sxs-lookup"><span data-stu-id="e44e1-136">SortAsc</span></span>  <br/> |<span data-ttu-id="e44e1-137">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="e44e1-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="e44e1-138">可选</span><span class="sxs-lookup"><span data-stu-id="e44e1-138">optional</span></span>  <br/> |<span data-ttu-id="e44e1-139">数据排序所基于的列。</span><span class="sxs-lookup"><span data-stu-id="e44e1-139">The column on which to sort the data.</span></span>  <br/> |<span data-ttu-id="e44e1-140">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e44e1-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="e44e1-141">SortColumn</span><span class="sxs-lookup"><span data-stu-id="e44e1-141">SortColumn</span></span>  <br/> |<span data-ttu-id="e44e1-142">xsd：string</span><span class="sxs-lookup"><span data-stu-id="e44e1-142">xsd:string</span></span>  <br/> |<span data-ttu-id="e44e1-143">可选</span><span class="sxs-lookup"><span data-stu-id="e44e1-143">optional</span></span>  <br/> |<span data-ttu-id="e44e1-144">按升序排序 **SortColumn** 列 (1) 0 (0) 排序。</span><span class="sxs-lookup"><span data-stu-id="e44e1-144">Whether to sort the **SortColumn** column in ascending (1) or descending (0) order.</span></span>  <br/> |<span data-ttu-id="e44e1-145">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e44e1-145">Values of the xsd:string type.</span></span>  <br/> |
   

