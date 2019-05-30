---
title: AutoLinkComparison 元素 (DataRecordSet_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: af5eb7fd-89c6-49bf-4e45-431b63d6cd6a
description: 定义一个规则, 该规则将父 DataRecordset 元素中的列与在用户界面中上次执行的成功自动链接操作的形状数据项进行比较。
ms.openlocfilehash: 7d25d12844fe33ec1f1abb66984c5be40c4995c3
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537869"
---
# <a name="autolinkcomparison-element-datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="d45fc-103">AutoLinkComparison 元素 (DataRecordSet_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d45fc-103">AutoLinkComparison element (DataRecordSet_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="d45fc-104">定义一个规则, 该规则将父**DataRecordset**元素中的列与在用户界面中上次执行的成功自动链接操作的形状数据项进行比较。</span><span class="sxs-lookup"><span data-stu-id="d45fc-104">Defines a rule that compares a column in the parent **DataRecordset** element with a shape data item from the last successful automatic linking action performed in the user interface.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="d45fc-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d45fc-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d45fc-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d45fc-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d45fc-107">AutoLinkComparison_Type</span><span class="sxs-lookup"><span data-stu-id="d45fc-107">AutoLinkComparison_Type</span></span>](autolinkcomparison_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d45fc-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d45fc-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d45fc-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d45fc-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d45fc-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="d45fc-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d45fc-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d45fc-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d45fc-112">记录集 .xml</span><span class="sxs-lookup"><span data-stu-id="d45fc-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d45fc-113">定义</span><span class="sxs-lookup"><span data-stu-id="d45fc-113">Definition</span></span>

```XML
<xs:element name="AutoLinkComparison" type="AutoLinkComparison_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d45fc-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d45fc-114">Elements and attributes</span></span>

<span data-ttu-id="d45fc-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="d45fc-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d45fc-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d45fc-116">Parent elements</span></span>

|<span data-ttu-id="d45fc-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d45fc-117">**Element**</span></span>|<span data-ttu-id="d45fc-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d45fc-118">**Type**</span></span>|<span data-ttu-id="d45fc-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d45fc-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d45fc-120">DataRecordSet</span><span class="sxs-lookup"><span data-stu-id="d45fc-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d45fc-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="d45fc-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d45fc-122">指定在绘图页中该 recordset 和形状之间的 recordset 和数据绑定。</span><span class="sxs-lookup"><span data-stu-id="d45fc-122">Specifies a recordset and the data binding between that recordset and shapes in drawing pages.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d45fc-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d45fc-123">Child elements</span></span>

<span data-ttu-id="d45fc-124">无。</span><span class="sxs-lookup"><span data-stu-id="d45fc-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d45fc-125">属性</span><span class="sxs-lookup"><span data-stu-id="d45fc-125">Attributes</span></span>

|<span data-ttu-id="d45fc-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="d45fc-126">**Attribute**</span></span>|<span data-ttu-id="d45fc-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="d45fc-127">**Type**</span></span>|<span data-ttu-id="d45fc-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="d45fc-128">**Required**</span></span>|<span data-ttu-id="d45fc-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="d45fc-129">**Description**</span></span>|<span data-ttu-id="d45fc-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d45fc-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d45fc-131">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d45fc-131">ColumnName</span></span>  <br/> |<span data-ttu-id="d45fc-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d45fc-132">xsd:string</span></span>  <br/> |<span data-ttu-id="d45fc-133">必需</span><span class="sxs-lookup"><span data-stu-id="d45fc-133">required</span></span>  <br/> |<span data-ttu-id="d45fc-134">对应于 ADO recordset 中的列名称。</span><span class="sxs-lookup"><span data-stu-id="d45fc-134">Corresponds to a column name in the ADO recordset.</span></span>  <br/> |<span data-ttu-id="d45fc-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d45fc-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d45fc-136">ContextType</span><span class="sxs-lookup"><span data-stu-id="d45fc-136">ContextType</span></span>  <br/> |<span data-ttu-id="d45fc-137">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d45fc-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d45fc-138">必需</span><span class="sxs-lookup"><span data-stu-id="d45fc-138">required</span></span>  <br/> |<span data-ttu-id="d45fc-139">指定要用于比较的组或形状的属性。</span><span class="sxs-lookup"><span data-stu-id="d45fc-139">Specifies properties of the group or shape to use for the comparison.</span></span> <span data-ttu-id="d45fc-140">下表中显示了可能的值。</span><span class="sxs-lookup"><span data-stu-id="d45fc-140">Possible values are shown in the following table.</span></span>  <br/> |<span data-ttu-id="d45fc-141">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d45fc-141">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d45fc-142">ContextTypeLabel</span><span class="sxs-lookup"><span data-stu-id="d45fc-142">ContextTypeLabel</span></span>  <br/> |<span data-ttu-id="d45fc-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d45fc-143">xsd:string</span></span>  <br/> |<span data-ttu-id="d45fc-144">可选</span><span class="sxs-lookup"><span data-stu-id="d45fc-144">optional</span></span>  <br/> |<span data-ttu-id="d45fc-145">如果 ContextType 值为2或 3, 则需要使用此属性来定义比较。</span><span class="sxs-lookup"><span data-stu-id="d45fc-145">If the ContextType value is 2 or 3, this attribute is required to define a comparison.</span></span> <span data-ttu-id="d45fc-146">对于 ContextType = 2, ContextTypeLabel 必须是 shape 数据项标签, 如果**ContextType** = 3, 则 ContextTypeLabel 必须为本地行名称。</span><span class="sxs-lookup"><span data-stu-id="d45fc-146">For ContextType = 2, ContextTypeLabel must be the shape data item label, and if **ContextType** = 3, ContextTypeLabel must be the local row name.</span></span>  <br/> |<span data-ttu-id="d45fc-147">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d45fc-147">Values of the xsd:string type.</span></span>  <br/> |
   

