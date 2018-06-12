---
title: Sheet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4855350c-8204-ef1f-4d08-4ab6540249e9
ms.openlocfilehash: f171f250fbe37ebf1d0d434709b06ab56804407f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781328"
---
# <a name="sheettype-complextype-visio-xml"></a><span data-ttu-id="fa708-102">Sheet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="fa708-102">Sheet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="fa708-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="fa708-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fa708-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="fa708-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="fa708-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="fa708-105">**Schema file**</span></span> <br/> |<span data-ttu-id="fa708-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="fa708-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="fa708-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="fa708-107">**Extension base**</span></span> <br/> |<span data-ttu-id="fa708-108">无</span><span class="sxs-lookup"><span data-stu-id="fa708-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="fa708-109">定义</span><span class="sxs-lookup"><span data-stu-id="fa708-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="fa708-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="fa708-110">Elements and attributes</span></span>

<span data-ttu-id="fa708-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="fa708-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="fa708-112">子元素</span><span class="sxs-lookup"><span data-stu-id="fa708-112">Child elements</span></span>

|<span data-ttu-id="fa708-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="fa708-113">**Element**</span></span>|<span data-ttu-id="fa708-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="fa708-114">**Type**</span></span>|<span data-ttu-id="fa708-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="fa708-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fa708-116">Cell</span><span class="sxs-lookup"><span data-stu-id="fa708-116">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="fa708-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="fa708-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="fa708-118">节</span><span class="sxs-lookup"><span data-stu-id="fa708-118">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fa708-119">Section_Type</span><span class="sxs-lookup"><span data-stu-id="fa708-119">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="fa708-120">Trigger</span><span class="sxs-lookup"><span data-stu-id="fa708-120">Trigger</span></span>](trigger-elementvisio-xml.md) <br/> |[<span data-ttu-id="fa708-121">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="fa708-121">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="fa708-122">属性</span><span class="sxs-lookup"><span data-stu-id="fa708-122">Attributes</span></span>

|<span data-ttu-id="fa708-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="fa708-123">**Attribute**</span></span>|<span data-ttu-id="fa708-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="fa708-124">**Type**</span></span>|<span data-ttu-id="fa708-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="fa708-125">**Required**</span></span>|<span data-ttu-id="fa708-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="fa708-126">**Description**</span></span>|<span data-ttu-id="fa708-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="fa708-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fa708-128">FillStyle</span><span class="sxs-lookup"><span data-stu-id="fa708-128">FillStyle</span></span>  <br/> |<span data-ttu-id="fa708-129">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="fa708-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="fa708-130">可选</span><span class="sxs-lookup"><span data-stu-id="fa708-130">optional</span></span>  <br/> ||<span data-ttu-id="fa708-131">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fa708-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="fa708-132">LineStyle</span><span class="sxs-lookup"><span data-stu-id="fa708-132">LineStyle</span></span>  <br/> |<span data-ttu-id="fa708-133">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="fa708-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="fa708-134">可选</span><span class="sxs-lookup"><span data-stu-id="fa708-134">optional</span></span>  <br/> ||<span data-ttu-id="fa708-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fa708-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="fa708-136">TextStyle</span><span class="sxs-lookup"><span data-stu-id="fa708-136">TextStyle</span></span>  <br/> |<span data-ttu-id="fa708-137">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="fa708-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="fa708-138">可选</span><span class="sxs-lookup"><span data-stu-id="fa708-138">optional</span></span>  <br/> ||<span data-ttu-id="fa708-139">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fa708-139">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

