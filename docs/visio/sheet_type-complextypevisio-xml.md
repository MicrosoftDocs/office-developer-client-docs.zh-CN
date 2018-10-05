---
title: Sheet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4855350c-8204-ef1f-4d08-4ab6540249e9
ms.openlocfilehash: dc8930ffa89baf059074a12bb285e6b53e329e41
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388747"
---
# <a name="sheettype-complextype-visio-xml"></a><span data-ttu-id="83fdf-102">Sheet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="83fdf-102">Sheet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="83fdf-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="83fdf-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="83fdf-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="83fdf-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="83fdf-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="83fdf-105">**Schema file**</span></span> <br/> |<span data-ttu-id="83fdf-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="83fdf-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="83fdf-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="83fdf-107">**Extension base**</span></span> <br/> |<span data-ttu-id="83fdf-108">无</span><span class="sxs-lookup"><span data-stu-id="83fdf-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="83fdf-109">定义</span><span class="sxs-lookup"><span data-stu-id="83fdf-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="83fdf-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="83fdf-110">Elements and attributes</span></span>

<span data-ttu-id="83fdf-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="83fdf-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="83fdf-112">子元素</span><span class="sxs-lookup"><span data-stu-id="83fdf-112">Child elements</span></span>

|<span data-ttu-id="83fdf-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="83fdf-113">**Element**</span></span>|<span data-ttu-id="83fdf-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="83fdf-114">**Type**</span></span>|<span data-ttu-id="83fdf-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="83fdf-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="83fdf-116">Cell</span><span class="sxs-lookup"><span data-stu-id="83fdf-116">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="83fdf-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="83fdf-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="83fdf-118">Section</span><span class="sxs-lookup"><span data-stu-id="83fdf-118">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="83fdf-119">Section_Type</span><span class="sxs-lookup"><span data-stu-id="83fdf-119">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="83fdf-120">Trigger</span><span class="sxs-lookup"><span data-stu-id="83fdf-120">Trigger</span></span>](trigger-elementvisio-xml.md) <br/> |[<span data-ttu-id="83fdf-121">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="83fdf-121">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="83fdf-122">Attributes</span><span class="sxs-lookup"><span data-stu-id="83fdf-122">Attributes</span></span>

|<span data-ttu-id="83fdf-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="83fdf-123">**Attribute**</span></span>|<span data-ttu-id="83fdf-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="83fdf-124">**Type**</span></span>|<span data-ttu-id="83fdf-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="83fdf-125">**Required**</span></span>|<span data-ttu-id="83fdf-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="83fdf-126">**Description**</span></span>|<span data-ttu-id="83fdf-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="83fdf-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="83fdf-128">FillStyle</span><span class="sxs-lookup"><span data-stu-id="83fdf-128">FillStyle</span></span>  <br/> |<span data-ttu-id="83fdf-129">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="83fdf-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="83fdf-130">可选</span><span class="sxs-lookup"><span data-stu-id="83fdf-130">optional</span></span>  <br/> ||<span data-ttu-id="83fdf-131">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="83fdf-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="83fdf-132">LineStyle</span><span class="sxs-lookup"><span data-stu-id="83fdf-132">LineStyle</span></span>  <br/> |<span data-ttu-id="83fdf-133">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="83fdf-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="83fdf-134">可选</span><span class="sxs-lookup"><span data-stu-id="83fdf-134">optional</span></span>  <br/> ||<span data-ttu-id="83fdf-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="83fdf-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="83fdf-136">TextStyle</span><span class="sxs-lookup"><span data-stu-id="83fdf-136">TextStyle</span></span>  <br/> |<span data-ttu-id="83fdf-137">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="83fdf-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="83fdf-138">可选</span><span class="sxs-lookup"><span data-stu-id="83fdf-138">optional</span></span>  <br/> ||<span data-ttu-id="83fdf-139">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="83fdf-139">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

