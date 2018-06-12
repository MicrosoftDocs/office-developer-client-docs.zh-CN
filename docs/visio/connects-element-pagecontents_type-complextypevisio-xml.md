---
title: 连接元素 （PageContents_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 398c141c-8a40-7605-254a-2ee7cc0a7af5
description: 包含与绘图中的两个形状间的每个连接的 Connect 元素。
ms.openlocfilehash: 93930a8f21f9d250bf24d821b0eeb4036f6fe187
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779968"
---
# <a name="connects-element-pagecontentstype-complextype-visio-xml"></a><span data-ttu-id="02c77-103">连接元素 （PageContents_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="02c77-103">Connects element (PageContents_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="02c77-104">包含与绘图中的两个形状间的每个连接的**Connect**元素。</span><span class="sxs-lookup"><span data-stu-id="02c77-104">Contains a **Connect** element for each connection between two shapes in a drawing.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="02c77-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="02c77-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="02c77-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="02c77-106">**Element type**</span></span> <br/> |[<span data-ttu-id="02c77-107">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="02c77-107">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="02c77-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="02c77-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="02c77-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="02c77-109">**Schema file**</span></span> <br/> |<span data-ttu-id="02c77-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="02c77-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="02c77-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="02c77-111">**Document parts**</span></span> <br/> |<span data-ttu-id="02c77-112">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="02c77-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="02c77-113">定义</span><span class="sxs-lookup"><span data-stu-id="02c77-113">Definition</span></span>

```XML
< xs:element name="Connects" type="Connects_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="02c77-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="02c77-114">Elements and attributes</span></span>

<span data-ttu-id="02c77-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="02c77-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="02c77-116">父元素</span><span class="sxs-lookup"><span data-stu-id="02c77-116">Parent elements</span></span>

|<span data-ttu-id="02c77-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="02c77-117">**Element**</span></span>|<span data-ttu-id="02c77-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="02c77-118">**Type**</span></span>|<span data-ttu-id="02c77-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="02c77-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="02c77-120">MasterContents</span><span class="sxs-lookup"><span data-stu-id="02c77-120">MasterContents</span></span>](mastercontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="02c77-121">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="02c77-121">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="02c77-122">指定绘图的主控形状或绘图页中的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="02c77-122">Specifies the information about the shapes in a master or drawing page of a drawing.</span></span>  <br/> |
|[<span data-ttu-id="02c77-123">PageContents</span><span class="sxs-lookup"><span data-stu-id="02c77-123">PageContents</span></span>](pagecontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="02c77-124">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="02c77-124">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="02c77-125">指定绘图的主控形状或绘图页中的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="02c77-125">Specifies the information about the shapes in a master or drawing page of a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="02c77-126">子元素</span><span class="sxs-lookup"><span data-stu-id="02c77-126">Child elements</span></span>

|<span data-ttu-id="02c77-127">**元素**</span><span class="sxs-lookup"><span data-stu-id="02c77-127">**Element**</span></span>|<span data-ttu-id="02c77-128">**类型**</span><span class="sxs-lookup"><span data-stu-id="02c77-128">**Type**</span></span>|<span data-ttu-id="02c77-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="02c77-129">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="02c77-130">Connect</span><span class="sxs-lookup"><span data-stu-id="02c77-130">Connect</span></span>](connect-element-connects_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="02c77-131">Connect_Type</span><span class="sxs-lookup"><span data-stu-id="02c77-131">Connect_Type</span></span>](connect_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="02c77-132">代表在绘图中，如的线和框组织结构图中的两个形状间的连接。</span><span class="sxs-lookup"><span data-stu-id="02c77-132">Represents a connection between two shapes in a drawing, such as a line and a box in an organization chart.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="02c77-133">属性</span><span class="sxs-lookup"><span data-stu-id="02c77-133">Attributes</span></span>

<span data-ttu-id="02c77-134">无。</span><span class="sxs-lookup"><span data-stu-id="02c77-134">None.</span></span>
  

