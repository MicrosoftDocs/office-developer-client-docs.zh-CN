---
title: FooterMargin 元素 （HeaderFooter_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 047f42cf-4202-50bd-40b4-a71052e2dfb3
description: 指定文档的页脚的边距。
ms.openlocfilehash: f0c2b8ab1cc7bd1465af3281dfb51766ecba5d8c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401417"
---
# <a name="footermargin-element-headerfootertype-complextype-visio-xml"></a><span data-ttu-id="9e71c-103">FooterMargin 元素 （HeaderFooter_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="9e71c-103">FooterMargin element (HeaderFooter_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="9e71c-104">指定文档的页脚的边距。</span><span class="sxs-lookup"><span data-stu-id="9e71c-104">Specifies the margin of a document's footer.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="9e71c-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="9e71c-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9e71c-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="9e71c-106">**Element type**</span></span> <br/> |[<span data-ttu-id="9e71c-107">FooterMargin_Type</span><span class="sxs-lookup"><span data-stu-id="9e71c-107">FooterMargin_Type</span></span>](footermargin_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="9e71c-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9e71c-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="9e71c-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9e71c-109">**Schema file**</span></span> <br/> |<span data-ttu-id="9e71c-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="9e71c-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="9e71c-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="9e71c-111">**Document parts**</span></span> <br/> |<span data-ttu-id="9e71c-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="9e71c-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9e71c-113">定义</span><span class="sxs-lookup"><span data-stu-id="9e71c-113">Definition</span></span>

```XML
< xs:element name="FooterMargin" type="FooterMargin_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="9e71c-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9e71c-114">Elements and attributes</span></span>

<span data-ttu-id="9e71c-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="9e71c-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="9e71c-116">父元素</span><span class="sxs-lookup"><span data-stu-id="9e71c-116">Parent elements</span></span>

|<span data-ttu-id="9e71c-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="9e71c-117">**Element**</span></span>|<span data-ttu-id="9e71c-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="9e71c-118">**Type**</span></span>|<span data-ttu-id="9e71c-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e71c-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9e71c-120">HeaderFooter</span><span class="sxs-lookup"><span data-stu-id="9e71c-120">HeaderFooter</span></span>](headerfooter-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e71c-121">HeaderFooter_Type</span><span class="sxs-lookup"><span data-stu-id="9e71c-121">HeaderFooter_Type</span></span>](headerfooter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9e71c-122">包含文档的页眉和页脚的元素。</span><span class="sxs-lookup"><span data-stu-id="9e71c-122">Contains elements for a document's header and footer.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="9e71c-123">子元素</span><span class="sxs-lookup"><span data-stu-id="9e71c-123">Child elements</span></span>

<span data-ttu-id="9e71c-124">无。</span><span class="sxs-lookup"><span data-stu-id="9e71c-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="9e71c-125">属性</span><span class="sxs-lookup"><span data-stu-id="9e71c-125">Attributes</span></span>

|<span data-ttu-id="9e71c-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="9e71c-126">**Attribute**</span></span>|<span data-ttu-id="9e71c-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="9e71c-127">**Type**</span></span>|<span data-ttu-id="9e71c-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="9e71c-128">**Required**</span></span>|<span data-ttu-id="9e71c-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e71c-129">**Description**</span></span>|<span data-ttu-id="9e71c-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9e71c-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e71c-131">单位</span><span class="sxs-lookup"><span data-stu-id="9e71c-131">Unit</span></span>  <br/> |<span data-ttu-id="9e71c-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9e71c-132">xsd:string</span></span>  <br/> |<span data-ttu-id="9e71c-133">可选</span><span class="sxs-lookup"><span data-stu-id="9e71c-133">optional</span></span>  <br/> |<span data-ttu-id="9e71c-134">表示度量的单位。</span><span class="sxs-lookup"><span data-stu-id="9e71c-134">Represents a unit of measure.</span></span> <span data-ttu-id="9e71c-135">默认值为 in。</span><span class="sxs-lookup"><span data-stu-id="9e71c-135">The default is IN.</span></span>  <br/> |<span data-ttu-id="9e71c-136">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9e71c-136">Values of the xsd:string type.</span></span>  <br/> |
   

