---
title: Comments_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6bc870d2-e163-636f-beae-b3002d54a96c
ms.openlocfilehash: b2d40b1c8368945cfa27aad0e1d567beea694c28
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393469"
---
# <a name="commentstype-complextype-visio-xml"></a><span data-ttu-id="d911c-102">Comments_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d911c-102">Comments_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="d911c-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="d911c-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d911c-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d911c-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="d911c-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d911c-105">**Schema file**</span></span> <br/> |<span data-ttu-id="d911c-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="d911c-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="d911c-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="d911c-107">**Extension base**</span></span> <br/> |<span data-ttu-id="d911c-108">无</span><span class="sxs-lookup"><span data-stu-id="d911c-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d911c-109">定义</span><span class="sxs-lookup"><span data-stu-id="d911c-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="d911c-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d911c-110">Elements and attributes</span></span>

<span data-ttu-id="d911c-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d911c-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="d911c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d911c-112">Child elements</span></span>

|<span data-ttu-id="d911c-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="d911c-113">**Element**</span></span>|<span data-ttu-id="d911c-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="d911c-114">**Type**</span></span>|<span data-ttu-id="d911c-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="d911c-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d911c-116">AuthorList</span><span class="sxs-lookup"><span data-stu-id="d911c-116">AuthorList</span></span>](authorlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d911c-117">AuthorList_Type</span><span class="sxs-lookup"><span data-stu-id="d911c-117">AuthorList_Type</span></span>](authorlist_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d911c-118">CommentList</span><span class="sxs-lookup"><span data-stu-id="d911c-118">CommentList</span></span>](commentlist-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d911c-119">CommentList_Type</span><span class="sxs-lookup"><span data-stu-id="d911c-119">CommentList_Type</span></span>](commentlist_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="d911c-120">Attributes</span><span class="sxs-lookup"><span data-stu-id="d911c-120">Attributes</span></span>

|<span data-ttu-id="d911c-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="d911c-121">**Attribute**</span></span>|<span data-ttu-id="d911c-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="d911c-122">**Type**</span></span>|<span data-ttu-id="d911c-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="d911c-123">**Required**</span></span>|<span data-ttu-id="d911c-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="d911c-124">**Description**</span></span>|<span data-ttu-id="d911c-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d911c-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d911c-126">ShowCommentTags</span><span class="sxs-lookup"><span data-stu-id="d911c-126">ShowCommentTags</span></span>  <br/> |<span data-ttu-id="d911c-127">化</span><span class="sxs-lookup"><span data-stu-id="d911c-127">xsd:boolean</span></span>  <br/> |<span data-ttu-id="d911c-128">可选</span><span class="sxs-lookup"><span data-stu-id="d911c-128">optional</span></span>  <br/> ||<span data-ttu-id="d911c-129">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="d911c-129">Values of the xsd:boolean type.</span></span>  <br/> |
   

