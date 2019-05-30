---
title: Comments_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6bc870d2-e163-636f-beae-b3002d54a96c
ms.openlocfilehash: cce19353343190225efedec7f0a5c7bc0f026705
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542014"
---
# <a name="commentstype-complextype-visio-xml"></a><span data-ttu-id="fa1ed-102">Comments_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="fa1ed-102">Comments_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="fa1ed-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="fa1ed-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fa1ed-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="fa1ed-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="fa1ed-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="fa1ed-105">**Schema file**</span></span> <br/> |<span data-ttu-id="fa1ed-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="fa1ed-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="fa1ed-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="fa1ed-107">**Extension base**</span></span> <br/> |<span data-ttu-id="fa1ed-108">无</span><span class="sxs-lookup"><span data-stu-id="fa1ed-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="fa1ed-109">定义</span><span class="sxs-lookup"><span data-stu-id="fa1ed-109">Definition</span></span>

```XML
          <xs:complexType name="Comments_Type">
          
          <xs:sequence>
    <xs:element name="AuthorList"  type="AuthorList_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="CommentList"  type="CommentList_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="ShowCommentTags"
  type="xsd:boolean"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="fa1ed-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="fa1ed-110">Elements and attributes</span></span>

<span data-ttu-id="fa1ed-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="fa1ed-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="fa1ed-112">子元素</span><span class="sxs-lookup"><span data-stu-id="fa1ed-112">Child elements</span></span>

|<span data-ttu-id="fa1ed-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="fa1ed-113">**Element**</span></span>|<span data-ttu-id="fa1ed-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="fa1ed-114">**Type**</span></span>|<span data-ttu-id="fa1ed-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="fa1ed-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fa1ed-116">AuthorList</span><span class="sxs-lookup"><span data-stu-id="fa1ed-116">AuthorList</span></span>](authorlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fa1ed-117">AuthorList_Type</span><span class="sxs-lookup"><span data-stu-id="fa1ed-117">AuthorList_Type</span></span>](authorlist_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="fa1ed-118">CommentList</span><span class="sxs-lookup"><span data-stu-id="fa1ed-118">CommentList</span></span>](commentlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fa1ed-119">CommentList_Type</span><span class="sxs-lookup"><span data-stu-id="fa1ed-119">CommentList_Type</span></span>](commentlist_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="fa1ed-120">属性</span><span class="sxs-lookup"><span data-stu-id="fa1ed-120">Attributes</span></span>

|<span data-ttu-id="fa1ed-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="fa1ed-121">**Attribute**</span></span>|<span data-ttu-id="fa1ed-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="fa1ed-122">**Type**</span></span>|<span data-ttu-id="fa1ed-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="fa1ed-123">**Required**</span></span>|<span data-ttu-id="fa1ed-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="fa1ed-124">**Description**</span></span>|<span data-ttu-id="fa1ed-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="fa1ed-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fa1ed-126">ShowCommentTags</span><span class="sxs-lookup"><span data-stu-id="fa1ed-126">ShowCommentTags</span></span>  <br/> |<span data-ttu-id="fa1ed-127">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="fa1ed-127">xsd:boolean</span></span>  <br/> |<span data-ttu-id="fa1ed-128">可选</span><span class="sxs-lookup"><span data-stu-id="fa1ed-128">optional</span></span>  <br/> ||<span data-ttu-id="fa1ed-129">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fa1ed-129">Values of the xsd:boolean type.</span></span>  <br/> |
   

