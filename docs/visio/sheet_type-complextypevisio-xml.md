---
title: Sheet_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4855350c-8204-ef1f-4d08-4ab6540249e9
ms.openlocfilehash: dc8930ffa89baf059074a12bb285e6b53e329e41
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342866"
---
# <a name="sheettype-complextype-visio-xml"></a><span data-ttu-id="673d9-102">Sheet_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="673d9-102">Sheet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="673d9-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="673d9-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="673d9-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="673d9-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="673d9-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="673d9-105">**Schema file**</span></span> <br/> |<span data-ttu-id="673d9-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="673d9-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="673d9-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="673d9-107">**Extension base**</span></span> <br/> |<span data-ttu-id="673d9-108">无</span><span class="sxs-lookup"><span data-stu-id="673d9-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="673d9-109">定义</span><span class="sxs-lookup"><span data-stu-id="673d9-109">Definition</span></span>

```XML
        <xs:complexType name="Sheet_Type" abstract="true">
        
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
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
    
    <xs:element name="Section"  type="Section_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs: name="" >
    </xs:>
    
      </xs:sequence>
    <xs:attribute name="LineStyle"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="FillStyle"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="TextStyle"
  type="xsd:unsignedInt"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="673d9-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="673d9-110">Elements and attributes</span></span>

<span data-ttu-id="673d9-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="673d9-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="673d9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="673d9-112">Child elements</span></span>

|<span data-ttu-id="673d9-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="673d9-113">**Element**</span></span>|<span data-ttu-id="673d9-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="673d9-114">**Type**</span></span>|<span data-ttu-id="673d9-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="673d9-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="673d9-116">Cell</span><span class="sxs-lookup"><span data-stu-id="673d9-116">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="673d9-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="673d9-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="673d9-118">Section</span><span class="sxs-lookup"><span data-stu-id="673d9-118">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="673d9-119">Section_Type</span><span class="sxs-lookup"><span data-stu-id="673d9-119">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="673d9-120">Trigger</span><span class="sxs-lookup"><span data-stu-id="673d9-120">Trigger</span></span>](trigger-elementvisio-xml.md) <br/> |[<span data-ttu-id="673d9-121">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="673d9-121">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="673d9-122">属性</span><span class="sxs-lookup"><span data-stu-id="673d9-122">Attributes</span></span>

|<span data-ttu-id="673d9-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="673d9-123">**Attribute**</span></span>|<span data-ttu-id="673d9-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="673d9-124">**Type**</span></span>|<span data-ttu-id="673d9-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="673d9-125">**Required**</span></span>|<span data-ttu-id="673d9-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="673d9-126">**Description**</span></span>|<span data-ttu-id="673d9-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="673d9-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="673d9-128">FillStyle</span><span class="sxs-lookup"><span data-stu-id="673d9-128">FillStyle</span></span>  <br/> |<span data-ttu-id="673d9-129">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="673d9-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="673d9-130">可选</span><span class="sxs-lookup"><span data-stu-id="673d9-130">optional</span></span>  <br/> ||<span data-ttu-id="673d9-131">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="673d9-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="673d9-132">LineStyle</span><span class="sxs-lookup"><span data-stu-id="673d9-132">LineStyle</span></span>  <br/> |<span data-ttu-id="673d9-133">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="673d9-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="673d9-134">可选</span><span class="sxs-lookup"><span data-stu-id="673d9-134">optional</span></span>  <br/> ||<span data-ttu-id="673d9-135">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="673d9-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="673d9-136">TextStyle</span><span class="sxs-lookup"><span data-stu-id="673d9-136">TextStyle</span></span>  <br/> |<span data-ttu-id="673d9-137">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="673d9-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="673d9-138">可选</span><span class="sxs-lookup"><span data-stu-id="673d9-138">optional</span></span>  <br/> ||<span data-ttu-id="673d9-139">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="673d9-139">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

