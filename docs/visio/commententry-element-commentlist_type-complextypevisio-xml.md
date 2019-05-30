---
title: CommentEntry 元素 (CommentList_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b0653622-fa94-4889-68c2-94f3e7a83119
description: 指定用于标识绘图中的注释的属性。
ms.openlocfilehash: 6b4f20d632b54e7c96ef8181310e8ffab1abbd0f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540110"
---
# <a name="commententry-element-commentlisttype-complextype-visio-xml"></a><span data-ttu-id="91c5d-103">CommentEntry 元素 (CommentList_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="91c5d-103">CommentEntry element (CommentList_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="91c5d-104">指定用于标识绘图中的注释的属性。</span><span class="sxs-lookup"><span data-stu-id="91c5d-104">Specifies properties used to identify a comment in a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="91c5d-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="91c5d-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="91c5d-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="91c5d-106">**Element type**</span></span> <br/> |[<span data-ttu-id="91c5d-107">CommentEntry_Type</span><span class="sxs-lookup"><span data-stu-id="91c5d-107">CommentEntry_Type</span></span>](commententry_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="91c5d-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="91c5d-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="91c5d-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="91c5d-109">**Schema file**</span></span> <br/> |<span data-ttu-id="91c5d-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="91c5d-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="91c5d-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="91c5d-111">**Document parts**</span></span> <br/> |<span data-ttu-id="91c5d-112">注释 .xml</span><span class="sxs-lookup"><span data-stu-id="91c5d-112">comments.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="91c5d-113">定义</span><span class="sxs-lookup"><span data-stu-id="91c5d-113">Definition</span></span>

```XML
< xs:element name="CommentEntry" type="CommentEntry_Type" minOccurs="0" maxOccurs="unbounded" >
< /xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="91c5d-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="91c5d-114">Elements and attributes</span></span>

<span data-ttu-id="91c5d-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="91c5d-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="91c5d-116">父元素</span><span class="sxs-lookup"><span data-stu-id="91c5d-116">Parent elements</span></span>

|<span data-ttu-id="91c5d-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="91c5d-117">**Element**</span></span>|<span data-ttu-id="91c5d-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="91c5d-118">**Type**</span></span>|<span data-ttu-id="91c5d-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="91c5d-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="91c5d-120">CommentList</span><span class="sxs-lookup"><span data-stu-id="91c5d-120">CommentList</span></span>](commentlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="91c5d-121">CommentList_Type</span><span class="sxs-lookup"><span data-stu-id="91c5d-121">CommentList_Type</span></span>](commentlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="91c5d-122">指定绘图中的注释。</span><span class="sxs-lookup"><span data-stu-id="91c5d-122">Specifies the comments in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="91c5d-123">子元素</span><span class="sxs-lookup"><span data-stu-id="91c5d-123">Child elements</span></span>

<span data-ttu-id="91c5d-124">无。</span><span class="sxs-lookup"><span data-stu-id="91c5d-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="91c5d-125">属性</span><span class="sxs-lookup"><span data-stu-id="91c5d-125">Attributes</span></span>

|<span data-ttu-id="91c5d-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="91c5d-126">**Attribute**</span></span>|<span data-ttu-id="91c5d-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="91c5d-127">**Type**</span></span>|<span data-ttu-id="91c5d-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="91c5d-128">**Required**</span></span>|<span data-ttu-id="91c5d-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="91c5d-129">**Description**</span></span>|<span data-ttu-id="91c5d-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="91c5d-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="91c5d-131">AuthorID</span><span class="sxs-lookup"><span data-stu-id="91c5d-131">AuthorID</span></span>  <br/> |<span data-ttu-id="91c5d-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="91c5d-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="91c5d-133">必需</span><span class="sxs-lookup"><span data-stu-id="91c5d-133">required</span></span>  <br/> |<span data-ttu-id="91c5d-134">一个用于标识作者的基于1的值。</span><span class="sxs-lookup"><span data-stu-id="91c5d-134">A one-based value that identifies the author.</span></span>  <br/> |<span data-ttu-id="91c5d-135">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91c5d-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="91c5d-136">CommentID</span><span class="sxs-lookup"><span data-stu-id="91c5d-136">CommentID</span></span>  <br/> |<span data-ttu-id="91c5d-137">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="91c5d-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="91c5d-138">必需</span><span class="sxs-lookup"><span data-stu-id="91c5d-138">required</span></span>  <br/> |<span data-ttu-id="91c5d-139">标识绘图页中的注释的唯一值。</span><span class="sxs-lookup"><span data-stu-id="91c5d-139">A unique value that identifies the comment in a drawing page.</span></span>  <br/> |<span data-ttu-id="91c5d-140">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91c5d-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="91c5d-141">日期</span><span class="sxs-lookup"><span data-stu-id="91c5d-141">Date</span></span>  <br/> |<span data-ttu-id="91c5d-142">xsd: dateTime</span><span class="sxs-lookup"><span data-stu-id="91c5d-142">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="91c5d-143">必需</span><span class="sxs-lookup"><span data-stu-id="91c5d-143">required</span></span>  <br/> |<span data-ttu-id="91c5d-144">指定何时创建注释。</span><span class="sxs-lookup"><span data-stu-id="91c5d-144">Specifies when a comment was created.</span></span>  <br/> |<span data-ttu-id="91c5d-145">Xsd: dateTime 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91c5d-145">Values of the xsd:dateTime type.</span></span>  <br/> |
|<span data-ttu-id="91c5d-146">Done</span><span class="sxs-lookup"><span data-stu-id="91c5d-146">Done</span></span>  <br/> |<span data-ttu-id="91c5d-147">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="91c5d-147">xsd:boolean</span></span>  <br/> |<span data-ttu-id="91c5d-148">可选</span><span class="sxs-lookup"><span data-stu-id="91c5d-148">optional</span></span>  <br/> |<span data-ttu-id="91c5d-149">指定注释的当前状态。</span><span class="sxs-lookup"><span data-stu-id="91c5d-149">Specifies the current state of the comment.</span></span>  <br/> |<span data-ttu-id="91c5d-150">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91c5d-150">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="91c5d-151">EditDate</span><span class="sxs-lookup"><span data-stu-id="91c5d-151">EditDate</span></span>  <br/> |<span data-ttu-id="91c5d-152">xsd: dateTime</span><span class="sxs-lookup"><span data-stu-id="91c5d-152">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="91c5d-153">可选</span><span class="sxs-lookup"><span data-stu-id="91c5d-153">optional</span></span>  <br/> |<span data-ttu-id="91c5d-154">指定上次更改注释的时间。</span><span class="sxs-lookup"><span data-stu-id="91c5d-154">Specifies when a comment was last changed.</span></span>  <br/> |<span data-ttu-id="91c5d-155">Xsd: dateTime 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91c5d-155">Values of the xsd:dateTime type.</span></span>  <br/> |
|<span data-ttu-id="91c5d-156">PageID</span><span class="sxs-lookup"><span data-stu-id="91c5d-156">PageID</span></span>  <br/> |<span data-ttu-id="91c5d-157">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="91c5d-157">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="91c5d-158">必需</span><span class="sxs-lookup"><span data-stu-id="91c5d-158">required</span></span>  <br/> |<span data-ttu-id="91c5d-159">一个值, 用于标识注释所在的绘图页。</span><span class="sxs-lookup"><span data-stu-id="91c5d-159">A value that identifies the drawing page the comment is on.</span></span>  <br/> |<span data-ttu-id="91c5d-160">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91c5d-160">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="91c5d-161">ShapeID</span><span class="sxs-lookup"><span data-stu-id="91c5d-161">ShapeID</span></span>  <br/> |<span data-ttu-id="91c5d-162">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="91c5d-162">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="91c5d-163">可选</span><span class="sxs-lookup"><span data-stu-id="91c5d-163">optional</span></span>  <br/> |<span data-ttu-id="91c5d-164">一个标识批注所在的形状的值。</span><span class="sxs-lookup"><span data-stu-id="91c5d-164">A value that identifies the shape the comment is on.</span></span> <span data-ttu-id="91c5d-165">如果未指定 ShapeID, 则注释引用绘图页。</span><span class="sxs-lookup"><span data-stu-id="91c5d-165">If no ShapeID is specified, the comment refers to the drawing page.</span></span>  <br/> |<span data-ttu-id="91c5d-166">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91c5d-166">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

