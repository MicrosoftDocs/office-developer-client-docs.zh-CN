---
title: SectionDef_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ab57bf2-0d9f-4a3a-4882-c77d7c781cbd
ms.openlocfilehash: 1d13cf54861435aea2ce0b3aade955575d538891
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395075"
---
# <a name="sectiondeftype-complextype-visio-xml"></a><span data-ttu-id="4d7aa-102">SectionDef_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="4d7aa-102">SectionDef_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="4d7aa-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="4d7aa-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4d7aa-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="4d7aa-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-105">**Schema file**</span></span> <br/> |<span data-ttu-id="4d7aa-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="4d7aa-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="4d7aa-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-107">**Extension base**</span></span> <br/> |<span data-ttu-id="4d7aa-108">无</span><span class="sxs-lookup"><span data-stu-id="4d7aa-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4d7aa-109">定义</span><span class="sxs-lookup"><span data-stu-id="4d7aa-109">Definition</span></span>

```XML
          <xs:complexType name="SectionDef_Type">
          
          <xs:sequence>
    <xs:element name="CellDef"  type="CellDef_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="RowDef"  type="RowDef_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="N"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="T"
  type="xsd:string"
    />
    <xs:attribute name="S"
  type="xsd:unsignedByte"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4d7aa-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4d7aa-110">Elements and attributes</span></span>

<span data-ttu-id="4d7aa-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4d7aa-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="4d7aa-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4d7aa-112">Child elements</span></span>

|<span data-ttu-id="4d7aa-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-113">**Element**</span></span>|<span data-ttu-id="4d7aa-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-114">**Type**</span></span>|<span data-ttu-id="4d7aa-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4d7aa-116">CellDef</span><span class="sxs-lookup"><span data-stu-id="4d7aa-116">CellDef</span></span> <br/> |[<span data-ttu-id="4d7aa-117">CellDef_Type</span><span class="sxs-lookup"><span data-stu-id="4d7aa-117">CellDef_Type</span></span>](celldef_type-complextypevisio-xml.md) <br/> ||
|<span data-ttu-id="4d7aa-118">RowDef</span><span class="sxs-lookup"><span data-stu-id="4d7aa-118">RowDef</span></span> <br/> |[<span data-ttu-id="4d7aa-119">RowDef_Type</span><span class="sxs-lookup"><span data-stu-id="4d7aa-119">RowDef_Type</span></span>](rowdef_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="4d7aa-120">Attributes</span><span class="sxs-lookup"><span data-stu-id="4d7aa-120">Attributes</span></span>

|<span data-ttu-id="4d7aa-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-121">**Attribute**</span></span>|<span data-ttu-id="4d7aa-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-122">**Type**</span></span>|<span data-ttu-id="4d7aa-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-123">**Required**</span></span>|<span data-ttu-id="4d7aa-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-124">**Description**</span></span>|<span data-ttu-id="4d7aa-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4d7aa-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d7aa-126">N</span><span class="sxs-lookup"><span data-stu-id="4d7aa-126">N</span></span>  <br/> |<span data-ttu-id="4d7aa-127">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4d7aa-127">xsd:string</span></span>  <br/> |<span data-ttu-id="4d7aa-128">必需</span><span class="sxs-lookup"><span data-stu-id="4d7aa-128">required</span></span>  <br/> ||<span data-ttu-id="4d7aa-129">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4d7aa-129">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="4d7aa-130">S</span><span class="sxs-lookup"><span data-stu-id="4d7aa-130">S</span></span>  <br/> |<span data-ttu-id="4d7aa-131">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="4d7aa-131">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="4d7aa-132">可选</span><span class="sxs-lookup"><span data-stu-id="4d7aa-132">optional</span></span>  <br/> ||<span data-ttu-id="4d7aa-133">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4d7aa-133">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="4d7aa-134">T</span><span class="sxs-lookup"><span data-stu-id="4d7aa-134">T</span></span>  <br/> |<span data-ttu-id="4d7aa-135">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4d7aa-135">xsd:string</span></span>  <br/> |<span data-ttu-id="4d7aa-136">可选</span><span class="sxs-lookup"><span data-stu-id="4d7aa-136">optional</span></span>  <br/> ||<span data-ttu-id="4d7aa-137">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4d7aa-137">Values of the xsd:string type.</span></span>  <br/> |
   

