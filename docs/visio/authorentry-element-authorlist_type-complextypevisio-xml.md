---
title: AuthorEntry 元素 (AuthorList_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21ca601b-27f0-b30b-a99e-56359bdf594c
description: 指定用于标识绘图中的注释作者的属性。
ms.openlocfilehash: 29dc4459d0df3b914d61140cb2c5f33cc3e1306e
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537904"
---
# <a name="authorentry-element-authorlisttype-complextype-visio-xml"></a><span data-ttu-id="b554a-103">AuthorEntry 元素 (AuthorList_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b554a-103">AuthorEntry element (AuthorList_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="b554a-104">指定用于标识绘图中的注释作者的属性。</span><span class="sxs-lookup"><span data-stu-id="b554a-104">Specifies properties used to identify the author of a comment in a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="b554a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="b554a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b554a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="b554a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="b554a-107">AuthorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="b554a-107">AuthorEntry_Type</span></span>](authorentry_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="b554a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b554a-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="b554a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b554a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="b554a-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="b554a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="b554a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="b554a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="b554a-112">注释 .xml</span><span class="sxs-lookup"><span data-stu-id="b554a-112">comments.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b554a-113">定义</span><span class="sxs-lookup"><span data-stu-id="b554a-113">Definition</span></span>

```XML
< xs:element name="AuthorEntry" type="AuthorEntry_Type" minOccurs="0" maxOccurs="unbounded" >
< /xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b554a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b554a-114">Elements and attributes</span></span>

<span data-ttu-id="b554a-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="b554a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="b554a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b554a-116">Parent elements</span></span>

|<span data-ttu-id="b554a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="b554a-117">**Element**</span></span>|<span data-ttu-id="b554a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="b554a-118">**Type**</span></span>|<span data-ttu-id="b554a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="b554a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b554a-120">AuthorList</span><span class="sxs-lookup"><span data-stu-id="b554a-120">AuthorList</span></span>](authorlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b554a-121">AuthorList_Type</span><span class="sxs-lookup"><span data-stu-id="b554a-121">AuthorList_Type</span></span>](authorlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b554a-122">指定绘图中的作者。</span><span class="sxs-lookup"><span data-stu-id="b554a-122">Specifies the authors in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="b554a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="b554a-123">Child elements</span></span>

<span data-ttu-id="b554a-124">无。</span><span class="sxs-lookup"><span data-stu-id="b554a-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b554a-125">属性</span><span class="sxs-lookup"><span data-stu-id="b554a-125">Attributes</span></span>

|<span data-ttu-id="b554a-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="b554a-126">**Attribute**</span></span>|<span data-ttu-id="b554a-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="b554a-127">**Type**</span></span>|<span data-ttu-id="b554a-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="b554a-128">**Required**</span></span>|<span data-ttu-id="b554a-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="b554a-129">**Description**</span></span>|<span data-ttu-id="b554a-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b554a-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b554a-131">ID</span><span class="sxs-lookup"><span data-stu-id="b554a-131">ID</span></span>  <br/> |<span data-ttu-id="b554a-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b554a-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b554a-133">必需</span><span class="sxs-lookup"><span data-stu-id="b554a-133">required</span></span>  <br/> |<span data-ttu-id="b554a-134">一个用于标识作者的基于1的值。</span><span class="sxs-lookup"><span data-stu-id="b554a-134">A one-based value that identifies the author.</span></span>  <br/> |<span data-ttu-id="b554a-135">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b554a-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b554a-136">缩写</span><span class="sxs-lookup"><span data-stu-id="b554a-136">Initials</span></span>  <br/> |<span data-ttu-id="b554a-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b554a-137">xsd:string</span></span>  <br/> |<span data-ttu-id="b554a-138">可选</span><span class="sxs-lookup"><span data-stu-id="b554a-138">optional</span></span>  <br/> |<span data-ttu-id="b554a-139">作者的姓名首字母缩写。</span><span class="sxs-lookup"><span data-stu-id="b554a-139">The initials of the author.</span></span>  <br/> |<span data-ttu-id="b554a-140">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b554a-140">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="b554a-141">名称</span><span class="sxs-lookup"><span data-stu-id="b554a-141">Name</span></span>  <br/> |<span data-ttu-id="b554a-142">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b554a-142">xsd:string</span></span>  <br/> |<span data-ttu-id="b554a-143">可选</span><span class="sxs-lookup"><span data-stu-id="b554a-143">optional</span></span>  <br/> |<span data-ttu-id="b554a-144">作者的姓名。</span><span class="sxs-lookup"><span data-stu-id="b554a-144">The name of the author.</span></span>  <br/> |<span data-ttu-id="b554a-145">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b554a-145">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="b554a-146">ResolutionID</span><span class="sxs-lookup"><span data-stu-id="b554a-146">ResolutionID</span></span>  <br/> |<span data-ttu-id="b554a-147">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b554a-147">xsd:string</span></span>  <br/> |<span data-ttu-id="b554a-148">可选</span><span class="sxs-lookup"><span data-stu-id="b554a-148">optional</span></span>  <br/> |<span data-ttu-id="b554a-149">作者的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b554a-149">A unique identifier for the author.</span></span>  <br/> |<span data-ttu-id="b554a-150">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b554a-150">Values of the xsd:string type.</span></span>  <br/> |
   

