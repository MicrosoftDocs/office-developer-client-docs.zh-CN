---
title: PageContents 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 818793d6-608e-5f23-eca2-55ce6667050b
description: 指定绘图的主控形状或绘图页中的形状的信息。
ms.openlocfilehash: aec860f4135e15f18436dba50986b0ad0e6ee9e2
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396566"
---
# <a name="pagecontents-element-visio-xml"></a><span data-ttu-id="771f7-103">PageContents 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="771f7-103">PageContents element ('Visio XML')</span></span>

<span data-ttu-id="771f7-104">指定绘图的主控形状或绘图页中的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="771f7-104">Specifies the information about the shapes in a master or drawing page of a drawing.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="771f7-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="771f7-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="771f7-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="771f7-106">**Element type**</span></span> <br/> |[<span data-ttu-id="771f7-107">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="771f7-107">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="771f7-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="771f7-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="771f7-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="771f7-109">**Schema file**</span></span> <br/> |<span data-ttu-id="771f7-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="771f7-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="771f7-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="771f7-111">**Document parts**</span></span> <br/> |<span data-ttu-id="771f7-112">页 #.xml</span><span class="sxs-lookup"><span data-stu-id="771f7-112">page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="771f7-113">定义</span><span class="sxs-lookup"><span data-stu-id="771f7-113">Definition</span></span>

```XML
< xs:element name="PageContents" type="PageContents_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="771f7-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="771f7-114">Elements and attributes</span></span>

<span data-ttu-id="771f7-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="771f7-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="771f7-116">父元素</span><span class="sxs-lookup"><span data-stu-id="771f7-116">Parent elements</span></span>

<span data-ttu-id="771f7-117">无。</span><span class="sxs-lookup"><span data-stu-id="771f7-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="771f7-118">子元素</span><span class="sxs-lookup"><span data-stu-id="771f7-118">Child elements</span></span>

|<span data-ttu-id="771f7-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="771f7-119">**Element**</span></span>|<span data-ttu-id="771f7-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="771f7-120">**Type**</span></span>|<span data-ttu-id="771f7-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="771f7-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="771f7-122">Connects</span><span class="sxs-lookup"><span data-stu-id="771f7-122">Connects</span></span>](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="771f7-123">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="771f7-123">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="771f7-124">包含与绘图中的两个形状间的每个连接的**Connect**元素。</span><span class="sxs-lookup"><span data-stu-id="771f7-124">Contains a **Connect** element for each connection between two shapes in a drawing.</span></span>  <br/> |
|[<span data-ttu-id="771f7-125">Shapes</span><span class="sxs-lookup"><span data-stu-id="771f7-125">Shapes</span></span>](shapes-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="771f7-126">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="771f7-126">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="771f7-127">指定形状的集合。</span><span class="sxs-lookup"><span data-stu-id="771f7-127">Specifies a collection of shapes.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="771f7-128">Attributes</span><span class="sxs-lookup"><span data-stu-id="771f7-128">Attributes</span></span>

<span data-ttu-id="771f7-129">无。</span><span class="sxs-lookup"><span data-stu-id="771f7-129">None.</span></span>
  

