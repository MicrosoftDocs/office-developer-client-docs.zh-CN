---
title: Comments 元素 （Comments_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f72ced69-0d49-18cd-f1e6-d0b2cb39b4c0
description: 指定用于标识的作者和注释与绘图中的属性。
ms.openlocfilehash: 77695fb32aa88cb6c2b6ac5e9bff99fa12e262bf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779913"
---
# <a name="comments-element-commentstype-complextype-visio-xml"></a><span data-ttu-id="88121-103">Comments 元素 （Comments_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="88121-103">Comments element (Comments_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="88121-104">指定用于标识的作者和注释与绘图中的属性。</span><span class="sxs-lookup"><span data-stu-id="88121-104">Specifies properties used to identify the authors and comments in a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="88121-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="88121-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="88121-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="88121-106">**Element type**</span></span> <br/> |[<span data-ttu-id="88121-107">Comments_Type</span><span class="sxs-lookup"><span data-stu-id="88121-107">Comments_Type</span></span>](comments_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="88121-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="88121-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="88121-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="88121-109">**Schema file**</span></span> <br/> |<span data-ttu-id="88121-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="88121-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="88121-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="88121-111">**Document parts**</span></span> <br/> |<span data-ttu-id="88121-112">comments.xml</span><span class="sxs-lookup"><span data-stu-id="88121-112">comments.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="88121-113">定义</span><span class="sxs-lookup"><span data-stu-id="88121-113">Definition</span></span>

```XML
< xs:element name="Comments" type="Comments_Type" >
< /xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="88121-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="88121-114">Elements and attributes</span></span>

<span data-ttu-id="88121-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="88121-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="88121-116">父元素</span><span class="sxs-lookup"><span data-stu-id="88121-116">Parent elements</span></span>

<span data-ttu-id="88121-117">无。</span><span class="sxs-lookup"><span data-stu-id="88121-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="88121-118">子元素</span><span class="sxs-lookup"><span data-stu-id="88121-118">Child elements</span></span>

|<span data-ttu-id="88121-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="88121-119">**Element**</span></span>|<span data-ttu-id="88121-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="88121-120">**Type**</span></span>|<span data-ttu-id="88121-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="88121-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="88121-122">AuthorList</span><span class="sxs-lookup"><span data-stu-id="88121-122">AuthorList</span></span>](authorlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="88121-123">AuthorList_Type</span><span class="sxs-lookup"><span data-stu-id="88121-123">AuthorList_Type</span></span>](authorlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="88121-124">指定与绘图中的作者。</span><span class="sxs-lookup"><span data-stu-id="88121-124">Specifies the authors in a drawing.</span></span>  <br/> |
|[<span data-ttu-id="88121-125">CommentList</span><span class="sxs-lookup"><span data-stu-id="88121-125">CommentList</span></span>](commentlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="88121-126">CommentList_Type</span><span class="sxs-lookup"><span data-stu-id="88121-126">CommentList_Type</span></span>](commentlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="88121-127">指定与绘图中的注释。</span><span class="sxs-lookup"><span data-stu-id="88121-127">Specifies the comments in a drawing.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="88121-128">Attributes</span><span class="sxs-lookup"><span data-stu-id="88121-128">Attributes</span></span>

<span data-ttu-id="88121-129">无。</span><span class="sxs-lookup"><span data-stu-id="88121-129">None.</span></span>
  

