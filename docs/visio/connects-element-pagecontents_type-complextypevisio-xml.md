---
title: 'Connects 元素 (PageContents_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 398c141c-8a40-7605-254a-2ee7cc0a7af5
description: 包含一连接图形中两个形状之间的每个连接的一个属性元素。
ms.openlocfilehash: d421068926a40a8f7c24a783388d06091700211f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538709"
---
# <a name="connects-element-pagecontents_type-complextype-visio-xml"></a><span data-ttu-id="c4c00-103">Connects 元素 (PageContents_Type complexType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="c4c00-103">Connects element (PageContents_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="c4c00-104">包含一 **连接** 图形中两个形状之间的每个连接的一个属性元素。</span><span class="sxs-lookup"><span data-stu-id="c4c00-104">Contains a **Connect** element for each connection between two shapes in a drawing.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="c4c00-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="c4c00-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c4c00-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="c4c00-106">**Element type**</span></span> <br/> |[<span data-ttu-id="c4c00-107">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="c4c00-107">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="c4c00-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c4c00-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="c4c00-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c4c00-109">**Schema file**</span></span> <br/> |<span data-ttu-id="c4c00-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="c4c00-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="c4c00-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="c4c00-111">**Document parts**</span></span> <br/> |<span data-ttu-id="c4c00-112">page#.xml，master#.xml</span><span class="sxs-lookup"><span data-stu-id="c4c00-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c4c00-113">定义</span><span class="sxs-lookup"><span data-stu-id="c4c00-113">Definition</span></span>

```XML
< xs:element name="Connects" type="Connects_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c4c00-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c4c00-114">Elements and attributes</span></span>

<span data-ttu-id="c4c00-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="c4c00-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="c4c00-116">父元素</span><span class="sxs-lookup"><span data-stu-id="c4c00-116">Parent elements</span></span>

|<span data-ttu-id="c4c00-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="c4c00-117">**Element**</span></span>|<span data-ttu-id="c4c00-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="c4c00-118">**Type**</span></span>|<span data-ttu-id="c4c00-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="c4c00-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c4c00-120">MasterContents</span><span class="sxs-lookup"><span data-stu-id="c4c00-120">MasterContents</span></span>](mastercontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="c4c00-121">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="c4c00-121">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c4c00-122">指定有关绘图的主控形状或绘图页中形状的信息。</span><span class="sxs-lookup"><span data-stu-id="c4c00-122">Specifies the information about the shapes in a master or drawing page of a drawing.</span></span>  <br/> |
|[<span data-ttu-id="c4c00-123">PageContents</span><span class="sxs-lookup"><span data-stu-id="c4c00-123">PageContents</span></span>](pagecontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="c4c00-124">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="c4c00-124">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c4c00-125">指定有关绘图的主控形状或绘图页中形状的信息。</span><span class="sxs-lookup"><span data-stu-id="c4c00-125">Specifies the information about the shapes in a master or drawing page of a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="c4c00-126">子元素</span><span class="sxs-lookup"><span data-stu-id="c4c00-126">Child elements</span></span>

|<span data-ttu-id="c4c00-127">**元素**</span><span class="sxs-lookup"><span data-stu-id="c4c00-127">**Element**</span></span>|<span data-ttu-id="c4c00-128">**类型**</span><span class="sxs-lookup"><span data-stu-id="c4c00-128">**Type**</span></span>|<span data-ttu-id="c4c00-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="c4c00-129">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c4c00-130">Connect</span><span class="sxs-lookup"><span data-stu-id="c4c00-130">Connect</span></span>](connect-element-connects_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c4c00-131">Connect_Type</span><span class="sxs-lookup"><span data-stu-id="c4c00-131">Connect_Type</span></span>](connect_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c4c00-132">表示绘图中的两个形状间的连接，如组织结构图中的线和框。</span><span class="sxs-lookup"><span data-stu-id="c4c00-132">Represents a connection between two shapes in a drawing, such as a line and a box in an organization chart.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="c4c00-133">Attributes</span><span class="sxs-lookup"><span data-stu-id="c4c00-133">Attributes</span></span>

<span data-ttu-id="c4c00-134">无。</span><span class="sxs-lookup"><span data-stu-id="c4c00-134">None.</span></span>
  

