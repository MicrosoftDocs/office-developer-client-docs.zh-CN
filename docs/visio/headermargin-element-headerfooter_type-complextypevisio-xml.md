---
title: HeaderMargin 元素 (HeaderFooter_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2bb0f4c5-eacf-e09b-2fce-dcff2d927557
description: 指定文档页眉的边距。
ms.openlocfilehash: d8126ae73b1fb330234698343d14468fcbb3eed8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351665"
---
# <a name="headermargin-element-headerfootertype-complextype-visio-xml"></a><span data-ttu-id="d056a-103">HeaderMargin 元素 (HeaderFooter_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="d056a-103">HeaderMargin element (HeaderFooter_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="d056a-104">指定文档页眉的边距。</span><span class="sxs-lookup"><span data-stu-id="d056a-104">Specifies the margin of a document's header.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="d056a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d056a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d056a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d056a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d056a-107">HeaderMargin_Type</span><span class="sxs-lookup"><span data-stu-id="d056a-107">HeaderMargin_Type</span></span>](headermargin_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d056a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d056a-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d056a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d056a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d056a-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="d056a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d056a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d056a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d056a-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="d056a-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d056a-113">定义</span><span class="sxs-lookup"><span data-stu-id="d056a-113">Definition</span></span>

```XML
< xs:element name="HeaderMargin" type="HeaderMargin_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d056a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d056a-114">Elements and attributes</span></span>

<span data-ttu-id="d056a-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="d056a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d056a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d056a-116">Parent elements</span></span>

|<span data-ttu-id="d056a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d056a-117">**Element**</span></span>|<span data-ttu-id="d056a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d056a-118">**Type**</span></span>|<span data-ttu-id="d056a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d056a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d056a-120">HeaderFooter</span><span class="sxs-lookup"><span data-stu-id="d056a-120">HeaderFooter</span></span>](headerfooter-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d056a-121">HeaderFooter_Type</span><span class="sxs-lookup"><span data-stu-id="d056a-121">HeaderFooter_Type</span></span>](headerfooter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d056a-122">包含文档的页眉和页脚的元素。</span><span class="sxs-lookup"><span data-stu-id="d056a-122">Contains elements for a document's header and footer.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d056a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d056a-123">Child elements</span></span>

<span data-ttu-id="d056a-124">无。</span><span class="sxs-lookup"><span data-stu-id="d056a-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d056a-125">属性</span><span class="sxs-lookup"><span data-stu-id="d056a-125">Attributes</span></span>

|<span data-ttu-id="d056a-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="d056a-126">**Attribute**</span></span>|<span data-ttu-id="d056a-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="d056a-127">**Type**</span></span>|<span data-ttu-id="d056a-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="d056a-128">**Required**</span></span>|<span data-ttu-id="d056a-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="d056a-129">**Description**</span></span>|<span data-ttu-id="d056a-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d056a-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d056a-131">Unit</span><span class="sxs-lookup"><span data-stu-id="d056a-131">Unit</span></span>  <br/> |<span data-ttu-id="d056a-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d056a-132">xsd:string</span></span>  <br/> |<span data-ttu-id="d056a-133">可选</span><span class="sxs-lookup"><span data-stu-id="d056a-133">optional</span></span>  <br/> |<span data-ttu-id="d056a-134">表示度量单位。</span><span class="sxs-lookup"><span data-stu-id="d056a-134">Represents a unit of measure.</span></span> <span data-ttu-id="d056a-135">默认值为 DP。</span><span class="sxs-lookup"><span data-stu-id="d056a-135">The default is DP.</span></span>  <br/> |<span data-ttu-id="d056a-136">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d056a-136">Values of the xsd:string type.</span></span>  <br/> |
   

