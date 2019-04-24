---
title: CommentList 元素 (Comments_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 49fee70d-6556-887b-003f-4f56916d541d
description: 指定绘图中的注释。
ms.openlocfilehash: 424eb10ab356fc2b7f07a1fae27a8e2715e3f2fd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359428"
---
# <a name="commentlist-element-commentstype-complextype-visio-xml"></a><span data-ttu-id="20fc0-103">CommentList 元素 (Comments_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="20fc0-103">CommentList element (Comments_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="20fc0-104">指定绘图中的注释。</span><span class="sxs-lookup"><span data-stu-id="20fc0-104">Specifies the comments in a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="20fc0-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="20fc0-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="20fc0-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="20fc0-106">**Element type**</span></span> <br/> |[<span data-ttu-id="20fc0-107">CommentList_Type</span><span class="sxs-lookup"><span data-stu-id="20fc0-107">CommentList_Type</span></span>](commentlist_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="20fc0-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="20fc0-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="20fc0-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="20fc0-109">**Schema file**</span></span> <br/> |<span data-ttu-id="20fc0-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="20fc0-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="20fc0-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="20fc0-111">**Document parts**</span></span> <br/> |<span data-ttu-id="20fc0-112">注释 .xml</span><span class="sxs-lookup"><span data-stu-id="20fc0-112">comments.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="20fc0-113">定义</span><span class="sxs-lookup"><span data-stu-id="20fc0-113">Definition</span></span>

```XML
< xs:element name="CommentList" type="CommentList_Type" minOccurs="0" maxOccurs="1" >
< /xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="20fc0-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="20fc0-114">Elements and attributes</span></span>

<span data-ttu-id="20fc0-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="20fc0-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="20fc0-116">父元素</span><span class="sxs-lookup"><span data-stu-id="20fc0-116">Parent elements</span></span>

|<span data-ttu-id="20fc0-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="20fc0-117">**Element**</span></span>|<span data-ttu-id="20fc0-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="20fc0-118">**Type**</span></span>|<span data-ttu-id="20fc0-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="20fc0-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="20fc0-120">Comments</span><span class="sxs-lookup"><span data-stu-id="20fc0-120">Comments</span></span>](comments-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="20fc0-121">Comments_Type</span><span class="sxs-lookup"><span data-stu-id="20fc0-121">Comments_Type</span></span>](comments_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="20fc0-122">指定用于标识绘图中的作者和批注的属性。</span><span class="sxs-lookup"><span data-stu-id="20fc0-122">Specifies properties used to identify the authors and comments in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="20fc0-123">子元素</span><span class="sxs-lookup"><span data-stu-id="20fc0-123">Child elements</span></span>

|<span data-ttu-id="20fc0-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="20fc0-124">**Element**</span></span>|<span data-ttu-id="20fc0-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="20fc0-125">**Type**</span></span>|<span data-ttu-id="20fc0-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="20fc0-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="20fc0-127">CommentEntry</span><span class="sxs-lookup"><span data-stu-id="20fc0-127">CommentEntry</span></span>](commententry-element-commentlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="20fc0-128">CommentEntry_Type</span><span class="sxs-lookup"><span data-stu-id="20fc0-128">CommentEntry_Type</span></span>](commententry_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="20fc0-129">指定用于标识绘图中的注释的属性。</span><span class="sxs-lookup"><span data-stu-id="20fc0-129">Specifies properties used to identify a comment in a drawing.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="20fc0-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="20fc0-130">Attributes</span></span>

<span data-ttu-id="20fc0-131">无。</span><span class="sxs-lookup"><span data-stu-id="20fc0-131">None.</span></span>
  

