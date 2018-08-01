---
title: AuthorEntry 元素 （AuthorList_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21ca601b-27f0-b30b-a99e-56359bdf594c
description: 指定用于确定在绘图中批注的作者属性。
ms.openlocfilehash: 905dbc5d08cfb2010c9d749e59584cc294e54e86
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779658"
---
# <a name="authorentry-element-authorlisttype-complextype-visio-xml"></a><span data-ttu-id="fa6e8-103">AuthorEntry 元素 （AuthorList_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="fa6e8-103">AuthorEntry element (AuthorList_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="fa6e8-104">指定用于确定在绘图中批注的作者属性。</span><span class="sxs-lookup"><span data-stu-id="fa6e8-104">Specifies properties used to identify the author of a comment in a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="fa6e8-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="fa6e8-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fa6e8-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="fa6e8-106">**Element type**</span></span> <br/> |[<span data-ttu-id="fa6e8-107">AuthorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="fa6e8-107">AuthorEntry_Type</span></span>](authorentry_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="fa6e8-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="fa6e8-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="fa6e8-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="fa6e8-109">**Schema file**</span></span> <br/> |<span data-ttu-id="fa6e8-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="fa6e8-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="fa6e8-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="fa6e8-111">**Document parts**</span></span> <br/> |<span data-ttu-id="fa6e8-112">comments.xml</span><span class="sxs-lookup"><span data-stu-id="fa6e8-112">comments.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="fa6e8-113">定义</span><span class="sxs-lookup"><span data-stu-id="fa6e8-113">Definition</span></span>

```XML
< xs:element name="AuthorEntry" type="AuthorEntry_Type" minOccurs="0" maxOccurs="unbounded" >
< /xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="fa6e8-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="fa6e8-114">Elements and attributes</span></span>

<span data-ttu-id="fa6e8-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="fa6e8-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="fa6e8-116">父元素</span><span class="sxs-lookup"><span data-stu-id="fa6e8-116">Parent elements</span></span>

|<span data-ttu-id="fa6e8-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="fa6e8-117">**Element**</span></span>|<span data-ttu-id="fa6e8-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="fa6e8-118">**Type**</span></span>|<span data-ttu-id="fa6e8-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="fa6e8-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fa6e8-120">AuthorList</span><span class="sxs-lookup"><span data-stu-id="fa6e8-120">AuthorList</span></span>](authorlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fa6e8-121">AuthorList_Type</span><span class="sxs-lookup"><span data-stu-id="fa6e8-121">AuthorList_Type</span></span>](authorlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fa6e8-122">指定与绘图中的作者。</span><span class="sxs-lookup"><span data-stu-id="fa6e8-122">Specifies the authors in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="fa6e8-123">子元素</span><span class="sxs-lookup"><span data-stu-id="fa6e8-123">Child elements</span></span>

<span data-ttu-id="fa6e8-124">无。</span><span class="sxs-lookup"><span data-stu-id="fa6e8-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="fa6e8-125">属性</span><span class="sxs-lookup"><span data-stu-id="fa6e8-125">Attributes</span></span>

|<span data-ttu-id="fa6e8-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="fa6e8-126">**Attribute**</span></span>|<span data-ttu-id="fa6e8-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="fa6e8-127">**Type**</span></span>|<span data-ttu-id="fa6e8-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="fa6e8-128">**Required**</span></span>|<span data-ttu-id="fa6e8-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="fa6e8-129">**Description**</span></span>|<span data-ttu-id="fa6e8-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="fa6e8-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fa6e8-131">ID</span><span class="sxs-lookup"><span data-stu-id="fa6e8-131">ID</span></span>  <br/> |<span data-ttu-id="fa6e8-132">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="fa6e8-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="fa6e8-133">必需</span><span class="sxs-lookup"><span data-stu-id="fa6e8-133">required</span></span>  <br/> |<span data-ttu-id="fa6e8-134">一个从 1 开始的值，标识作者。</span><span class="sxs-lookup"><span data-stu-id="fa6e8-134">A one-based value that identifies the author.</span></span>  <br/> |<span data-ttu-id="fa6e8-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fa6e8-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="fa6e8-136">Initials</span><span class="sxs-lookup"><span data-stu-id="fa6e8-136">Initials</span></span>  <br/> |<span data-ttu-id="fa6e8-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="fa6e8-137">xsd:string</span></span>  <br/> |<span data-ttu-id="fa6e8-138">可选</span><span class="sxs-lookup"><span data-stu-id="fa6e8-138">optional</span></span>  <br/> |<span data-ttu-id="fa6e8-139">作者的首字母缩写。</span><span class="sxs-lookup"><span data-stu-id="fa6e8-139">The initials of the author.</span></span>  <br/> |<span data-ttu-id="fa6e8-140">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fa6e8-140">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="fa6e8-141">名称</span><span class="sxs-lookup"><span data-stu-id="fa6e8-141">Name</span></span>  <br/> |<span data-ttu-id="fa6e8-142">xsd: string</span><span class="sxs-lookup"><span data-stu-id="fa6e8-142">xsd:string</span></span>  <br/> |<span data-ttu-id="fa6e8-143">可选</span><span class="sxs-lookup"><span data-stu-id="fa6e8-143">optional</span></span>  <br/> |<span data-ttu-id="fa6e8-144">作者的名称。</span><span class="sxs-lookup"><span data-stu-id="fa6e8-144">The name of the author.</span></span>  <br/> |<span data-ttu-id="fa6e8-145">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fa6e8-145">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="fa6e8-146">ResolutionID</span><span class="sxs-lookup"><span data-stu-id="fa6e8-146">ResolutionID</span></span>  <br/> |<span data-ttu-id="fa6e8-147">xsd: string</span><span class="sxs-lookup"><span data-stu-id="fa6e8-147">xsd:string</span></span>  <br/> |<span data-ttu-id="fa6e8-148">可选</span><span class="sxs-lookup"><span data-stu-id="fa6e8-148">optional</span></span>  <br/> |<span data-ttu-id="fa6e8-149">作者的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="fa6e8-149">A unique identifier for the author.</span></span>  <br/> |<span data-ttu-id="fa6e8-150">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fa6e8-150">Values of the xsd:string type.</span></span>  <br/> |
   

