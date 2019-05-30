---
title: 连接元素 (PageContents_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 398c141c-8a40-7605-254a-2ee7cc0a7af5
description: 包含绘图中两个形状之间的每个连接的 Connect 元素。
ms.openlocfilehash: d421068926a40a8f7c24a783388d06091700211f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538709"
---
# <a name="connects-element-pagecontentstype-complextype-visio-xml"></a><span data-ttu-id="318df-103">连接元素 (PageContents_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="318df-103">Connects element (PageContents_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="318df-104">包含绘图中两个形状之间的每个连接的**Connect**元素。</span><span class="sxs-lookup"><span data-stu-id="318df-104">Contains a **Connect** element for each connection between two shapes in a drawing.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="318df-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="318df-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="318df-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="318df-106">**Element type**</span></span> <br/> |[<span data-ttu-id="318df-107">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="318df-107">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="318df-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="318df-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="318df-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="318df-109">**Schema file**</span></span> <br/> |<span data-ttu-id="318df-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="318df-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="318df-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="318df-111">**Document parts**</span></span> <br/> |<span data-ttu-id="318df-112">页面 # .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="318df-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="318df-113">定义</span><span class="sxs-lookup"><span data-stu-id="318df-113">Definition</span></span>

```XML
< xs:element name="Connects" type="Connects_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="318df-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="318df-114">Elements and attributes</span></span>

<span data-ttu-id="318df-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="318df-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="318df-116">父元素</span><span class="sxs-lookup"><span data-stu-id="318df-116">Parent elements</span></span>

|<span data-ttu-id="318df-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="318df-117">**Element**</span></span>|<span data-ttu-id="318df-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="318df-118">**Type**</span></span>|<span data-ttu-id="318df-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="318df-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="318df-120">MasterContents</span><span class="sxs-lookup"><span data-stu-id="318df-120">MasterContents</span></span>](mastercontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="318df-121">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="318df-121">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="318df-122">指定有关绘图的主控形状或绘图页中的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="318df-122">Specifies the information about the shapes in a master or drawing page of a drawing.</span></span>  <br/> |
|[<span data-ttu-id="318df-123">PageContents</span><span class="sxs-lookup"><span data-stu-id="318df-123">PageContents</span></span>](pagecontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="318df-124">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="318df-124">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="318df-125">指定有关绘图的主控形状或绘图页中的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="318df-125">Specifies the information about the shapes in a master or drawing page of a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="318df-126">子元素</span><span class="sxs-lookup"><span data-stu-id="318df-126">Child elements</span></span>

|<span data-ttu-id="318df-127">**元素**</span><span class="sxs-lookup"><span data-stu-id="318df-127">**Element**</span></span>|<span data-ttu-id="318df-128">**类型**</span><span class="sxs-lookup"><span data-stu-id="318df-128">**Type**</span></span>|<span data-ttu-id="318df-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="318df-129">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="318df-130">Connect</span><span class="sxs-lookup"><span data-stu-id="318df-130">Connect</span></span>](connect-element-connects_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="318df-131">Connect_Type</span><span class="sxs-lookup"><span data-stu-id="318df-131">Connect_Type</span></span>](connect_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="318df-132">表示绘图中的两个形状间的连接，如组织结构图中的线和框。</span><span class="sxs-lookup"><span data-stu-id="318df-132">Represents a connection between two shapes in a drawing, such as a line and a box in an organization chart.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="318df-133">Attributes</span><span class="sxs-lookup"><span data-stu-id="318df-133">Attributes</span></span>

<span data-ttu-id="318df-134">无。</span><span class="sxs-lookup"><span data-stu-id="318df-134">None.</span></span>
  

