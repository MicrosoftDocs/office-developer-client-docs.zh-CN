---
title: DataColumns 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 34e25349-d0fa-b3a0-425b-778184e9f58f
description: 包含数据记录集中的所有 DataColumn 元素。
ms.openlocfilehash: a7a0a8faefdb965384e435ee3a9b059a3acbc3f0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345246"
---
# <a name="datacolumns-element-datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="32700-103">DataColumns 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="32700-103">DataColumns element (DataRecordSet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="32700-104">包含数据记录集中的所有**DataColumn**元素。</span><span class="sxs-lookup"><span data-stu-id="32700-104">Contains all the **DataColumn** elements in a data recordset.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="32700-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="32700-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="32700-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="32700-106">**Element type**</span></span> <br/> |[<span data-ttu-id="32700-107">DataColumns_Type</span><span class="sxs-lookup"><span data-stu-id="32700-107">DataColumns_Type</span></span>](datacolumns_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="32700-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="32700-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="32700-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="32700-109">**Schema file**</span></span> <br/> |<span data-ttu-id="32700-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="32700-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="32700-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="32700-111">**Document parts**</span></span> <br/> |<span data-ttu-id="32700-112">记录集 .xml</span><span class="sxs-lookup"><span data-stu-id="32700-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="32700-113">定义</span><span class="sxs-lookup"><span data-stu-id="32700-113">Definition</span></span>

```XML
< xs:element name="DataColumns" type="DataColumns_Type" minOccurs="1" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="32700-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="32700-114">Elements and attributes</span></span>

<span data-ttu-id="32700-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="32700-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="32700-116">父元素</span><span class="sxs-lookup"><span data-stu-id="32700-116">Parent elements</span></span>

|<span data-ttu-id="32700-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="32700-117">**Element**</span></span>|<span data-ttu-id="32700-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="32700-118">**Type**</span></span>|<span data-ttu-id="32700-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="32700-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="32700-120">DataRecordSet</span><span class="sxs-lookup"><span data-stu-id="32700-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="32700-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="32700-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="32700-122">在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。</span><span class="sxs-lookup"><span data-stu-id="32700-122">Stores, formats, refreshes, and exposes data queried from a database in Microsoft Visio.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="32700-123">子元素</span><span class="sxs-lookup"><span data-stu-id="32700-123">Child elements</span></span>

|<span data-ttu-id="32700-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="32700-124">**Element**</span></span>|<span data-ttu-id="32700-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="32700-125">**Type**</span></span>|<span data-ttu-id="32700-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="32700-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="32700-127">DataColumn</span><span class="sxs-lookup"><span data-stu-id="32700-127">DataColumn</span></span>](datacolumn-element-datacolumns_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="32700-128">DataColumn_Type</span><span class="sxs-lookup"><span data-stu-id="32700-128">DataColumn_Type</span></span>](datacolumn_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="32700-129">定义数据列在 Visio 用户界面的**外部数据**窗口中的显示方式, 并通过定义数据类型和格式来限定列中的数据。</span><span class="sxs-lookup"><span data-stu-id="32700-129">Defines how a data column appears in the **External Data** window in the Visio user interface and qualifies the data in the column by defining its data type and formatting.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="32700-130">属性</span><span class="sxs-lookup"><span data-stu-id="32700-130">Attributes</span></span>

|<span data-ttu-id="32700-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="32700-131">**Attribute**</span></span>|<span data-ttu-id="32700-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="32700-132">**Type**</span></span>|<span data-ttu-id="32700-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="32700-133">**Required**</span></span>|<span data-ttu-id="32700-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="32700-134">**Description**</span></span>|<span data-ttu-id="32700-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="32700-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="32700-136">SortAsc</span><span class="sxs-lookup"><span data-stu-id="32700-136">SortAsc</span></span>  <br/> |<span data-ttu-id="32700-137">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="32700-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="32700-138">可选</span><span class="sxs-lookup"><span data-stu-id="32700-138">optional</span></span>  <br/> |<span data-ttu-id="32700-139">对数据进行排序所依据的列。</span><span class="sxs-lookup"><span data-stu-id="32700-139">The column on which to sort the data.</span></span>  <br/> |<span data-ttu-id="32700-140">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="32700-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="32700-141">SortColumn</span><span class="sxs-lookup"><span data-stu-id="32700-141">SortColumn</span></span>  <br/> |<span data-ttu-id="32700-142">xsd: string</span><span class="sxs-lookup"><span data-stu-id="32700-142">xsd:string</span></span>  <br/> |<span data-ttu-id="32700-143">可选</span><span class="sxs-lookup"><span data-stu-id="32700-143">optional</span></span>  <br/> |<span data-ttu-id="32700-144">是按升序 (1) 还是降序 (0) 顺序对**SortColumn**列进行排序。</span><span class="sxs-lookup"><span data-stu-id="32700-144">Whether to sort the **SortColumn** column in ascending (1) or descending (0) order.</span></span>  <br/> |<span data-ttu-id="32700-145">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="32700-145">Values of the xsd:string type.</span></span>  <br/> |
   

