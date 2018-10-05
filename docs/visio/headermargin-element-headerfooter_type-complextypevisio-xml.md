---
title: HeaderMargin 元素 （HeaderFooter_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2bb0f4c5-eacf-e09b-2fce-dcff2d927557
description: 指定文档的页眉的边距。
ms.openlocfilehash: d8126ae73b1fb330234698343d14468fcbb3eed8
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393374"
---
# <a name="headermargin-element-headerfootertype-complextype-visio-xml"></a><span data-ttu-id="8df77-103">HeaderMargin 元素 （HeaderFooter_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="8df77-103">HeaderMargin element (HeaderFooter_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="8df77-104">指定文档的页眉的边距。</span><span class="sxs-lookup"><span data-stu-id="8df77-104">Specifies the margin of a document's header.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="8df77-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="8df77-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8df77-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="8df77-106">**Element type**</span></span> <br/> |[<span data-ttu-id="8df77-107">HeaderMargin_Type</span><span class="sxs-lookup"><span data-stu-id="8df77-107">HeaderMargin_Type</span></span>](headermargin_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="8df77-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="8df77-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="8df77-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="8df77-109">**Schema file**</span></span> <br/> |<span data-ttu-id="8df77-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="8df77-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="8df77-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="8df77-111">**Document parts**</span></span> <br/> |<span data-ttu-id="8df77-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="8df77-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="8df77-113">定义</span><span class="sxs-lookup"><span data-stu-id="8df77-113">Definition</span></span>

```XML
< xs:element name="HeaderMargin" type="HeaderMargin_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="8df77-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="8df77-114">Elements and attributes</span></span>

<span data-ttu-id="8df77-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="8df77-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="8df77-116">父元素</span><span class="sxs-lookup"><span data-stu-id="8df77-116">Parent elements</span></span>

|<span data-ttu-id="8df77-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="8df77-117">**Element**</span></span>|<span data-ttu-id="8df77-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="8df77-118">**Type**</span></span>|<span data-ttu-id="8df77-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="8df77-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8df77-120">HeaderFooter</span><span class="sxs-lookup"><span data-stu-id="8df77-120">HeaderFooter</span></span>](headerfooter-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="8df77-121">HeaderFooter_Type</span><span class="sxs-lookup"><span data-stu-id="8df77-121">HeaderFooter_Type</span></span>](headerfooter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8df77-122">包含文档的页眉和页脚的元素。</span><span class="sxs-lookup"><span data-stu-id="8df77-122">Contains elements for a document's header and footer.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="8df77-123">子元素</span><span class="sxs-lookup"><span data-stu-id="8df77-123">Child elements</span></span>

<span data-ttu-id="8df77-124">无。</span><span class="sxs-lookup"><span data-stu-id="8df77-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="8df77-125">属性</span><span class="sxs-lookup"><span data-stu-id="8df77-125">Attributes</span></span>

|<span data-ttu-id="8df77-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="8df77-126">**Attribute**</span></span>|<span data-ttu-id="8df77-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="8df77-127">**Type**</span></span>|<span data-ttu-id="8df77-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="8df77-128">**Required**</span></span>|<span data-ttu-id="8df77-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="8df77-129">**Description**</span></span>|<span data-ttu-id="8df77-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="8df77-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8df77-131">单位</span><span class="sxs-lookup"><span data-stu-id="8df77-131">Unit</span></span>  <br/> |<span data-ttu-id="8df77-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8df77-132">xsd:string</span></span>  <br/> |<span data-ttu-id="8df77-133">可选</span><span class="sxs-lookup"><span data-stu-id="8df77-133">optional</span></span>  <br/> |<span data-ttu-id="8df77-134">表示度量的单位。</span><span class="sxs-lookup"><span data-stu-id="8df77-134">Represents a unit of measure.</span></span> <span data-ttu-id="8df77-135">默认值为 DP。</span><span class="sxs-lookup"><span data-stu-id="8df77-135">The default is DP.</span></span>  <br/> |<span data-ttu-id="8df77-136">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8df77-136">Values of the xsd:string type.</span></span>  <br/> |
   

