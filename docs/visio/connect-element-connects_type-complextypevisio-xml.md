---
title: Connect 元素 (Connects_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6e1ad47b-ee28-6b9a-f2f9-642e09ca28d4
description: 表示绘图中的两个形状间的连接，如组织结构图中的线和框。
ms.openlocfilehash: 3450a07e042fc633b9cd4952d9b3ad6b8190ed1e
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541993"
---
# <a name="connect-element-connectstype-complextype-visio-xml"></a><span data-ttu-id="7ce17-103">Connect 元素 (Connects_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="7ce17-103">Connect element (Connects_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="7ce17-104">表示绘图中的两个形状间的连接，如组织结构图中的线和框。</span><span class="sxs-lookup"><span data-stu-id="7ce17-104">Represents a connection between two shapes in a drawing, such as a line and a box in an organization chart.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="7ce17-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="7ce17-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7ce17-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="7ce17-106">**Element type**</span></span> <br/> |[<span data-ttu-id="7ce17-107">Connect_Type</span><span class="sxs-lookup"><span data-stu-id="7ce17-107">Connect_Type</span></span>](connect_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="7ce17-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="7ce17-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="7ce17-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="7ce17-109">**Schema file**</span></span> <br/> |<span data-ttu-id="7ce17-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="7ce17-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="7ce17-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="7ce17-111">**Document parts**</span></span> <br/> |<span data-ttu-id="7ce17-112">页面 # .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="7ce17-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="7ce17-113">定义</span><span class="sxs-lookup"><span data-stu-id="7ce17-113">Definition</span></span>

```XML
< xs:element name="Connect" type="Connect_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="7ce17-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="7ce17-114">Elements and attributes</span></span>

<span data-ttu-id="7ce17-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="7ce17-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="7ce17-116">父元素</span><span class="sxs-lookup"><span data-stu-id="7ce17-116">Parent elements</span></span>

|<span data-ttu-id="7ce17-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="7ce17-117">**Element**</span></span>|<span data-ttu-id="7ce17-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="7ce17-118">**Type**</span></span>|<span data-ttu-id="7ce17-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ce17-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7ce17-120">Connects</span><span class="sxs-lookup"><span data-stu-id="7ce17-120">Connects</span></span>](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="7ce17-121">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="7ce17-121">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7ce17-122">包含绘图中两个形状之间的每个连接的**Connect**元素。</span><span class="sxs-lookup"><span data-stu-id="7ce17-122">Contains a **Connect** element for each connection between two shapes in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="7ce17-123">子元素</span><span class="sxs-lookup"><span data-stu-id="7ce17-123">Child elements</span></span>

<span data-ttu-id="7ce17-124">无。</span><span class="sxs-lookup"><span data-stu-id="7ce17-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="7ce17-125">属性</span><span class="sxs-lookup"><span data-stu-id="7ce17-125">Attributes</span></span>

|<span data-ttu-id="7ce17-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="7ce17-126">**Attribute**</span></span>|<span data-ttu-id="7ce17-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="7ce17-127">**Type**</span></span>|<span data-ttu-id="7ce17-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="7ce17-128">**Required**</span></span>|<span data-ttu-id="7ce17-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="7ce17-129">**Description**</span></span>|<span data-ttu-id="7ce17-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="7ce17-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ce17-131">FromCell</span><span class="sxs-lookup"><span data-stu-id="7ce17-131">FromCell</span></span>  <br/> |<span data-ttu-id="7ce17-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="7ce17-132">xsd:string</span></span>  <br/> |<span data-ttu-id="7ce17-133">可选</span><span class="sxs-lookup"><span data-stu-id="7ce17-133">optional</span></span>  <br/> |<span data-ttu-id="7ce17-134">从中发起连接的单元格。</span><span class="sxs-lookup"><span data-stu-id="7ce17-134">The cell from which a connection originates.</span></span>  <br/> |<span data-ttu-id="7ce17-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="7ce17-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="7ce17-136">FromPart</span><span class="sxs-lookup"><span data-stu-id="7ce17-136">FromPart</span></span>  <br/> |<span data-ttu-id="7ce17-137">xsd: int</span><span class="sxs-lookup"><span data-stu-id="7ce17-137">xsd:int</span></span>  <br/> |<span data-ttu-id="7ce17-138">可选</span><span class="sxs-lookup"><span data-stu-id="7ce17-138">optional</span></span>  <br/> |<span data-ttu-id="7ce17-139">从其发起连接的形状的部件。</span><span class="sxs-lookup"><span data-stu-id="7ce17-139">The part of a shape from which a connection originates.</span></span>  <br/> |<span data-ttu-id="7ce17-140">Xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="7ce17-140">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="7ce17-141">FromSheet</span><span class="sxs-lookup"><span data-stu-id="7ce17-141">FromSheet</span></span>  <br/> |<span data-ttu-id="7ce17-142">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="7ce17-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="7ce17-143">必需</span><span class="sxs-lookup"><span data-stu-id="7ce17-143">required</span></span>  <br/> |<span data-ttu-id="7ce17-144">从中发起连接或连接的形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="7ce17-144">The ID of the shape from which a connection or connections originate.</span></span>  <br/> |<span data-ttu-id="7ce17-145">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="7ce17-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="7ce17-146">ToCell</span><span class="sxs-lookup"><span data-stu-id="7ce17-146">ToCell</span></span>  <br/> |<span data-ttu-id="7ce17-147">xsd: string</span><span class="sxs-lookup"><span data-stu-id="7ce17-147">xsd:string</span></span>  <br/> |<span data-ttu-id="7ce17-148">可选</span><span class="sxs-lookup"><span data-stu-id="7ce17-148">optional</span></span>  <br/> |<span data-ttu-id="7ce17-149">建立了连接的单元格。</span><span class="sxs-lookup"><span data-stu-id="7ce17-149">The cell to which a connection is made.</span></span>  <br/> |<span data-ttu-id="7ce17-150">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="7ce17-150">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="7ce17-151">ToPart</span><span class="sxs-lookup"><span data-stu-id="7ce17-151">ToPart</span></span>  <br/> |<span data-ttu-id="7ce17-152">xsd: int</span><span class="sxs-lookup"><span data-stu-id="7ce17-152">xsd:int</span></span>  <br/> |<span data-ttu-id="7ce17-153">可选</span><span class="sxs-lookup"><span data-stu-id="7ce17-153">optional</span></span>  <br/> |<span data-ttu-id="7ce17-154">建立了连接的形状的一部分。</span><span class="sxs-lookup"><span data-stu-id="7ce17-154">The part of a shape to which a connection is made.</span></span>  <br/> |<span data-ttu-id="7ce17-155">Xsd: Int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="7ce17-155">Values of the xsd:Int type.</span></span>  <br/> |
|<span data-ttu-id="7ce17-156">ToSheet</span><span class="sxs-lookup"><span data-stu-id="7ce17-156">ToSheet</span></span>  <br/> |<span data-ttu-id="7ce17-157">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="7ce17-157">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="7ce17-158">必需</span><span class="sxs-lookup"><span data-stu-id="7ce17-158">required</span></span>  <br/> |<span data-ttu-id="7ce17-159">建立了一个或多个连接的形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="7ce17-159">The ID of the shape to which one or more connections are made.</span></span>  <br/> |<span data-ttu-id="7ce17-160">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="7ce17-160">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

