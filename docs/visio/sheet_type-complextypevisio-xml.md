---
title: Sheet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4855350c-8204-ef1f-4d08-4ab6540249e9
ms.openlocfilehash: b747f2257f2b09083b72a17a59856be0a985b270
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540404"
---
# <a name="sheettype-complextype-visio-xml"></a><span data-ttu-id="5e5f2-102">Sheet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="5e5f2-102">Sheet_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="5e5f2-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="5e5f2-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5e5f2-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5e5f2-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="5e5f2-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5e5f2-105">**Schema file**</span></span> <br/> |<span data-ttu-id="5e5f2-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="5e5f2-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="5e5f2-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="5e5f2-107">**Extension base**</span></span> <br/> |<span data-ttu-id="5e5f2-108">无</span><span class="sxs-lookup"><span data-stu-id="5e5f2-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5e5f2-109">定义</span><span class="sxs-lookup"><span data-stu-id="5e5f2-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="5e5f2-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5e5f2-110">Elements and attributes</span></span>

<span data-ttu-id="5e5f2-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="5e5f2-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="5e5f2-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5e5f2-112">Child elements</span></span>

|<span data-ttu-id="5e5f2-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="5e5f2-113">**Element**</span></span>|<span data-ttu-id="5e5f2-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="5e5f2-114">**Type**</span></span>|<span data-ttu-id="5e5f2-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="5e5f2-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5e5f2-116">Cell</span><span class="sxs-lookup"><span data-stu-id="5e5f2-116">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="5e5f2-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="5e5f2-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="5e5f2-118">Section</span><span class="sxs-lookup"><span data-stu-id="5e5f2-118">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5e5f2-119">Section_Type</span><span class="sxs-lookup"><span data-stu-id="5e5f2-119">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="5e5f2-120">Trigger</span><span class="sxs-lookup"><span data-stu-id="5e5f2-120">Trigger</span></span>](trigger-elementvisio-xml.md) <br/> |[<span data-ttu-id="5e5f2-121">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="5e5f2-121">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="5e5f2-122">属性</span><span class="sxs-lookup"><span data-stu-id="5e5f2-122">Attributes</span></span>

|<span data-ttu-id="5e5f2-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="5e5f2-123">**Attribute**</span></span>|<span data-ttu-id="5e5f2-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="5e5f2-124">**Type**</span></span>|<span data-ttu-id="5e5f2-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="5e5f2-125">**Required**</span></span>|<span data-ttu-id="5e5f2-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="5e5f2-126">**Description**</span></span>|<span data-ttu-id="5e5f2-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="5e5f2-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5e5f2-128">FillStyle</span><span class="sxs-lookup"><span data-stu-id="5e5f2-128">FillStyle</span></span>  <br/> |<span data-ttu-id="5e5f2-129">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5e5f2-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5e5f2-130">可选</span><span class="sxs-lookup"><span data-stu-id="5e5f2-130">optional</span></span>  <br/> ||<span data-ttu-id="5e5f2-131">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5e5f2-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5e5f2-132">LineStyle</span><span class="sxs-lookup"><span data-stu-id="5e5f2-132">LineStyle</span></span>  <br/> |<span data-ttu-id="5e5f2-133">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5e5f2-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5e5f2-134">可选</span><span class="sxs-lookup"><span data-stu-id="5e5f2-134">optional</span></span>  <br/> ||<span data-ttu-id="5e5f2-135">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5e5f2-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5e5f2-136">TextStyle</span><span class="sxs-lookup"><span data-stu-id="5e5f2-136">TextStyle</span></span>  <br/> |<span data-ttu-id="5e5f2-137">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5e5f2-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5e5f2-138">可选</span><span class="sxs-lookup"><span data-stu-id="5e5f2-138">optional</span></span>  <br/> ||<span data-ttu-id="5e5f2-139">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5e5f2-139">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

