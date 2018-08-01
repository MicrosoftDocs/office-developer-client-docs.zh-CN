---
title: PageContents 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 818793d6-608e-5f23-eca2-55ce6667050b
description: 指定绘图的主控形状或绘图页中的形状的信息。
ms.openlocfilehash: 0ca705081ad42d799a0155b26eb42ff0b64cd7d7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780820"
---
# <a name="pagecontents-element-visio-xml"></a><span data-ttu-id="b339f-103">PageContents 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b339f-103">PageContents element ('Visio XML')</span></span>

<span data-ttu-id="b339f-104">指定绘图的主控形状或绘图页中的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="b339f-104">Specifies the information about the shapes in a master or drawing page of a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="b339f-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="b339f-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b339f-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="b339f-106">**Element type**</span></span> <br/> |[<span data-ttu-id="b339f-107">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="b339f-107">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="b339f-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b339f-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="b339f-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b339f-109">**Schema file**</span></span> <br/> |<span data-ttu-id="b339f-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="b339f-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="b339f-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="b339f-111">**Document parts**</span></span> <br/> |<span data-ttu-id="b339f-112">页 #.xml</span><span class="sxs-lookup"><span data-stu-id="b339f-112">page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b339f-113">定义</span><span class="sxs-lookup"><span data-stu-id="b339f-113">Definition</span></span>

```XML
< xs:element name="PageContents" type="PageContents_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b339f-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b339f-114">Elements and attributes</span></span>

<span data-ttu-id="b339f-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="b339f-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="b339f-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b339f-116">Parent elements</span></span>

<span data-ttu-id="b339f-117">无。</span><span class="sxs-lookup"><span data-stu-id="b339f-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="b339f-118">子元素</span><span class="sxs-lookup"><span data-stu-id="b339f-118">Child elements</span></span>

|<span data-ttu-id="b339f-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="b339f-119">**Element**</span></span>|<span data-ttu-id="b339f-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="b339f-120">**Type**</span></span>|<span data-ttu-id="b339f-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="b339f-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b339f-122">Connects</span><span class="sxs-lookup"><span data-stu-id="b339f-122">Connects</span></span>](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b339f-123">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="b339f-123">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b339f-124">包含与绘图中的两个形状间的每个连接的**Connect**元素。</span><span class="sxs-lookup"><span data-stu-id="b339f-124">Contains a **Connect** element for each connection between two shapes in a drawing.</span></span>  <br/> |
|[<span data-ttu-id="b339f-125">Shapes</span><span class="sxs-lookup"><span data-stu-id="b339f-125">Shapes</span></span>](shapes-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b339f-126">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="b339f-126">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b339f-127">指定形状的集合。</span><span class="sxs-lookup"><span data-stu-id="b339f-127">Specifies a collection of shapes.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="b339f-128">Attributes</span><span class="sxs-lookup"><span data-stu-id="b339f-128">Attributes</span></span>

<span data-ttu-id="b339f-129">无。</span><span class="sxs-lookup"><span data-stu-id="b339f-129">None.</span></span>
  

