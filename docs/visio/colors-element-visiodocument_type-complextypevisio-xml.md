---
title: Colors 元素 (VisioDocument_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3f439c2d-78be-5f2e-fa5a-f3feb83a0234
description: 包含文档的颜色表。
ms.openlocfilehash: 6f18926961583e09f83dd7921ca140c07a60ecc3
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540173"
---
# <a name="colors-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="c1684-103">Colors 元素 (VisioDocument_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="c1684-103">Colors element (VisioDocument_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="c1684-104">包含文档的颜色表。</span><span class="sxs-lookup"><span data-stu-id="c1684-104">Contains the document's color table.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="c1684-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="c1684-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c1684-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="c1684-106">**Element type**</span></span> <br/> |[<span data-ttu-id="c1684-107">Colors_Type</span><span class="sxs-lookup"><span data-stu-id="c1684-107">Colors_Type</span></span>](colors_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="c1684-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c1684-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="c1684-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c1684-109">**Schema file**</span></span> <br/> |<span data-ttu-id="c1684-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="c1684-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="c1684-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="c1684-111">**Document parts**</span></span> <br/> |<span data-ttu-id="c1684-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="c1684-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c1684-113">定义</span><span class="sxs-lookup"><span data-stu-id="c1684-113">Definition</span></span>

```XML
< xs:element name="Colors" type="Colors_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c1684-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c1684-114">Elements and attributes</span></span>

<span data-ttu-id="c1684-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="c1684-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="c1684-116">父元素</span><span class="sxs-lookup"><span data-stu-id="c1684-116">Parent elements</span></span>

|<span data-ttu-id="c1684-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="c1684-117">**Element**</span></span>|<span data-ttu-id="c1684-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="c1684-118">**Type**</span></span>|<span data-ttu-id="c1684-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="c1684-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c1684-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="c1684-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="c1684-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="c1684-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c1684-122">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="c1684-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="c1684-123">子元素</span><span class="sxs-lookup"><span data-stu-id="c1684-123">Child elements</span></span>

|<span data-ttu-id="c1684-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="c1684-124">**Element**</span></span>|<span data-ttu-id="c1684-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="c1684-125">**Type**</span></span>|<span data-ttu-id="c1684-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="c1684-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c1684-127">ColorEntry</span><span class="sxs-lookup"><span data-stu-id="c1684-127">ColorEntry</span></span>](colorentry-element-colors_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c1684-128">ColorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="c1684-128">ColorEntry_Type</span></span>](colorentry_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c1684-129">包含颜色表项。</span><span class="sxs-lookup"><span data-stu-id="c1684-129">Contains a color table entry.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="c1684-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="c1684-130">Attributes</span></span>

<span data-ttu-id="c1684-131">无。</span><span class="sxs-lookup"><span data-stu-id="c1684-131">None.</span></span>
  

