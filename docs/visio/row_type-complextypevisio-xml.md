---
title: Row_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5e5c420e-f384-7b62-c862-35aea16e6d55
ms.openlocfilehash: dfa3a90aaec51ba89845934c1d4fad484914afa7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781172"
---
# <a name="rowtype-complextype-visio-xml"></a><span data-ttu-id="6a6b6-102">Row_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="6a6b6-102">Row_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="6a6b6-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="6a6b6-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6a6b6-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6a6b6-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="6a6b6-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6a6b6-105">**Schema file**</span></span> <br/> |<span data-ttu-id="6a6b6-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="6a6b6-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="6a6b6-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="6a6b6-107">**Extension base**</span></span> <br/> |<span data-ttu-id="6a6b6-108">无</span><span class="sxs-lookup"><span data-stu-id="6a6b6-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6a6b6-109">定义</span><span class="sxs-lookup"><span data-stu-id="6a6b6-109">Definition</span></span>

```XML
          <xs:complexType name="Row_Type">
          
          <xs:sequence>
    <xs:element name="Cell"  type="Cell_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="Trigger"  type="Trigger_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="N"
  type="xsd:string"
    />
    <xs:attribute name="LocalName"
  type="xsd:string"
    />
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="T"
  type="xsd:string"
    />
    <xs:attribute name="Del"
  type="xsd:boolean"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="6a6b6-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6a6b6-110">Elements and attributes</span></span>

<span data-ttu-id="6a6b6-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="6a6b6-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="6a6b6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="6a6b6-112">Child elements</span></span>

|<span data-ttu-id="6a6b6-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="6a6b6-113">**Element**</span></span>|<span data-ttu-id="6a6b6-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="6a6b6-114">**Type**</span></span>|<span data-ttu-id="6a6b6-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="6a6b6-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6a6b6-116">Cell</span><span class="sxs-lookup"><span data-stu-id="6a6b6-116">Cell</span></span>](http://msdn.microsoft.com/library/5e060a3f-e804-834f-531b-78a544fee61f%28Office.15%29.aspx) <br/> |[<span data-ttu-id="6a6b6-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="6a6b6-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="6a6b6-118">Trigger</span><span class="sxs-lookup"><span data-stu-id="6a6b6-118">Trigger</span></span>](http://msdn.microsoft.com/library/6dbd2c66-3b29-03f6-648f-723d359ded0d%28Office.15%29.aspx) <br/> |[<span data-ttu-id="6a6b6-119">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="6a6b6-119">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="6a6b6-120">属性</span><span class="sxs-lookup"><span data-stu-id="6a6b6-120">Attributes</span></span>

|<span data-ttu-id="6a6b6-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="6a6b6-121">**Attribute**</span></span>|<span data-ttu-id="6a6b6-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="6a6b6-122">**Type**</span></span>|<span data-ttu-id="6a6b6-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="6a6b6-123">**Required**</span></span>|<span data-ttu-id="6a6b6-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="6a6b6-124">**Description**</span></span>|<span data-ttu-id="6a6b6-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="6a6b6-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6a6b6-126">Del</span><span class="sxs-lookup"><span data-stu-id="6a6b6-126">Del</span></span>  <br/> |<span data-ttu-id="6a6b6-127">化</span><span class="sxs-lookup"><span data-stu-id="6a6b6-127">xsd:boolean</span></span>  <br/> |<span data-ttu-id="6a6b6-128">可选</span><span class="sxs-lookup"><span data-stu-id="6a6b6-128">optional</span></span>  <br/> ||<span data-ttu-id="6a6b6-129">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="6a6b6-129">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="6a6b6-130">IX</span><span class="sxs-lookup"><span data-stu-id="6a6b6-130">IX</span></span>  <br/> |<span data-ttu-id="6a6b6-131">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="6a6b6-131">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="6a6b6-132">可选</span><span class="sxs-lookup"><span data-stu-id="6a6b6-132">optional</span></span>  <br/> ||<span data-ttu-id="6a6b6-133">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6a6b6-133">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="6a6b6-134">LocalName</span><span class="sxs-lookup"><span data-stu-id="6a6b6-134">LocalName</span></span>  <br/> |<span data-ttu-id="6a6b6-135">xsd: string</span><span class="sxs-lookup"><span data-stu-id="6a6b6-135">xsd:string</span></span>  <br/> |<span data-ttu-id="6a6b6-136">可选</span><span class="sxs-lookup"><span data-stu-id="6a6b6-136">optional</span></span>  <br/> ||<span data-ttu-id="6a6b6-137">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6a6b6-137">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="6a6b6-138">N</span><span class="sxs-lookup"><span data-stu-id="6a6b6-138">N</span></span>  <br/> |<span data-ttu-id="6a6b6-139">xsd: string</span><span class="sxs-lookup"><span data-stu-id="6a6b6-139">xsd:string</span></span>  <br/> |<span data-ttu-id="6a6b6-140">可选</span><span class="sxs-lookup"><span data-stu-id="6a6b6-140">optional</span></span>  <br/> ||<span data-ttu-id="6a6b6-141">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6a6b6-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="6a6b6-142">T</span><span class="sxs-lookup"><span data-stu-id="6a6b6-142">T</span></span>  <br/> |<span data-ttu-id="6a6b6-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="6a6b6-143">xsd:string</span></span>  <br/> |<span data-ttu-id="6a6b6-144">可选</span><span class="sxs-lookup"><span data-stu-id="6a6b6-144">optional</span></span>  <br/> ||<span data-ttu-id="6a6b6-145">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6a6b6-145">Values of the xsd:string type.</span></span>  <br/> |
   

