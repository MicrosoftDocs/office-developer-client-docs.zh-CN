---
title: MasterContents 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 71e75e9a-1392-b40b-1d51-167cd28b2c53
description: 指定绘图中的主控形状中的形状的有关信息。
ms.openlocfilehash: 381afe288864553dc56bdf8bb6dc19861abdcc8f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385464"
---
# <a name="mastercontents-element-visio-xml"></a><span data-ttu-id="f9ddf-103">MasterContents 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f9ddf-103">MasterContents element ('Visio XML')</span></span>

<span data-ttu-id="f9ddf-104">指定绘图中的主控形状中的形状的有关信息。</span><span class="sxs-lookup"><span data-stu-id="f9ddf-104">Specifies information about the shapes in a master in a drawing.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="f9ddf-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="f9ddf-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f9ddf-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="f9ddf-106">**Element type**</span></span> <br/> |[<span data-ttu-id="f9ddf-107">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="f9ddf-107">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="f9ddf-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f9ddf-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="f9ddf-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f9ddf-109">**Schema file**</span></span> <br/> |<span data-ttu-id="f9ddf-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="f9ddf-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="f9ddf-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="f9ddf-111">**Document parts**</span></span> <br/> |<span data-ttu-id="f9ddf-112">主 #.xml</span><span class="sxs-lookup"><span data-stu-id="f9ddf-112">master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f9ddf-113">定义</span><span class="sxs-lookup"><span data-stu-id="f9ddf-113">Definition</span></span>

```XML
< xs:element name="MasterContents" type="PageContents_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f9ddf-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f9ddf-114">Elements and attributes</span></span>

<span data-ttu-id="f9ddf-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f9ddf-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="f9ddf-116">父元素</span><span class="sxs-lookup"><span data-stu-id="f9ddf-116">Parent elements</span></span>

<span data-ttu-id="f9ddf-117">无。</span><span class="sxs-lookup"><span data-stu-id="f9ddf-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f9ddf-118">子元素</span><span class="sxs-lookup"><span data-stu-id="f9ddf-118">Child elements</span></span>

|<span data-ttu-id="f9ddf-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="f9ddf-119">**Element**</span></span>|<span data-ttu-id="f9ddf-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="f9ddf-120">**Type**</span></span>|<span data-ttu-id="f9ddf-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9ddf-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f9ddf-122">Connects</span><span class="sxs-lookup"><span data-stu-id="f9ddf-122">Connects</span></span>](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f9ddf-123">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="f9ddf-123">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f9ddf-124">包含与绘图中的两个形状间的每个连接的**Connect**元素。</span><span class="sxs-lookup"><span data-stu-id="f9ddf-124">Contains a **Connect** element for each connection between two shapes in a drawing.</span></span>  <br/> |
|[<span data-ttu-id="f9ddf-125">Shapes</span><span class="sxs-lookup"><span data-stu-id="f9ddf-125">Shapes</span></span>](shapes-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f9ddf-126">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="f9ddf-126">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f9ddf-127">包含**形状**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="f9ddf-127">Contains a collection of **Shape** elements.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="f9ddf-128">Attributes</span><span class="sxs-lookup"><span data-stu-id="f9ddf-128">Attributes</span></span>

<span data-ttu-id="f9ddf-129">无。</span><span class="sxs-lookup"><span data-stu-id="f9ddf-129">None.</span></span>
  

