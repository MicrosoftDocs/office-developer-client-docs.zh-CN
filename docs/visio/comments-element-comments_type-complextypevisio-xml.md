---
title: 'Comments 元素 (Comments_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f72ced69-0d49-18cd-f1e6-d0b2cb39b4c0
description: 指定用于标识绘图中的作者和注释的属性。
ms.openlocfilehash: 93e75e47a203ee13385085c4b5e261fd3a724d4f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539218"
---
# <a name="comments-element-comments_type-complextype-visio-xml"></a><span data-ttu-id="2a728-103">Comments 元素 (Comments_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="2a728-103">Comments element (Comments_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="2a728-104">指定用于标识绘图中的作者和注释的属性。</span><span class="sxs-lookup"><span data-stu-id="2a728-104">Specifies properties used to identify the authors and comments in a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="2a728-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="2a728-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2a728-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="2a728-106">**Element type**</span></span> <br/> |[<span data-ttu-id="2a728-107">Comments_Type</span><span class="sxs-lookup"><span data-stu-id="2a728-107">Comments_Type</span></span>](comments_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="2a728-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2a728-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="2a728-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2a728-109">**Schema file**</span></span> <br/> |<span data-ttu-id="2a728-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="2a728-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="2a728-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="2a728-111">**Document parts**</span></span> <br/> |<span data-ttu-id="2a728-112">comments.xml</span><span class="sxs-lookup"><span data-stu-id="2a728-112">comments.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2a728-113">定义</span><span class="sxs-lookup"><span data-stu-id="2a728-113">Definition</span></span>

```XML
< xs:element name="Comments" type="Comments_Type" >
< /xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="2a728-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2a728-114">Elements and attributes</span></span>

<span data-ttu-id="2a728-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="2a728-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="2a728-116">父元素</span><span class="sxs-lookup"><span data-stu-id="2a728-116">Parent elements</span></span>

<span data-ttu-id="2a728-117">无。</span><span class="sxs-lookup"><span data-stu-id="2a728-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="2a728-118">子元素</span><span class="sxs-lookup"><span data-stu-id="2a728-118">Child elements</span></span>

|<span data-ttu-id="2a728-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="2a728-119">**Element**</span></span>|<span data-ttu-id="2a728-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="2a728-120">**Type**</span></span>|<span data-ttu-id="2a728-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a728-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2a728-122">AuthorList</span><span class="sxs-lookup"><span data-stu-id="2a728-122">AuthorList</span></span>](authorlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2a728-123">AuthorList_Type</span><span class="sxs-lookup"><span data-stu-id="2a728-123">AuthorList_Type</span></span>](authorlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="2a728-124">指定绘图中的作者。</span><span class="sxs-lookup"><span data-stu-id="2a728-124">Specifies the authors in a drawing.</span></span>  <br/> |
|[<span data-ttu-id="2a728-125">CommentList</span><span class="sxs-lookup"><span data-stu-id="2a728-125">CommentList</span></span>](commentlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2a728-126">CommentList_Type</span><span class="sxs-lookup"><span data-stu-id="2a728-126">CommentList_Type</span></span>](commentlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="2a728-127">指定绘图中的注释。</span><span class="sxs-lookup"><span data-stu-id="2a728-127">Specifies the comments in a drawing.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="2a728-128">Attributes</span><span class="sxs-lookup"><span data-stu-id="2a728-128">Attributes</span></span>

<span data-ttu-id="2a728-129">无。</span><span class="sxs-lookup"><span data-stu-id="2a728-129">None.</span></span>
  

