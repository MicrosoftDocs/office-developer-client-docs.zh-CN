---
title: HeaderFooter_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f5fcf3d9-c11a-ed5e-0bf5-e706259ef30b
ms.openlocfilehash: 581101909096d4ee8a4f44c8e9e95dab0313ed7c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342236"
---
# <a name="headerfootertype-complextype-visio-xml"></a><span data-ttu-id="527da-102">HeaderFooter_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="527da-102">HeaderFooter_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="527da-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="527da-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="527da-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="527da-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="527da-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="527da-105">**Schema file**</span></span> <br/> |<span data-ttu-id="527da-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="527da-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="527da-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="527da-107">**Extension base**</span></span> <br/> |<span data-ttu-id="527da-108">无</span><span class="sxs-lookup"><span data-stu-id="527da-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="527da-109">定义</span><span class="sxs-lookup"><span data-stu-id="527da-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="527da-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="527da-110">Elements and attributes</span></span>

<span data-ttu-id="527da-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="527da-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="527da-112">子元素</span><span class="sxs-lookup"><span data-stu-id="527da-112">Child elements</span></span>

|<span data-ttu-id="527da-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="527da-113">**Element**</span></span>|<span data-ttu-id="527da-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="527da-114">**Type**</span></span>|<span data-ttu-id="527da-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="527da-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="527da-116">FooterCenter</span><span class="sxs-lookup"><span data-stu-id="527da-116">FooterCenter</span></span>](footercenter-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="527da-117">FooterCenter_Type</span><span class="sxs-lookup"><span data-stu-id="527da-117">FooterCenter_Type</span></span>](footercenter_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="527da-118">FooterLeft</span><span class="sxs-lookup"><span data-stu-id="527da-118">FooterLeft</span></span>](footerleft-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="527da-119">FooterLeft_Type</span><span class="sxs-lookup"><span data-stu-id="527da-119">FooterLeft_Type</span></span>](footerleft_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="527da-120">FooterMargin</span><span class="sxs-lookup"><span data-stu-id="527da-120">FooterMargin</span></span>](footermargin-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="527da-121">FooterMargin_Type</span><span class="sxs-lookup"><span data-stu-id="527da-121">FooterMargin_Type</span></span>](footermargin_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="527da-122">FooterRight</span><span class="sxs-lookup"><span data-stu-id="527da-122">FooterRight</span></span>](footerright-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="527da-123">FooterRight_Type</span><span class="sxs-lookup"><span data-stu-id="527da-123">FooterRight_Type</span></span>](footerright_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="527da-124">HeaderCenter</span><span class="sxs-lookup"><span data-stu-id="527da-124">HeaderCenter</span></span>](headercenter-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="527da-125">HeaderCenter_Type</span><span class="sxs-lookup"><span data-stu-id="527da-125">HeaderCenter_Type</span></span>](headercenter_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="527da-126">HeaderFooterFont</span><span class="sxs-lookup"><span data-stu-id="527da-126">HeaderFooterFont</span></span>](headerfooterfont-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="527da-127">HeaderFooterFont_Type</span><span class="sxs-lookup"><span data-stu-id="527da-127">HeaderFooterFont_Type</span></span>](headerfooterfont_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="527da-128">HeaderLeft</span><span class="sxs-lookup"><span data-stu-id="527da-128">HeaderLeft</span></span>](headerleft-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="527da-129">HeaderLeft_Type</span><span class="sxs-lookup"><span data-stu-id="527da-129">HeaderLeft_Type</span></span>](headerleft_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="527da-130">HeaderMargin</span><span class="sxs-lookup"><span data-stu-id="527da-130">HeaderMargin</span></span>](headermargin-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="527da-131">HeaderMargin_Type</span><span class="sxs-lookup"><span data-stu-id="527da-131">HeaderMargin_Type</span></span>](headermargin_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="527da-132">HeaderRight</span><span class="sxs-lookup"><span data-stu-id="527da-132">HeaderRight</span></span>](headerright-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="527da-133">HeaderRight_Type</span><span class="sxs-lookup"><span data-stu-id="527da-133">HeaderRight_Type</span></span>](headerright_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="527da-134">属性</span><span class="sxs-lookup"><span data-stu-id="527da-134">Attributes</span></span>

|<span data-ttu-id="527da-135">**属性**</span><span class="sxs-lookup"><span data-stu-id="527da-135">**Attribute**</span></span>|<span data-ttu-id="527da-136">**类型**</span><span class="sxs-lookup"><span data-stu-id="527da-136">**Type**</span></span>|<span data-ttu-id="527da-137">**必需**</span><span class="sxs-lookup"><span data-stu-id="527da-137">**Required**</span></span>|<span data-ttu-id="527da-138">**描述**</span><span class="sxs-lookup"><span data-stu-id="527da-138">**Description**</span></span>|<span data-ttu-id="527da-139">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="527da-139">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="527da-140">HeaderFooterColor</span><span class="sxs-lookup"><span data-stu-id="527da-140">HeaderFooterColor</span></span>  <br/> |<span data-ttu-id="527da-141">xsd: string</span><span class="sxs-lookup"><span data-stu-id="527da-141">xsd:string</span></span>  <br/> |<span data-ttu-id="527da-142">可选</span><span class="sxs-lookup"><span data-stu-id="527da-142">optional</span></span>  <br/> ||<span data-ttu-id="527da-143">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="527da-143">Values of the xsd:string type.</span></span>  <br/> |
   

