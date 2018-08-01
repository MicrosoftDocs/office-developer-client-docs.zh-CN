---
title: AutoLinkComparison 元素 （DataRecordSet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: af5eb7fd-89c6-49bf-4e45-431b63d6cd6a
description: 定义一个将形状数据项目从上次成功自动链接执行的操作在用户界面中将父 DataRecordset 元素中的列进行比较的规则。
ms.openlocfilehash: 38970a84676f769c36c9bdc3f8334652f7d9ec21
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779669"
---
# <a name="autolinkcomparison-element-datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="771ab-103">AutoLinkComparison 元素 （DataRecordSet_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="771ab-103">AutoLinkComparison element (DataRecordSet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="771ab-104">定义一个将形状数据项目从上次成功自动链接执行的操作在用户界面中将父**DataRecordset**元素中的列进行比较的规则。</span><span class="sxs-lookup"><span data-stu-id="771ab-104">Defines a rule that compares a column in the parent **DataRecordset** element with a shape data item from the last successful automatic linking action performed in the user interface.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="771ab-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="771ab-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="771ab-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="771ab-106">**Element type**</span></span> <br/> |[<span data-ttu-id="771ab-107">AutoLinkComparison_Type</span><span class="sxs-lookup"><span data-stu-id="771ab-107">AutoLinkComparison_Type</span></span>](autolinkcomparison_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="771ab-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="771ab-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="771ab-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="771ab-109">**Schema file**</span></span> <br/> |<span data-ttu-id="771ab-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="771ab-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="771ab-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="771ab-111">**Document parts**</span></span> <br/> |<span data-ttu-id="771ab-112">recordsets.xml</span><span class="sxs-lookup"><span data-stu-id="771ab-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="771ab-113">定义</span><span class="sxs-lookup"><span data-stu-id="771ab-113">Definition</span></span>

```XML
<xs:element name="AutoLinkComparison" type="AutoLinkComparison_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="771ab-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="771ab-114">Elements and attributes</span></span>

<span data-ttu-id="771ab-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="771ab-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="771ab-116">父元素</span><span class="sxs-lookup"><span data-stu-id="771ab-116">Parent elements</span></span>

|<span data-ttu-id="771ab-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="771ab-117">**Element**</span></span>|<span data-ttu-id="771ab-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="771ab-118">**Type**</span></span>|<span data-ttu-id="771ab-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="771ab-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="771ab-120">数据记录集</span><span class="sxs-lookup"><span data-stu-id="771ab-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="771ab-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="771ab-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="771ab-122">在绘图页指定记录集和该记录集和形状之间的数据绑定。</span><span class="sxs-lookup"><span data-stu-id="771ab-122">Specifies a recordset and the data binding between that recordset and shapes in drawing pages.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="771ab-123">子元素</span><span class="sxs-lookup"><span data-stu-id="771ab-123">Child elements</span></span>

<span data-ttu-id="771ab-124">无。</span><span class="sxs-lookup"><span data-stu-id="771ab-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="771ab-125">属性</span><span class="sxs-lookup"><span data-stu-id="771ab-125">Attributes</span></span>

|<span data-ttu-id="771ab-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="771ab-126">**Attribute**</span></span>|<span data-ttu-id="771ab-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="771ab-127">**Type**</span></span>|<span data-ttu-id="771ab-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="771ab-128">**Required**</span></span>|<span data-ttu-id="771ab-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="771ab-129">**Description**</span></span>|<span data-ttu-id="771ab-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="771ab-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="771ab-131">ColumnName</span><span class="sxs-lookup"><span data-stu-id="771ab-131">ColumnName</span></span>  <br/> |<span data-ttu-id="771ab-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="771ab-132">xsd:string</span></span>  <br/> |<span data-ttu-id="771ab-133">必需</span><span class="sxs-lookup"><span data-stu-id="771ab-133">required</span></span>  <br/> |<span data-ttu-id="771ab-134">对应于 ADO recordset 中的列名称。</span><span class="sxs-lookup"><span data-stu-id="771ab-134">Corresponds to a column name in the ADO recordset.</span></span>  <br/> |<span data-ttu-id="771ab-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="771ab-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="771ab-136">ContextType</span><span class="sxs-lookup"><span data-stu-id="771ab-136">ContextType</span></span>  <br/> |<span data-ttu-id="771ab-137">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="771ab-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="771ab-138">必需</span><span class="sxs-lookup"><span data-stu-id="771ab-138">required</span></span>  <br/> |<span data-ttu-id="771ab-139">指定要用于比较的组或形状的属性。</span><span class="sxs-lookup"><span data-stu-id="771ab-139">Specifies properties of the group or shape to use for the comparison.</span></span> <span data-ttu-id="771ab-140">可能值如下表所示。</span><span class="sxs-lookup"><span data-stu-id="771ab-140">Possible values are shown in the following table.</span></span>  <br/> |<span data-ttu-id="771ab-141">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="771ab-141">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="771ab-142">ContextTypeLabel</span><span class="sxs-lookup"><span data-stu-id="771ab-142">ContextTypeLabel</span></span>  <br/> |<span data-ttu-id="771ab-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="771ab-143">xsd:string</span></span>  <br/> |<span data-ttu-id="771ab-144">可选</span><span class="sxs-lookup"><span data-stu-id="771ab-144">optional</span></span>  <br/> |<span data-ttu-id="771ab-145">如果 ContextType 值为 2 或 3，此属性需要定义比较。</span><span class="sxs-lookup"><span data-stu-id="771ab-145">If the ContextType value is 2 or 3, this attribute is required to define a comparison.</span></span> <span data-ttu-id="771ab-146">为 ContextType = 2，ContextTypeLabel 必须是形状数据项目标签，并且如果**ContextType** = 3，ContextTypeLabel 必须是本地行名称。</span><span class="sxs-lookup"><span data-stu-id="771ab-146">For ContextType = 2, ContextTypeLabel must be the shape data item label, and if **ContextType** = 3, ContextTypeLabel must be the local row name.</span></span>  <br/> |<span data-ttu-id="771ab-147">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="771ab-147">Values of the xsd:string type.</span></span>  <br/> |
   

