---
title: RuleSet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2fc66419-f299-8573-ec72-0ea5ff39a896
ms.openlocfilehash: dfb0d50cd1c39be9b98a880028b5c4b4dc597bc0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781204"
---
# <a name="rulesettype-complextype-visio-xml"></a><span data-ttu-id="6fbec-102">RuleSet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="6fbec-102">RuleSet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="6fbec-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="6fbec-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6fbec-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6fbec-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="6fbec-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6fbec-105">**Schema file**</span></span> <br/> |<span data-ttu-id="6fbec-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="6fbec-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="6fbec-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="6fbec-107">**Extension base**</span></span> <br/> |<span data-ttu-id="6fbec-108">无</span><span class="sxs-lookup"><span data-stu-id="6fbec-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6fbec-109">定义</span><span class="sxs-lookup"><span data-stu-id="6fbec-109">Definition</span></span>

```XML
          <xs:complexType name="RuleSet_Type">
          
          <xs:sequence>
    <xs:element name="RuleSetFlags"  type="RuleSetFlags_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Rule"  type="Rule_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="Name"
  type="xsd:string"
    />
    <xs:attribute name="NameU"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="Description"
  type="xsd:string"
    />
    <xs:attribute name="Enabled"
  type="xsd:boolean"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="6fbec-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6fbec-110">Elements and attributes</span></span>

<span data-ttu-id="6fbec-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="6fbec-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="6fbec-112">子元素</span><span class="sxs-lookup"><span data-stu-id="6fbec-112">Child elements</span></span>

|<span data-ttu-id="6fbec-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="6fbec-113">**Element**</span></span>|<span data-ttu-id="6fbec-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="6fbec-114">**Type**</span></span>|<span data-ttu-id="6fbec-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="6fbec-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6fbec-116">Rule</span><span class="sxs-lookup"><span data-stu-id="6fbec-116">Rule</span></span>](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="6fbec-117">Rule_Type</span><span class="sxs-lookup"><span data-stu-id="6fbec-117">Rule_Type</span></span>](rule_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="6fbec-118">RuleSetFlags</span><span class="sxs-lookup"><span data-stu-id="6fbec-118">RuleSetFlags</span></span>](rulesetflags-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="6fbec-119">RuleSetFlags_Type</span><span class="sxs-lookup"><span data-stu-id="6fbec-119">RuleSetFlags_Type</span></span>](rulesetflags_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="6fbec-120">属性</span><span class="sxs-lookup"><span data-stu-id="6fbec-120">Attributes</span></span>

|<span data-ttu-id="6fbec-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="6fbec-121">**Attribute**</span></span>|<span data-ttu-id="6fbec-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="6fbec-122">**Type**</span></span>|<span data-ttu-id="6fbec-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="6fbec-123">**Required**</span></span>|<span data-ttu-id="6fbec-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="6fbec-124">**Description**</span></span>|<span data-ttu-id="6fbec-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="6fbec-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6fbec-126">说明</span><span class="sxs-lookup"><span data-stu-id="6fbec-126">Description</span></span>  <br/> |<span data-ttu-id="6fbec-127">xsd: string</span><span class="sxs-lookup"><span data-stu-id="6fbec-127">xsd:string</span></span>  <br/> |<span data-ttu-id="6fbec-128">可选</span><span class="sxs-lookup"><span data-stu-id="6fbec-128">optional</span></span>  <br/> ||<span data-ttu-id="6fbec-129">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6fbec-129">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="6fbec-130">已启用</span><span class="sxs-lookup"><span data-stu-id="6fbec-130">Enabled</span></span>  <br/> |<span data-ttu-id="6fbec-131">化</span><span class="sxs-lookup"><span data-stu-id="6fbec-131">xsd:boolean</span></span>  <br/> |<span data-ttu-id="6fbec-132">可选</span><span class="sxs-lookup"><span data-stu-id="6fbec-132">optional</span></span>  <br/> ||<span data-ttu-id="6fbec-133">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="6fbec-133">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="6fbec-134">ID</span><span class="sxs-lookup"><span data-stu-id="6fbec-134">ID</span></span>  <br/> |<span data-ttu-id="6fbec-135">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="6fbec-135">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="6fbec-136">必需</span><span class="sxs-lookup"><span data-stu-id="6fbec-136">required</span></span>  <br/> ||<span data-ttu-id="6fbec-137">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6fbec-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="6fbec-138">名称</span><span class="sxs-lookup"><span data-stu-id="6fbec-138">Name</span></span>  <br/> |<span data-ttu-id="6fbec-139">xsd: string</span><span class="sxs-lookup"><span data-stu-id="6fbec-139">xsd:string</span></span>  <br/> |<span data-ttu-id="6fbec-140">可选</span><span class="sxs-lookup"><span data-stu-id="6fbec-140">optional</span></span>  <br/> ||<span data-ttu-id="6fbec-141">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6fbec-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="6fbec-142">NameU</span><span class="sxs-lookup"><span data-stu-id="6fbec-142">NameU</span></span>  <br/> |<span data-ttu-id="6fbec-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="6fbec-143">xsd:string</span></span>  <br/> |<span data-ttu-id="6fbec-144">必需</span><span class="sxs-lookup"><span data-stu-id="6fbec-144">required</span></span>  <br/> ||<span data-ttu-id="6fbec-145">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6fbec-145">Values of the xsd:string type.</span></span>  <br/> |
   

