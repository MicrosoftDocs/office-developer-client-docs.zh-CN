---
title: 连接元素 (PageContents_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 398c141c-8a40-7605-254a-2ee7cc0a7af5
description: 包含绘图中两个形状之间的每个连接的 Connect 元素。
ms.openlocfilehash: 00bba6be8b32fc2a8e1d996e89c6983e1e61e3a8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318961"
---
# <a name="connects-element-pagecontentstype-complextype-visio-xml"></a><span data-ttu-id="2b724-103">连接元素 (PageContents_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="2b724-103">Connects element (PageContents_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="2b724-104">包含绘图中两个形状之间的每个连接的**Connect**元素。</span><span class="sxs-lookup"><span data-stu-id="2b724-104">Contains a **Connect** element for each connection between two shapes in a drawing.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="2b724-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="2b724-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2b724-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="2b724-106">**Element type**</span></span> <br/> |[<span data-ttu-id="2b724-107">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="2b724-107">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="2b724-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2b724-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="2b724-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2b724-109">**Schema file**</span></span> <br/> |<span data-ttu-id="2b724-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="2b724-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="2b724-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="2b724-111">**Document parts**</span></span> <br/> |<span data-ttu-id="2b724-112">页面 # .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="2b724-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2b724-113">定义</span><span class="sxs-lookup"><span data-stu-id="2b724-113">Definition</span></span>

```XML
< xs:element name="Connects" type="Connects_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="2b724-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2b724-114">Elements and attributes</span></span>

<span data-ttu-id="2b724-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="2b724-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="2b724-116">父元素</span><span class="sxs-lookup"><span data-stu-id="2b724-116">Parent elements</span></span>

|<span data-ttu-id="2b724-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="2b724-117">**Element**</span></span>|<span data-ttu-id="2b724-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="2b724-118">**Type**</span></span>|<span data-ttu-id="2b724-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="2b724-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2b724-120">MasterContents</span><span class="sxs-lookup"><span data-stu-id="2b724-120">MasterContents</span></span>](mastercontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="2b724-121">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="2b724-121">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="2b724-122">指定有关绘图的主控形状或绘图页中的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="2b724-122">Specifies the information about the shapes in a master or drawing page of a drawing.</span></span>  <br/> |
|[<span data-ttu-id="2b724-123">PageContents</span><span class="sxs-lookup"><span data-stu-id="2b724-123">PageContents</span></span>](pagecontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="2b724-124">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="2b724-124">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="2b724-125">指定有关绘图的主控形状或绘图页中的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="2b724-125">Specifies the information about the shapes in a master or drawing page of a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="2b724-126">子元素</span><span class="sxs-lookup"><span data-stu-id="2b724-126">Child elements</span></span>

|<span data-ttu-id="2b724-127">**元素**</span><span class="sxs-lookup"><span data-stu-id="2b724-127">**Element**</span></span>|<span data-ttu-id="2b724-128">**类型**</span><span class="sxs-lookup"><span data-stu-id="2b724-128">**Type**</span></span>|<span data-ttu-id="2b724-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="2b724-129">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2b724-130">Connect</span><span class="sxs-lookup"><span data-stu-id="2b724-130">Connect</span></span>](connect-element-connects_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2b724-131">Connect_Type</span><span class="sxs-lookup"><span data-stu-id="2b724-131">Connect_Type</span></span>](connect_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="2b724-132">表示绘图中的两个形状间的连接，如组织结构图中的线和框。</span><span class="sxs-lookup"><span data-stu-id="2b724-132">Represents a connection between two shapes in a drawing, such as a line and a box in an organization chart.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="2b724-133">Attributes</span><span class="sxs-lookup"><span data-stu-id="2b724-133">Attributes</span></span>

<span data-ttu-id="2b724-134">无。</span><span class="sxs-lookup"><span data-stu-id="2b724-134">None.</span></span>
  

