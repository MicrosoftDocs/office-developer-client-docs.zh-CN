---
title: Rule_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d023139b-de1f-49f7-86d2-14a683bc5a46
ms.openlocfilehash: a1c3111458b90cd5e1b181a3b1776f64d8ec476b
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541713"
---
# <a name="ruletype-complextype-visio-xml"></a><span data-ttu-id="e03db-102">Rule_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="e03db-102">Rule_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="e03db-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="e03db-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e03db-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e03db-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="e03db-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e03db-105">**Schema file**</span></span> <br/> |<span data-ttu-id="e03db-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="e03db-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="e03db-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="e03db-107">**Extension base**</span></span> <br/> |<span data-ttu-id="e03db-108">无</span><span class="sxs-lookup"><span data-stu-id="e03db-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e03db-109">定义</span><span class="sxs-lookup"><span data-stu-id="e03db-109">Definition</span></span>

```XML
          <xs:complexType name="Rule_Type">
          
          <xs:sequence>
    <xs:element name="RuleFilter"  type="RuleFilter_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="RuleTest"  type="RuleTest_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="NameU"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="Category"
  type="xsd:string"
    />
    <xs:attribute name="Description"
  type="xsd:string"
    />
    <xs:attribute name="RuleTarget"
  type="xsd:int"
    />
    <xs:attribute name="Ignored"
  type="xsd:boolean"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e03db-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e03db-110">Elements and attributes</span></span>

<span data-ttu-id="e03db-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="e03db-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="e03db-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e03db-112">Child elements</span></span>

|<span data-ttu-id="e03db-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="e03db-113">**Element**</span></span>|<span data-ttu-id="e03db-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="e03db-114">**Type**</span></span>|<span data-ttu-id="e03db-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="e03db-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e03db-116">RuleFilter</span><span class="sxs-lookup"><span data-stu-id="e03db-116">RuleFilter</span></span>](rulefilter-element-rule_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e03db-117">RuleFilter_Type</span><span class="sxs-lookup"><span data-stu-id="e03db-117">RuleFilter_Type</span></span>](rulefilter_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="e03db-118">RuleTest</span><span class="sxs-lookup"><span data-stu-id="e03db-118">RuleTest</span></span>](ruletest-element-rule_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e03db-119">RuleTest_Type</span><span class="sxs-lookup"><span data-stu-id="e03db-119">RuleTest_Type</span></span>](ruletest_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="e03db-120">属性</span><span class="sxs-lookup"><span data-stu-id="e03db-120">Attributes</span></span>

|<span data-ttu-id="e03db-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="e03db-121">**Attribute**</span></span>|<span data-ttu-id="e03db-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="e03db-122">**Type**</span></span>|<span data-ttu-id="e03db-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="e03db-123">**Required**</span></span>|<span data-ttu-id="e03db-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="e03db-124">**Description**</span></span>|<span data-ttu-id="e03db-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e03db-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e03db-126">类别</span><span class="sxs-lookup"><span data-stu-id="e03db-126">Category</span></span>  <br/> |<span data-ttu-id="e03db-127">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e03db-127">xsd:string</span></span>  <br/> |<span data-ttu-id="e03db-128">可选</span><span class="sxs-lookup"><span data-stu-id="e03db-128">optional</span></span>  <br/> ||<span data-ttu-id="e03db-129">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e03db-129">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e03db-130">说明</span><span class="sxs-lookup"><span data-stu-id="e03db-130">Description</span></span>  <br/> |<span data-ttu-id="e03db-131">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e03db-131">xsd:string</span></span>  <br/> |<span data-ttu-id="e03db-132">可选</span><span class="sxs-lookup"><span data-stu-id="e03db-132">optional</span></span>  <br/> ||<span data-ttu-id="e03db-133">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e03db-133">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e03db-134">ID</span><span class="sxs-lookup"><span data-stu-id="e03db-134">ID</span></span>  <br/> |<span data-ttu-id="e03db-135">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e03db-135">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e03db-136">必需</span><span class="sxs-lookup"><span data-stu-id="e03db-136">required</span></span>  <br/> ||<span data-ttu-id="e03db-137">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e03db-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="e03db-138">Ignored</span><span class="sxs-lookup"><span data-stu-id="e03db-138">Ignored</span></span>  <br/> |<span data-ttu-id="e03db-139">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="e03db-139">xsd:boolean</span></span>  <br/> |<span data-ttu-id="e03db-140">可选</span><span class="sxs-lookup"><span data-stu-id="e03db-140">optional</span></span>  <br/> ||<span data-ttu-id="e03db-141">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e03db-141">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="e03db-142">NameU</span><span class="sxs-lookup"><span data-stu-id="e03db-142">NameU</span></span>  <br/> |<span data-ttu-id="e03db-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e03db-143">xsd:string</span></span>  <br/> |<span data-ttu-id="e03db-144">必需</span><span class="sxs-lookup"><span data-stu-id="e03db-144">required</span></span>  <br/> ||<span data-ttu-id="e03db-145">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e03db-145">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e03db-146">RuleTarget</span><span class="sxs-lookup"><span data-stu-id="e03db-146">RuleTarget</span></span>  <br/> |<span data-ttu-id="e03db-147">xsd: int</span><span class="sxs-lookup"><span data-stu-id="e03db-147">xsd:int</span></span>  <br/> |<span data-ttu-id="e03db-148">可选</span><span class="sxs-lookup"><span data-stu-id="e03db-148">optional</span></span>  <br/> ||<span data-ttu-id="e03db-149">Xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e03db-149">Values of the xsd:int type.</span></span>  <br/> |
   

