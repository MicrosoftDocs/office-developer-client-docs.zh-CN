---
title: 'Rule_Type COMPLEXType (Visio XML) '
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
# <a name="rule_type-complextype-visio-xml"></a><span data-ttu-id="ae81d-102">Rule_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="ae81d-102">Rule_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="ae81d-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="ae81d-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ae81d-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ae81d-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="ae81d-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ae81d-105">**Schema file**</span></span> <br/> |<span data-ttu-id="ae81d-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="ae81d-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="ae81d-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="ae81d-107">**Extension base**</span></span> <br/> |<span data-ttu-id="ae81d-108">无</span><span class="sxs-lookup"><span data-stu-id="ae81d-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ae81d-109">定义</span><span class="sxs-lookup"><span data-stu-id="ae81d-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="ae81d-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ae81d-110">Elements and attributes</span></span>

<span data-ttu-id="ae81d-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ae81d-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="ae81d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ae81d-112">Child elements</span></span>

|<span data-ttu-id="ae81d-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="ae81d-113">**Element**</span></span>|<span data-ttu-id="ae81d-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="ae81d-114">**Type**</span></span>|<span data-ttu-id="ae81d-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="ae81d-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ae81d-116">RuleFilter</span><span class="sxs-lookup"><span data-stu-id="ae81d-116">RuleFilter</span></span>](rulefilter-element-rule_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="ae81d-117">RuleFilter_Type</span><span class="sxs-lookup"><span data-stu-id="ae81d-117">RuleFilter_Type</span></span>](rulefilter_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="ae81d-118">RuleTest</span><span class="sxs-lookup"><span data-stu-id="ae81d-118">RuleTest</span></span>](ruletest-element-rule_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="ae81d-119">RuleTest_Type</span><span class="sxs-lookup"><span data-stu-id="ae81d-119">RuleTest_Type</span></span>](ruletest_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="ae81d-120">属性</span><span class="sxs-lookup"><span data-stu-id="ae81d-120">Attributes</span></span>

|<span data-ttu-id="ae81d-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="ae81d-121">**Attribute**</span></span>|<span data-ttu-id="ae81d-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="ae81d-122">**Type**</span></span>|<span data-ttu-id="ae81d-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="ae81d-123">**Required**</span></span>|<span data-ttu-id="ae81d-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="ae81d-124">**Description**</span></span>|<span data-ttu-id="ae81d-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="ae81d-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ae81d-126">类别</span><span class="sxs-lookup"><span data-stu-id="ae81d-126">Category</span></span>  <br/> |<span data-ttu-id="ae81d-127">xsd：string</span><span class="sxs-lookup"><span data-stu-id="ae81d-127">xsd:string</span></span>  <br/> |<span data-ttu-id="ae81d-128">可选</span><span class="sxs-lookup"><span data-stu-id="ae81d-128">optional</span></span>  <br/> ||<span data-ttu-id="ae81d-129">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ae81d-129">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="ae81d-130">说明</span><span class="sxs-lookup"><span data-stu-id="ae81d-130">Description</span></span>  <br/> |<span data-ttu-id="ae81d-131">xsd：string</span><span class="sxs-lookup"><span data-stu-id="ae81d-131">xsd:string</span></span>  <br/> |<span data-ttu-id="ae81d-132">可选</span><span class="sxs-lookup"><span data-stu-id="ae81d-132">optional</span></span>  <br/> ||<span data-ttu-id="ae81d-133">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ae81d-133">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="ae81d-134">ID</span><span class="sxs-lookup"><span data-stu-id="ae81d-134">ID</span></span>  <br/> |<span data-ttu-id="ae81d-135">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ae81d-135">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ae81d-136">必需</span><span class="sxs-lookup"><span data-stu-id="ae81d-136">required</span></span>  <br/> ||<span data-ttu-id="ae81d-137">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ae81d-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="ae81d-138">忽略</span><span class="sxs-lookup"><span data-stu-id="ae81d-138">Ignored</span></span>  <br/> |<span data-ttu-id="ae81d-139">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="ae81d-139">xsd:boolean</span></span>  <br/> |<span data-ttu-id="ae81d-140">可选</span><span class="sxs-lookup"><span data-stu-id="ae81d-140">optional</span></span>  <br/> ||<span data-ttu-id="ae81d-141">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ae81d-141">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="ae81d-142">NameU</span><span class="sxs-lookup"><span data-stu-id="ae81d-142">NameU</span></span>  <br/> |<span data-ttu-id="ae81d-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="ae81d-143">xsd:string</span></span>  <br/> |<span data-ttu-id="ae81d-144">必需</span><span class="sxs-lookup"><span data-stu-id="ae81d-144">required</span></span>  <br/> ||<span data-ttu-id="ae81d-145">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ae81d-145">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="ae81d-146">RuleTarget</span><span class="sxs-lookup"><span data-stu-id="ae81d-146">RuleTarget</span></span>  <br/> |<span data-ttu-id="ae81d-147">xsd：int</span><span class="sxs-lookup"><span data-stu-id="ae81d-147">xsd:int</span></span>  <br/> |<span data-ttu-id="ae81d-148">可选</span><span class="sxs-lookup"><span data-stu-id="ae81d-148">optional</span></span>  <br/> ||<span data-ttu-id="ae81d-149">xsd：int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ae81d-149">Values of the xsd:int type.</span></span>  <br/> |
   

