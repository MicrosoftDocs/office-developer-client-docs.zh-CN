---
title: RuleSet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2fc66419-f299-8573-ec72-0ea5ff39a896
ms.openlocfilehash: 3d8279b2995bcdf75f67fc7f65709dc3dab49642
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393619"
---
# <a name="rulesettype-complextype-visio-xml"></a><span data-ttu-id="85f4d-102">RuleSet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="85f4d-102">RuleSet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="85f4d-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="85f4d-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="85f4d-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="85f4d-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="85f4d-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="85f4d-105">**Schema file**</span></span> <br/> |<span data-ttu-id="85f4d-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="85f4d-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="85f4d-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="85f4d-107">**Extension base**</span></span> <br/> |<span data-ttu-id="85f4d-108">无</span><span class="sxs-lookup"><span data-stu-id="85f4d-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="85f4d-109">定义</span><span class="sxs-lookup"><span data-stu-id="85f4d-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="85f4d-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="85f4d-110">Elements and attributes</span></span>

<span data-ttu-id="85f4d-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="85f4d-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="85f4d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="85f4d-112">Child elements</span></span>

|<span data-ttu-id="85f4d-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="85f4d-113">**Element**</span></span>|<span data-ttu-id="85f4d-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="85f4d-114">**Type**</span></span>|<span data-ttu-id="85f4d-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="85f4d-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="85f4d-116">Rule</span><span class="sxs-lookup"><span data-stu-id="85f4d-116">Rule</span></span>](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="85f4d-117">Rule_Type</span><span class="sxs-lookup"><span data-stu-id="85f4d-117">Rule_Type</span></span>](rule_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="85f4d-118">RuleSetFlags</span><span class="sxs-lookup"><span data-stu-id="85f4d-118">RuleSetFlags</span></span>](rulesetflags-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="85f4d-119">RuleSetFlags_Type</span><span class="sxs-lookup"><span data-stu-id="85f4d-119">RuleSetFlags_Type</span></span>](rulesetflags_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="85f4d-120">Attributes</span><span class="sxs-lookup"><span data-stu-id="85f4d-120">Attributes</span></span>

|<span data-ttu-id="85f4d-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="85f4d-121">**Attribute**</span></span>|<span data-ttu-id="85f4d-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="85f4d-122">**Type**</span></span>|<span data-ttu-id="85f4d-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="85f4d-123">**Required**</span></span>|<span data-ttu-id="85f4d-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="85f4d-124">**Description**</span></span>|<span data-ttu-id="85f4d-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="85f4d-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="85f4d-126">说明</span><span class="sxs-lookup"><span data-stu-id="85f4d-126">Description</span></span>  <br/> |<span data-ttu-id="85f4d-127">xsd: string</span><span class="sxs-lookup"><span data-stu-id="85f4d-127">xsd:string</span></span>  <br/> |<span data-ttu-id="85f4d-128">可选</span><span class="sxs-lookup"><span data-stu-id="85f4d-128">optional</span></span>  <br/> ||<span data-ttu-id="85f4d-129">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="85f4d-129">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="85f4d-130">已启用</span><span class="sxs-lookup"><span data-stu-id="85f4d-130">Enabled</span></span>  <br/> |<span data-ttu-id="85f4d-131">化</span><span class="sxs-lookup"><span data-stu-id="85f4d-131">xsd:boolean</span></span>  <br/> |<span data-ttu-id="85f4d-132">可选</span><span class="sxs-lookup"><span data-stu-id="85f4d-132">optional</span></span>  <br/> ||<span data-ttu-id="85f4d-133">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="85f4d-133">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="85f4d-134">ID</span><span class="sxs-lookup"><span data-stu-id="85f4d-134">ID</span></span>  <br/> |<span data-ttu-id="85f4d-135">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="85f4d-135">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="85f4d-136">必需</span><span class="sxs-lookup"><span data-stu-id="85f4d-136">required</span></span>  <br/> ||<span data-ttu-id="85f4d-137">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="85f4d-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="85f4d-138">名称</span><span class="sxs-lookup"><span data-stu-id="85f4d-138">Name</span></span>  <br/> |<span data-ttu-id="85f4d-139">xsd: string</span><span class="sxs-lookup"><span data-stu-id="85f4d-139">xsd:string</span></span>  <br/> |<span data-ttu-id="85f4d-140">可选</span><span class="sxs-lookup"><span data-stu-id="85f4d-140">optional</span></span>  <br/> ||<span data-ttu-id="85f4d-141">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="85f4d-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="85f4d-142">NameU</span><span class="sxs-lookup"><span data-stu-id="85f4d-142">NameU</span></span>  <br/> |<span data-ttu-id="85f4d-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="85f4d-143">xsd:string</span></span>  <br/> |<span data-ttu-id="85f4d-144">必需</span><span class="sxs-lookup"><span data-stu-id="85f4d-144">required</span></span>  <br/> ||<span data-ttu-id="85f4d-145">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="85f4d-145">Values of the xsd:string type.</span></span>  <br/> |
   

