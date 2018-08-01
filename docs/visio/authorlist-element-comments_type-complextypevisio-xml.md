---
title: AuthorList 元素 （Comments_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4b6950c4-7c03-6462-eeab-3176db9a8f7e
description: 指定与绘图中的注释作者。
ms.openlocfilehash: 0f31e11e52809df60b41cb67b868b15435e0eb47
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779684"
---
# <a name="authorlist-element-commentstype-complextype-visio-xml"></a><span data-ttu-id="26a54-103">AuthorList 元素 （Comments_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="26a54-103">AuthorList element (Comments_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="26a54-104">指定与绘图中的注释作者。</span><span class="sxs-lookup"><span data-stu-id="26a54-104">Specifies the authors of comments in a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="26a54-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="26a54-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="26a54-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="26a54-106">**Element type**</span></span> <br/> |[<span data-ttu-id="26a54-107">AuthorList_Type</span><span class="sxs-lookup"><span data-stu-id="26a54-107">AuthorList_Type</span></span>](authorlist_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="26a54-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="26a54-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="26a54-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="26a54-109">**Schema file**</span></span> <br/> |<span data-ttu-id="26a54-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="26a54-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="26a54-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="26a54-111">**Document parts**</span></span> <br/> |<span data-ttu-id="26a54-112">comments.xml</span><span class="sxs-lookup"><span data-stu-id="26a54-112">comments.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="26a54-113">定义</span><span class="sxs-lookup"><span data-stu-id="26a54-113">Definition</span></span>

```XML
< xs:element name="AuthorList" type="AuthorList_Type" minOccurs="0" maxOccurs="1" >
< /xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="26a54-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="26a54-114">Elements and attributes</span></span>

<span data-ttu-id="26a54-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="26a54-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="26a54-116">父元素</span><span class="sxs-lookup"><span data-stu-id="26a54-116">Parent elements</span></span>

|<span data-ttu-id="26a54-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="26a54-117">**Element**</span></span>|<span data-ttu-id="26a54-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="26a54-118">**Type**</span></span>|<span data-ttu-id="26a54-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="26a54-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="26a54-120">Comments</span><span class="sxs-lookup"><span data-stu-id="26a54-120">Comments</span></span>](comments-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="26a54-121">Comments_Type</span><span class="sxs-lookup"><span data-stu-id="26a54-121">Comments_Type</span></span>](comments_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="26a54-122">指定与绘图中的注释。</span><span class="sxs-lookup"><span data-stu-id="26a54-122">Specifies the comments in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="26a54-123">子元素</span><span class="sxs-lookup"><span data-stu-id="26a54-123">Child elements</span></span>

|<span data-ttu-id="26a54-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="26a54-124">**Element**</span></span>|<span data-ttu-id="26a54-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="26a54-125">**Type**</span></span>|<span data-ttu-id="26a54-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="26a54-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="26a54-127">AuthorEntry</span><span class="sxs-lookup"><span data-stu-id="26a54-127">AuthorEntry</span></span>](authorentry-element-authorlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="26a54-128">AuthorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="26a54-128">AuthorEntry_Type</span></span>](authorentry_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="26a54-129">指定标识的绘图中的注释作者的属性。</span><span class="sxs-lookup"><span data-stu-id="26a54-129">Specifies the properties that identify the author of a comment in a drawing.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="26a54-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="26a54-130">Attributes</span></span>

<span data-ttu-id="26a54-131">无。</span><span class="sxs-lookup"><span data-stu-id="26a54-131">None.</span></span>
  

