---
title: MasterContents 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 71e75e9a-1392-b40b-1d51-167cd28b2c53
description: 指定绘图中的主控形状中的形状的有关信息。
ms.openlocfilehash: d1ba67a414ac80be9da2beebb93acc89faf71172
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780695"
---
# <a name="mastercontents-element-visio-xml"></a><span data-ttu-id="ee4aa-103">MasterContents 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="ee4aa-103">MasterContents element ('Visio XML')</span></span>

<span data-ttu-id="ee4aa-104">指定绘图中的主控形状中的形状的有关信息。</span><span class="sxs-lookup"><span data-stu-id="ee4aa-104">Specifies information about the shapes in a master in a drawing.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="ee4aa-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="ee4aa-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ee4aa-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="ee4aa-106">**Element type**</span></span> <br/> |[<span data-ttu-id="ee4aa-107">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="ee4aa-107">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="ee4aa-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ee4aa-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="ee4aa-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ee4aa-109">**Schema file**</span></span> <br/> |<span data-ttu-id="ee4aa-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="ee4aa-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="ee4aa-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="ee4aa-111">**Document parts**</span></span> <br/> |<span data-ttu-id="ee4aa-112">主 #.xml</span><span class="sxs-lookup"><span data-stu-id="ee4aa-112">master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ee4aa-113">定义</span><span class="sxs-lookup"><span data-stu-id="ee4aa-113">Definition</span></span>

```XML
< xs:element name="MasterContents" type="PageContents_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="ee4aa-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ee4aa-114">Elements and attributes</span></span>

<span data-ttu-id="ee4aa-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ee4aa-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="ee4aa-116">父元素</span><span class="sxs-lookup"><span data-stu-id="ee4aa-116">Parent elements</span></span>

<span data-ttu-id="ee4aa-117">无。</span><span class="sxs-lookup"><span data-stu-id="ee4aa-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="ee4aa-118">子元素</span><span class="sxs-lookup"><span data-stu-id="ee4aa-118">Child elements</span></span>

|<span data-ttu-id="ee4aa-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="ee4aa-119">**Element**</span></span>|<span data-ttu-id="ee4aa-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="ee4aa-120">**Type**</span></span>|<span data-ttu-id="ee4aa-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="ee4aa-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ee4aa-122">连接</span><span class="sxs-lookup"><span data-stu-id="ee4aa-122">Connects</span></span>](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="ee4aa-123">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="ee4aa-123">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="ee4aa-124">包含与绘图中的两个形状间的每个连接的**Connect**元素。</span><span class="sxs-lookup"><span data-stu-id="ee4aa-124">Contains a **Connect** element for each connection between two shapes in a drawing.</span></span>  <br/> |
|[<span data-ttu-id="ee4aa-125">Shapes</span><span class="sxs-lookup"><span data-stu-id="ee4aa-125">Shapes</span></span>](shapes-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="ee4aa-126">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="ee4aa-126">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="ee4aa-127">包含**形状**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="ee4aa-127">Contains a collection of **Shape** elements.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="ee4aa-128">属性</span><span class="sxs-lookup"><span data-stu-id="ee4aa-128">Attributes</span></span>

<span data-ttu-id="ee4aa-129">无。</span><span class="sxs-lookup"><span data-stu-id="ee4aa-129">None.</span></span>
  

