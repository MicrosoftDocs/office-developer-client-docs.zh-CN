---
title: 'CommentList 元素 (Comments_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 49fee70d-6556-887b-003f-4f56916d541d
description: 指定绘图中的注释。
ms.openlocfilehash: fbbc7ea668686a8f075f3f11843b2d828c257363
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539246"
---
# <a name="commentlist-element-comments_type-complextype-visio-xml"></a><span data-ttu-id="863a0-103">CommentList 元素 (Comments_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="863a0-103">CommentList element (Comments_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="863a0-104">指定绘图中的注释。</span><span class="sxs-lookup"><span data-stu-id="863a0-104">Specifies the comments in a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="863a0-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="863a0-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="863a0-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="863a0-106">**Element type**</span></span> <br/> |[<span data-ttu-id="863a0-107">CommentList_Type</span><span class="sxs-lookup"><span data-stu-id="863a0-107">CommentList_Type</span></span>](commentlist_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="863a0-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="863a0-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="863a0-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="863a0-109">**Schema file**</span></span> <br/> |<span data-ttu-id="863a0-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="863a0-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="863a0-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="863a0-111">**Document parts**</span></span> <br/> |<span data-ttu-id="863a0-112">comments.xml</span><span class="sxs-lookup"><span data-stu-id="863a0-112">comments.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="863a0-113">定义</span><span class="sxs-lookup"><span data-stu-id="863a0-113">Definition</span></span>

```XML
< xs:element name="CommentList" type="CommentList_Type" minOccurs="0" maxOccurs="1" >
< /xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="863a0-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="863a0-114">Elements and attributes</span></span>

<span data-ttu-id="863a0-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="863a0-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="863a0-116">父元素</span><span class="sxs-lookup"><span data-stu-id="863a0-116">Parent elements</span></span>

|<span data-ttu-id="863a0-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="863a0-117">**Element**</span></span>|<span data-ttu-id="863a0-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="863a0-118">**Type**</span></span>|<span data-ttu-id="863a0-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="863a0-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="863a0-120">备注</span><span class="sxs-lookup"><span data-stu-id="863a0-120">Comments</span></span>](comments-element-comments_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="863a0-121">Comments_Type</span><span class="sxs-lookup"><span data-stu-id="863a0-121">Comments_Type</span></span>](comments_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="863a0-122">指定用于标识绘图中的作者和注释的属性。</span><span class="sxs-lookup"><span data-stu-id="863a0-122">Specifies properties used to identify the authors and comments in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="863a0-123">子元素</span><span class="sxs-lookup"><span data-stu-id="863a0-123">Child elements</span></span>

|<span data-ttu-id="863a0-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="863a0-124">**Element**</span></span>|<span data-ttu-id="863a0-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="863a0-125">**Type**</span></span>|<span data-ttu-id="863a0-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="863a0-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="863a0-127">CommentEntry</span><span class="sxs-lookup"><span data-stu-id="863a0-127">CommentEntry</span></span>](commententry-element-commentlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="863a0-128">CommentEntry_Type</span><span class="sxs-lookup"><span data-stu-id="863a0-128">CommentEntry_Type</span></span>](commententry_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="863a0-129">指定用于标识绘图中的批注的属性。</span><span class="sxs-lookup"><span data-stu-id="863a0-129">Specifies properties used to identify a comment in a drawing.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="863a0-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="863a0-130">Attributes</span></span>

<span data-ttu-id="863a0-131">无。</span><span class="sxs-lookup"><span data-stu-id="863a0-131">None.</span></span>
  

