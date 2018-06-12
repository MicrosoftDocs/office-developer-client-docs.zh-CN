---
title: HeaderFooter_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f5fcf3d9-c11a-ed5e-0bf5-e706259ef30b
ms.openlocfilehash: 9c567542061ec419de9c4347209059b0486bdf88
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780370"
---
# <a name="headerfootertype-complextype-visio-xml"></a><span data-ttu-id="15e1c-102">HeaderFooter_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="15e1c-102">HeaderFooter_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="15e1c-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="15e1c-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="15e1c-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="15e1c-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="15e1c-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="15e1c-105">**Schema file**</span></span> <br/> |<span data-ttu-id="15e1c-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="15e1c-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="15e1c-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="15e1c-107">**Extension base**</span></span> <br/> |<span data-ttu-id="15e1c-108">无</span><span class="sxs-lookup"><span data-stu-id="15e1c-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="15e1c-109">定义</span><span class="sxs-lookup"><span data-stu-id="15e1c-109">Definition</span></span>

```XML
          <xs:complexType name="HeaderFooter_Type">
          
          <xs:all>
    <xs:element name="HeaderMargin"  type="HeaderMargin_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="FooterMargin"  type="FooterMargin_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="HeaderLeft"  type="HeaderLeft_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="HeaderCenter"  type="HeaderCenter_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="HeaderRight"  type="HeaderRight_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="FooterLeft"  type="FooterLeft_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="FooterCenter"  type="FooterCenter_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="FooterRight"  type="FooterRight_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="HeaderFooterFont"  type="HeaderFooterFont_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:all>
    <xs:attribute name="HeaderFooterColor"
  type="xsd:string"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="15e1c-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="15e1c-110">Elements and attributes</span></span>

<span data-ttu-id="15e1c-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="15e1c-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="15e1c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="15e1c-112">Child elements</span></span>

|<span data-ttu-id="15e1c-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="15e1c-113">**Element**</span></span>|<span data-ttu-id="15e1c-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="15e1c-114">**Type**</span></span>|<span data-ttu-id="15e1c-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="15e1c-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="15e1c-116">FooterCenter</span><span class="sxs-lookup"><span data-stu-id="15e1c-116">FooterCenter</span></span>](footercenter-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="15e1c-117">FooterCenter_Type</span><span class="sxs-lookup"><span data-stu-id="15e1c-117">FooterCenter_Type</span></span>](footercenter_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="15e1c-118">FooterLeft</span><span class="sxs-lookup"><span data-stu-id="15e1c-118">FooterLeft</span></span>](footerleft-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="15e1c-119">FooterLeft_Type</span><span class="sxs-lookup"><span data-stu-id="15e1c-119">FooterLeft_Type</span></span>](footerleft_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="15e1c-120">FooterMargin</span><span class="sxs-lookup"><span data-stu-id="15e1c-120">FooterMargin</span></span>](footermargin-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="15e1c-121">FooterMargin_Type</span><span class="sxs-lookup"><span data-stu-id="15e1c-121">FooterMargin_Type</span></span>](footermargin_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="15e1c-122">FooterRight</span><span class="sxs-lookup"><span data-stu-id="15e1c-122">FooterRight</span></span>](footerright-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="15e1c-123">FooterRight_Type</span><span class="sxs-lookup"><span data-stu-id="15e1c-123">FooterRight_Type</span></span>](footerright_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="15e1c-124">HeaderCenter</span><span class="sxs-lookup"><span data-stu-id="15e1c-124">HeaderCenter</span></span>](headercenter-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="15e1c-125">HeaderCenter_Type</span><span class="sxs-lookup"><span data-stu-id="15e1c-125">HeaderCenter_Type</span></span>](headercenter_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="15e1c-126">HeaderFooterFont</span><span class="sxs-lookup"><span data-stu-id="15e1c-126">HeaderFooterFont</span></span>](headerfooterfont-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="15e1c-127">HeaderFooterFont_Type</span><span class="sxs-lookup"><span data-stu-id="15e1c-127">HeaderFooterFont_Type</span></span>](headerfooterfont_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="15e1c-128">HeaderLeft</span><span class="sxs-lookup"><span data-stu-id="15e1c-128">HeaderLeft</span></span>](headerleft-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="15e1c-129">HeaderLeft_Type</span><span class="sxs-lookup"><span data-stu-id="15e1c-129">HeaderLeft_Type</span></span>](headerleft_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="15e1c-130">HeaderMargin</span><span class="sxs-lookup"><span data-stu-id="15e1c-130">HeaderMargin</span></span>](headermargin-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="15e1c-131">HeaderMargin_Type</span><span class="sxs-lookup"><span data-stu-id="15e1c-131">HeaderMargin_Type</span></span>](headermargin_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="15e1c-132">HeaderRight</span><span class="sxs-lookup"><span data-stu-id="15e1c-132">HeaderRight</span></span>](headerright-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="15e1c-133">HeaderRight_Type</span><span class="sxs-lookup"><span data-stu-id="15e1c-133">HeaderRight_Type</span></span>](headerright_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="15e1c-134">属性</span><span class="sxs-lookup"><span data-stu-id="15e1c-134">Attributes</span></span>

|<span data-ttu-id="15e1c-135">**属性**</span><span class="sxs-lookup"><span data-stu-id="15e1c-135">**Attribute**</span></span>|<span data-ttu-id="15e1c-136">**类型**</span><span class="sxs-lookup"><span data-stu-id="15e1c-136">**Type**</span></span>|<span data-ttu-id="15e1c-137">**必需**</span><span class="sxs-lookup"><span data-stu-id="15e1c-137">**Required**</span></span>|<span data-ttu-id="15e1c-138">**说明**</span><span class="sxs-lookup"><span data-stu-id="15e1c-138">**Description**</span></span>|<span data-ttu-id="15e1c-139">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="15e1c-139">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="15e1c-140">HeaderFooterColor</span><span class="sxs-lookup"><span data-stu-id="15e1c-140">HeaderFooterColor</span></span>  <br/> |<span data-ttu-id="15e1c-141">xsd: string</span><span class="sxs-lookup"><span data-stu-id="15e1c-141">xsd:string</span></span>  <br/> |<span data-ttu-id="15e1c-142">可选</span><span class="sxs-lookup"><span data-stu-id="15e1c-142">optional</span></span>  <br/> ||<span data-ttu-id="15e1c-143">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="15e1c-143">Values of the xsd:string type.</span></span>  <br/> |
   

