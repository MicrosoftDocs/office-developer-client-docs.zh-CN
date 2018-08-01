---
title: CommentList 元素 （Comments_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 49fee70d-6556-887b-003f-4f56916d541d
description: 指定与绘图中的注释。
ms.openlocfilehash: 5773b4553185fbc99718be495c48a478ae72000c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779917"
---
# <a name="commentlist-element-commentstype-complextype-visio-xml"></a><span data-ttu-id="25220-103">CommentList 元素 （Comments_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="25220-103">CommentList element (Comments_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="25220-104">指定与绘图中的注释。</span><span class="sxs-lookup"><span data-stu-id="25220-104">Specifies the comments in a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="25220-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="25220-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="25220-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="25220-106">**Element type**</span></span> <br/> |[<span data-ttu-id="25220-107">CommentList_Type</span><span class="sxs-lookup"><span data-stu-id="25220-107">CommentList_Type</span></span>](commentlist_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="25220-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="25220-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="25220-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="25220-109">**Schema file**</span></span> <br/> |<span data-ttu-id="25220-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="25220-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="25220-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="25220-111">**Document parts**</span></span> <br/> |<span data-ttu-id="25220-112">comments.xml</span><span class="sxs-lookup"><span data-stu-id="25220-112">comments.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="25220-113">定义</span><span class="sxs-lookup"><span data-stu-id="25220-113">Definition</span></span>

```XML
< xs:element name="CommentList" type="CommentList_Type" minOccurs="0" maxOccurs="1" >
< /xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="25220-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="25220-114">Elements and attributes</span></span>

<span data-ttu-id="25220-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="25220-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="25220-116">父元素</span><span class="sxs-lookup"><span data-stu-id="25220-116">Parent elements</span></span>

|<span data-ttu-id="25220-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="25220-117">**Element**</span></span>|<span data-ttu-id="25220-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="25220-118">**Type**</span></span>|<span data-ttu-id="25220-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="25220-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="25220-120">Comments</span><span class="sxs-lookup"><span data-stu-id="25220-120">Comments</span></span>](comments-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="25220-121">Comments_Type</span><span class="sxs-lookup"><span data-stu-id="25220-121">Comments_Type</span></span>](comments_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="25220-122">指定用于标识的作者和注释与绘图中的属性。</span><span class="sxs-lookup"><span data-stu-id="25220-122">Specifies properties used to identify the authors and comments in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="25220-123">子元素</span><span class="sxs-lookup"><span data-stu-id="25220-123">Child elements</span></span>

|<span data-ttu-id="25220-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="25220-124">**Element**</span></span>|<span data-ttu-id="25220-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="25220-125">**Type**</span></span>|<span data-ttu-id="25220-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="25220-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="25220-127">CommentEntry</span><span class="sxs-lookup"><span data-stu-id="25220-127">CommentEntry</span></span>](commententry-element-commentlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="25220-128">CommentEntry_Type</span><span class="sxs-lookup"><span data-stu-id="25220-128">CommentEntry_Type</span></span>](commententry_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="25220-129">指定用于标识与绘图中的注释的属性。</span><span class="sxs-lookup"><span data-stu-id="25220-129">Specifies properties used to identify a comment in a drawing.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="25220-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="25220-130">Attributes</span></span>

<span data-ttu-id="25220-131">无。</span><span class="sxs-lookup"><span data-stu-id="25220-131">None.</span></span>
  

