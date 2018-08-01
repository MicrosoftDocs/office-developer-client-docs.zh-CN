---
title: Section_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f8e855f-064c-d286-560f-9f89e7fce7b7
ms.openlocfilehash: 8eb9362f84849ad22a20662b327ae33cd795cc5a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781225"
---
# <a name="sectiontype-complextype-visio-xml"></a><span data-ttu-id="759a4-102">Section_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="759a4-102">Section_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="759a4-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="759a4-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="759a4-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="759a4-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="759a4-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="759a4-105">**Schema file**</span></span> <br/> |<span data-ttu-id="759a4-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="759a4-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="759a4-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="759a4-107">**Extension base**</span></span> <br/> |<span data-ttu-id="759a4-108">无</span><span class="sxs-lookup"><span data-stu-id="759a4-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="759a4-109">定义</span><span class="sxs-lookup"><span data-stu-id="759a4-109">Definition</span></span>

```XML
          <xs:complexType name="Section_Type">
          
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
    
    <xs:element name="Row"  type="Row_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="N"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="Del"
  type="xsd:boolean"
    />
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="759a4-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="759a4-110">Elements and attributes</span></span>

<span data-ttu-id="759a4-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="759a4-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="759a4-112">子元素</span><span class="sxs-lookup"><span data-stu-id="759a4-112">Child elements</span></span>

|<span data-ttu-id="759a4-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="759a4-113">**Element**</span></span>|<span data-ttu-id="759a4-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="759a4-114">**Type**</span></span>|<span data-ttu-id="759a4-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="759a4-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="759a4-116">Cell</span><span class="sxs-lookup"><span data-stu-id="759a4-116">Cell</span></span>](http://msdn.microsoft.com/library/70a9d6d6-a4ff-2b0d-febc-789a04a2f5b0%28Office.15%29.aspx) <br/> |[<span data-ttu-id="759a4-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="759a4-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="759a4-118">Row</span><span class="sxs-lookup"><span data-stu-id="759a4-118">Row</span></span>](http://msdn.microsoft.com/library/c978e3eb-b895-8fb7-e2ba-88c50e57b3db%28Office.15%29.aspx) <br/> |[<span data-ttu-id="759a4-119">Row_Type</span><span class="sxs-lookup"><span data-stu-id="759a4-119">Row_Type</span></span>](row_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="759a4-120">Trigger</span><span class="sxs-lookup"><span data-stu-id="759a4-120">Trigger</span></span>](http://msdn.microsoft.com/library/e4eeb238-f6d0-fb23-db1c-01d55b0a8d88%28Office.15%29.aspx) <br/> |[<span data-ttu-id="759a4-121">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="759a4-121">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="759a4-122">Attributes</span><span class="sxs-lookup"><span data-stu-id="759a4-122">Attributes</span></span>

|<span data-ttu-id="759a4-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="759a4-123">**Attribute**</span></span>|<span data-ttu-id="759a4-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="759a4-124">**Type**</span></span>|<span data-ttu-id="759a4-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="759a4-125">**Required**</span></span>|<span data-ttu-id="759a4-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="759a4-126">**Description**</span></span>|<span data-ttu-id="759a4-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="759a4-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="759a4-128">Del</span><span class="sxs-lookup"><span data-stu-id="759a4-128">Del</span></span>  <br/> |<span data-ttu-id="759a4-129">化</span><span class="sxs-lookup"><span data-stu-id="759a4-129">xsd:boolean</span></span>  <br/> |<span data-ttu-id="759a4-130">可选</span><span class="sxs-lookup"><span data-stu-id="759a4-130">optional</span></span>  <br/> ||<span data-ttu-id="759a4-131">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="759a4-131">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="759a4-132">IX</span><span class="sxs-lookup"><span data-stu-id="759a4-132">IX</span></span>  <br/> |<span data-ttu-id="759a4-133">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="759a4-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="759a4-134">可选</span><span class="sxs-lookup"><span data-stu-id="759a4-134">optional</span></span>  <br/> ||<span data-ttu-id="759a4-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="759a4-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="759a4-136">N</span><span class="sxs-lookup"><span data-stu-id="759a4-136">N</span></span>  <br/> |<span data-ttu-id="759a4-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="759a4-137">xsd:string</span></span>  <br/> |<span data-ttu-id="759a4-138">必需</span><span class="sxs-lookup"><span data-stu-id="759a4-138">required</span></span>  <br/> ||<span data-ttu-id="759a4-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="759a4-139">Values of the xsd:string type.</span></span>  <br/> |
   

