---
title: AuthorList 元素 （Comments_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4b6950c4-7c03-6462-eeab-3176db9a8f7e
description: 指定与绘图中的注释作者。
ms.openlocfilehash: af1b1889fa3736931c9abde35191cf5cb3e1bbd5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387739"
---
# <a name="authorlist-element-commentstype-complextype-visio-xml"></a><span data-ttu-id="5f5ea-103">AuthorList 元素 （Comments_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="5f5ea-103">AuthorList element (Comments_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="5f5ea-104">指定与绘图中的注释作者。</span><span class="sxs-lookup"><span data-stu-id="5f5ea-104">Specifies the authors of comments in a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="5f5ea-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="5f5ea-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5f5ea-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="5f5ea-106">**Element type**</span></span> <br/> |[<span data-ttu-id="5f5ea-107">AuthorList_Type</span><span class="sxs-lookup"><span data-stu-id="5f5ea-107">AuthorList_Type</span></span>](authorlist_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="5f5ea-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5f5ea-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="5f5ea-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5f5ea-109">**Schema file**</span></span> <br/> |<span data-ttu-id="5f5ea-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="5f5ea-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="5f5ea-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="5f5ea-111">**Document parts**</span></span> <br/> |<span data-ttu-id="5f5ea-112">comments.xml</span><span class="sxs-lookup"><span data-stu-id="5f5ea-112">comments.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5f5ea-113">定义</span><span class="sxs-lookup"><span data-stu-id="5f5ea-113">Definition</span></span>

```XML
< xs:element name="AuthorList" type="AuthorList_Type" minOccurs="0" maxOccurs="1" >
< /xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="5f5ea-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5f5ea-114">Elements and attributes</span></span>

<span data-ttu-id="5f5ea-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="5f5ea-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="5f5ea-116">父元素</span><span class="sxs-lookup"><span data-stu-id="5f5ea-116">Parent elements</span></span>

|<span data-ttu-id="5f5ea-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="5f5ea-117">**Element**</span></span>|<span data-ttu-id="5f5ea-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="5f5ea-118">**Type**</span></span>|<span data-ttu-id="5f5ea-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="5f5ea-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5f5ea-120">Comments</span><span class="sxs-lookup"><span data-stu-id="5f5ea-120">Comments</span></span>](comments-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5f5ea-121">Comments_Type</span><span class="sxs-lookup"><span data-stu-id="5f5ea-121">Comments_Type</span></span>](comments_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="5f5ea-122">指定与绘图中的注释。</span><span class="sxs-lookup"><span data-stu-id="5f5ea-122">Specifies the comments in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="5f5ea-123">子元素</span><span class="sxs-lookup"><span data-stu-id="5f5ea-123">Child elements</span></span>

|<span data-ttu-id="5f5ea-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="5f5ea-124">**Element**</span></span>|<span data-ttu-id="5f5ea-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="5f5ea-125">**Type**</span></span>|<span data-ttu-id="5f5ea-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="5f5ea-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5f5ea-127">AuthorEntry</span><span class="sxs-lookup"><span data-stu-id="5f5ea-127">AuthorEntry</span></span>](authorentry-element-authorlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5f5ea-128">AuthorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="5f5ea-128">AuthorEntry_Type</span></span>](authorentry_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="5f5ea-129">指定标识的绘图中的注释作者的属性。</span><span class="sxs-lookup"><span data-stu-id="5f5ea-129">Specifies the properties that identify the author of a comment in a drawing.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="5f5ea-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="5f5ea-130">Attributes</span></span>

<span data-ttu-id="5f5ea-131">无。</span><span class="sxs-lookup"><span data-stu-id="5f5ea-131">None.</span></span>
  

