---
title: DataRecordSets 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c75b3233-9ac5-d29c-a658-d554e86e6be4
description: 包含文档中的所有数据记录集元素。
ms.openlocfilehash: 7730e55f0025181db193a1e64226e879f9072e90
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401487"
---
# <a name="datarecordsets-element-visio-xml"></a><span data-ttu-id="bc556-103">DataRecordSets 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="bc556-103">DataRecordSets element ('Visio XML')</span></span>

<span data-ttu-id="bc556-104">包含文档中的所有**数据记录集**元素。</span><span class="sxs-lookup"><span data-stu-id="bc556-104">Contains all the **DataRecordset** elements in the document.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="bc556-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="bc556-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bc556-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="bc556-106">**Element type**</span></span> <br/> |[<span data-ttu-id="bc556-107">DataRecordSets_Type</span><span class="sxs-lookup"><span data-stu-id="bc556-107">DataRecordSets_Type</span></span>](datarecordsets_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="bc556-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="bc556-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="bc556-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="bc556-109">**Schema file**</span></span> <br/> |<span data-ttu-id="bc556-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="bc556-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="bc556-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="bc556-111">**Document parts**</span></span> <br/> |<span data-ttu-id="bc556-112">recordsets.xml</span><span class="sxs-lookup"><span data-stu-id="bc556-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="bc556-113">定义</span><span class="sxs-lookup"><span data-stu-id="bc556-113">Definition</span></span>

```XML
< xs:element name="DataRecordSets" type="DataRecordSets_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="bc556-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="bc556-114">Elements and attributes</span></span>

<span data-ttu-id="bc556-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="bc556-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="bc556-116">父元素</span><span class="sxs-lookup"><span data-stu-id="bc556-116">Parent elements</span></span>

<span data-ttu-id="bc556-117">无。</span><span class="sxs-lookup"><span data-stu-id="bc556-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="bc556-118">子元素</span><span class="sxs-lookup"><span data-stu-id="bc556-118">Child elements</span></span>

|<span data-ttu-id="bc556-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="bc556-119">**Element**</span></span>|<span data-ttu-id="bc556-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="bc556-120">**Type**</span></span>|<span data-ttu-id="bc556-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="bc556-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="bc556-122">数据记录集</span><span class="sxs-lookup"><span data-stu-id="bc556-122">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="bc556-123">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="bc556-123">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bc556-124">包含文档中的所有**数据记录集**元素。</span><span class="sxs-lookup"><span data-stu-id="bc556-124">Contains all the **DataRecordset** elements in the document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="bc556-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="bc556-125">Attributes</span></span>

|<span data-ttu-id="bc556-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="bc556-126">**Attribute**</span></span>|<span data-ttu-id="bc556-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="bc556-127">**Type**</span></span>|<span data-ttu-id="bc556-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="bc556-128">**Required**</span></span>|<span data-ttu-id="bc556-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="bc556-129">**Description**</span></span>|<span data-ttu-id="bc556-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="bc556-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bc556-131">ActiveRecordsetID</span><span class="sxs-lookup"><span data-stu-id="bc556-131">ActiveRecordsetID</span></span>  <br/> |<span data-ttu-id="bc556-132">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="bc556-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="bc556-133">可选</span><span class="sxs-lookup"><span data-stu-id="bc556-133">optional</span></span>  <br/> |<span data-ttu-id="bc556-134">打开**外部数据**窗口时该窗口将关闭，以便使其可以还原下次窗口中的活动数据记录集的 ID。</span><span class="sxs-lookup"><span data-stu-id="bc556-134">The ID of the active data recordset in the **External Data** window when the window closes, so that it can be restored the next time the window opens.</span></span>  <br/> |<span data-ttu-id="bc556-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="bc556-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="bc556-136">DataWindowOrder</span><span class="sxs-lookup"><span data-stu-id="bc556-136">DataWindowOrder</span></span>  <br/> |<span data-ttu-id="bc556-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="bc556-137">xsd:string</span></span>  <br/> |<span data-ttu-id="bc556-138">可选</span><span class="sxs-lookup"><span data-stu-id="bc556-138">optional</span></span>  <br/> |<span data-ttu-id="bc556-139">在**外部数据**窗口的选项卡上显示的数据记录集的顺序。</span><span class="sxs-lookup"><span data-stu-id="bc556-139">The order of the data recordsets displayed on the tabs of the **External Data** window.</span></span> <span data-ttu-id="bc556-140">数据记录集 Id，并用分号分隔的一个已排序的列表。</span><span class="sxs-lookup"><span data-stu-id="bc556-140">An ordered list of data-recordset IDs, separated by semi-colons.</span></span>  <br/> |<span data-ttu-id="bc556-141">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="bc556-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="bc556-142">NextID</span><span class="sxs-lookup"><span data-stu-id="bc556-142">NextID</span></span>  <br/> |<span data-ttu-id="bc556-143">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="bc556-143">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="bc556-144">必需</span><span class="sxs-lookup"><span data-stu-id="bc556-144">required</span></span>  <br/> |<span data-ttu-id="bc556-145">下一个可用 ID 为新的数据记录集的。</span><span class="sxs-lookup"><span data-stu-id="bc556-145">The next available ID for a new data recordset.</span></span>  <br/> |<span data-ttu-id="bc556-146">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="bc556-146">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

