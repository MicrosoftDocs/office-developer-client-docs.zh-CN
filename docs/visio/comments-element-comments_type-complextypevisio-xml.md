---
title: Comments 元素 （Comments_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f72ced69-0d49-18cd-f1e6-d0b2cb39b4c0
description: 指定用于标识的作者和注释与绘图中的属性。
ms.openlocfilehash: d82125cc5d795f0cb4455a5c10be1abf001e1198
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389643"
---
# <a name="comments-element-commentstype-complextype-visio-xml"></a><span data-ttu-id="b0b38-103">Comments 元素 （Comments_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b0b38-103">Comments element (Comments_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="b0b38-104">指定用于标识的作者和注释与绘图中的属性。</span><span class="sxs-lookup"><span data-stu-id="b0b38-104">Specifies properties used to identify the authors and comments in a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="b0b38-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="b0b38-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b0b38-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="b0b38-106">**Element type**</span></span> <br/> |[<span data-ttu-id="b0b38-107">Comments_Type</span><span class="sxs-lookup"><span data-stu-id="b0b38-107">Comments_Type</span></span>](comments_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="b0b38-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b0b38-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="b0b38-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b0b38-109">**Schema file**</span></span> <br/> |<span data-ttu-id="b0b38-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="b0b38-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="b0b38-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="b0b38-111">**Document parts**</span></span> <br/> |<span data-ttu-id="b0b38-112">comments.xml</span><span class="sxs-lookup"><span data-stu-id="b0b38-112">comments.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b0b38-113">定义</span><span class="sxs-lookup"><span data-stu-id="b0b38-113">Definition</span></span>

```XML
< xs:element name="Comments" type="Comments_Type" >
< /xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b0b38-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b0b38-114">Elements and attributes</span></span>

<span data-ttu-id="b0b38-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="b0b38-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="b0b38-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b0b38-116">Parent elements</span></span>

<span data-ttu-id="b0b38-117">无。</span><span class="sxs-lookup"><span data-stu-id="b0b38-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="b0b38-118">子元素</span><span class="sxs-lookup"><span data-stu-id="b0b38-118">Child elements</span></span>

|<span data-ttu-id="b0b38-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="b0b38-119">**Element**</span></span>|<span data-ttu-id="b0b38-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="b0b38-120">**Type**</span></span>|<span data-ttu-id="b0b38-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="b0b38-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b0b38-122">AuthorList</span><span class="sxs-lookup"><span data-stu-id="b0b38-122">AuthorList</span></span>](authorlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b0b38-123">AuthorList_Type</span><span class="sxs-lookup"><span data-stu-id="b0b38-123">AuthorList_Type</span></span>](authorlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b0b38-124">指定与绘图中的作者。</span><span class="sxs-lookup"><span data-stu-id="b0b38-124">Specifies the authors in a drawing.</span></span>  <br/> |
|[<span data-ttu-id="b0b38-125">CommentList</span><span class="sxs-lookup"><span data-stu-id="b0b38-125">CommentList</span></span>](commentlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b0b38-126">CommentList_Type</span><span class="sxs-lookup"><span data-stu-id="b0b38-126">CommentList_Type</span></span>](commentlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b0b38-127">指定与绘图中的注释。</span><span class="sxs-lookup"><span data-stu-id="b0b38-127">Specifies the comments in a drawing.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="b0b38-128">Attributes</span><span class="sxs-lookup"><span data-stu-id="b0b38-128">Attributes</span></span>

<span data-ttu-id="b0b38-129">无。</span><span class="sxs-lookup"><span data-stu-id="b0b38-129">None.</span></span>
  

