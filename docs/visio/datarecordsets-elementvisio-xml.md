---
title: DataRecordSets 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c75b3233-9ac5-d29c-a658-d554e86e6be4
description: 包含文档中的所有 DataRecordset 元素。
ms.openlocfilehash: efa7d58eabc1b1192862dbbe090ddd5008947c1d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542441"
---
# <a name="datarecordsets-element-visio-xml"></a><span data-ttu-id="30464-103">DataRecordSets 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="30464-103">DataRecordSets element (Visio XML)</span></span>

<span data-ttu-id="30464-104">包含文档中的所有**DataRecordset**元素。</span><span class="sxs-lookup"><span data-stu-id="30464-104">Contains all the **DataRecordset** elements in the document.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="30464-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="30464-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="30464-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="30464-106">**Element type**</span></span> <br/> |[<span data-ttu-id="30464-107">DataRecordSets_Type</span><span class="sxs-lookup"><span data-stu-id="30464-107">DataRecordSets_Type</span></span>](datarecordsets_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="30464-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="30464-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="30464-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="30464-109">**Schema file**</span></span> <br/> |<span data-ttu-id="30464-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="30464-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="30464-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="30464-111">**Document parts**</span></span> <br/> |<span data-ttu-id="30464-112">记录集 .xml</span><span class="sxs-lookup"><span data-stu-id="30464-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="30464-113">定义</span><span class="sxs-lookup"><span data-stu-id="30464-113">Definition</span></span>

```XML
< xs:element name="DataRecordSets" type="DataRecordSets_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="30464-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="30464-114">Elements and attributes</span></span>

<span data-ttu-id="30464-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="30464-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="30464-116">父元素</span><span class="sxs-lookup"><span data-stu-id="30464-116">Parent elements</span></span>

<span data-ttu-id="30464-117">无。</span><span class="sxs-lookup"><span data-stu-id="30464-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="30464-118">子元素</span><span class="sxs-lookup"><span data-stu-id="30464-118">Child elements</span></span>

|<span data-ttu-id="30464-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="30464-119">**Element**</span></span>|<span data-ttu-id="30464-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="30464-120">**Type**</span></span>|<span data-ttu-id="30464-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="30464-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="30464-122">DataRecordSet</span><span class="sxs-lookup"><span data-stu-id="30464-122">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="30464-123">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="30464-123">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="30464-124">包含文档中的所有**DataRecordset**元素。</span><span class="sxs-lookup"><span data-stu-id="30464-124">Contains all the **DataRecordset** elements in the document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="30464-125">属性</span><span class="sxs-lookup"><span data-stu-id="30464-125">Attributes</span></span>

|<span data-ttu-id="30464-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="30464-126">**Attribute**</span></span>|<span data-ttu-id="30464-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="30464-127">**Type**</span></span>|<span data-ttu-id="30464-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="30464-128">**Required**</span></span>|<span data-ttu-id="30464-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="30464-129">**Description**</span></span>|<span data-ttu-id="30464-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="30464-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="30464-131">ActiveRecordsetID</span><span class="sxs-lookup"><span data-stu-id="30464-131">ActiveRecordsetID</span></span>  <br/> |<span data-ttu-id="30464-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="30464-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="30464-133">可选</span><span class="sxs-lookup"><span data-stu-id="30464-133">optional</span></span>  <br/> |<span data-ttu-id="30464-134">窗口关闭时, "**外部数据**" 窗口中活动数据记录集的 ID, 以便在下次打开窗口时可对其进行还原。</span><span class="sxs-lookup"><span data-stu-id="30464-134">The ID of the active data recordset in the **External Data** window when the window closes, so that it can be restored the next time the window opens.</span></span>  <br/> |<span data-ttu-id="30464-135">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30464-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="30464-136">DataWindowOrder</span><span class="sxs-lookup"><span data-stu-id="30464-136">DataWindowOrder</span></span>  <br/> |<span data-ttu-id="30464-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="30464-137">xsd:string</span></span>  <br/> |<span data-ttu-id="30464-138">可选</span><span class="sxs-lookup"><span data-stu-id="30464-138">optional</span></span>  <br/> |<span data-ttu-id="30464-139">数据记录集在 "**外部数据**" 窗口的选项卡上显示的顺序。</span><span class="sxs-lookup"><span data-stu-id="30464-139">The order of the data recordsets displayed on the tabs of the **External Data** window.</span></span> <span data-ttu-id="30464-140">数据记录集 Id 的已排序列表, 用分号分隔。</span><span class="sxs-lookup"><span data-stu-id="30464-140">An ordered list of data-recordset IDs, separated by semi-colons.</span></span>  <br/> |<span data-ttu-id="30464-141">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30464-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="30464-142">NextID</span><span class="sxs-lookup"><span data-stu-id="30464-142">NextID</span></span>  <br/> |<span data-ttu-id="30464-143">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="30464-143">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="30464-144">必需</span><span class="sxs-lookup"><span data-stu-id="30464-144">required</span></span>  <br/> |<span data-ttu-id="30464-145">新的数据记录集的下一个可用 ID。</span><span class="sxs-lookup"><span data-stu-id="30464-145">The next available ID for a new data recordset.</span></span>  <br/> |<span data-ttu-id="30464-146">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30464-146">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

