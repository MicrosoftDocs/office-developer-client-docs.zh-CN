---
title: 连接元素 （Connects_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6e1ad47b-ee28-6b9a-f2f9-642e09ca28d4
description: "\n			表示绘图中的两个形状间的连接，如组织结构图中的线和框。\n"
ms.openlocfilehash: 82413f44f05f2ec6140e2b3981b7a1e8435becb0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399317"
---
# <a name="connect-element-connectstype-complextype-visio-xml"></a><span data-ttu-id="dbc3d-103">连接元素 （Connects_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="dbc3d-103">Connect element (Connects_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="dbc3d-104">
			表示绘图中的两个形状间的连接，如组织结构图中的线和框。
</span><span class="sxs-lookup"><span data-stu-id="dbc3d-104">Represents a connection between two shapes in a drawing, such as a line and a box in an organization chart.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="dbc3d-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="dbc3d-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="dbc3d-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="dbc3d-106">**Element type**</span></span> <br/> |[<span data-ttu-id="dbc3d-107">Connect_Type</span><span class="sxs-lookup"><span data-stu-id="dbc3d-107">Connect_Type</span></span>](connect_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="dbc3d-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="dbc3d-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="dbc3d-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="dbc3d-109">**Schema file**</span></span> <br/> |<span data-ttu-id="dbc3d-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="dbc3d-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="dbc3d-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="dbc3d-111">**Document parts**</span></span> <br/> |<span data-ttu-id="dbc3d-112">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="dbc3d-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="dbc3d-113">定义</span><span class="sxs-lookup"><span data-stu-id="dbc3d-113">Definition</span></span>

```XML
< xs:element name="Connect" type="Connect_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="dbc3d-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="dbc3d-114">Elements and attributes</span></span>

<span data-ttu-id="dbc3d-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="dbc3d-116">父元素</span><span class="sxs-lookup"><span data-stu-id="dbc3d-116">Parent elements</span></span>

|<span data-ttu-id="dbc3d-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="dbc3d-117">**Element**</span></span>|<span data-ttu-id="dbc3d-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="dbc3d-118">**Type**</span></span>|<span data-ttu-id="dbc3d-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="dbc3d-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="dbc3d-120">Connects</span><span class="sxs-lookup"><span data-stu-id="dbc3d-120">Connects</span></span>](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dbc3d-121">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="dbc3d-121">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="dbc3d-122">包含与绘图中的两个形状间的每个连接的**Connect**元素。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-122">Contains a **Connect** element for each connection between two shapes in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="dbc3d-123">子元素</span><span class="sxs-lookup"><span data-stu-id="dbc3d-123">Child elements</span></span>

<span data-ttu-id="dbc3d-124">无。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="dbc3d-125">属性</span><span class="sxs-lookup"><span data-stu-id="dbc3d-125">Attributes</span></span>

|<span data-ttu-id="dbc3d-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="dbc3d-126">**Attribute**</span></span>|<span data-ttu-id="dbc3d-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="dbc3d-127">**Type**</span></span>|<span data-ttu-id="dbc3d-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="dbc3d-128">**Required**</span></span>|<span data-ttu-id="dbc3d-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="dbc3d-129">**Description**</span></span>|<span data-ttu-id="dbc3d-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="dbc3d-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dbc3d-131">FromCell</span><span class="sxs-lookup"><span data-stu-id="dbc3d-131">FromCell</span></span>  <br/> |<span data-ttu-id="dbc3d-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="dbc3d-132">xsd:string</span></span>  <br/> |<span data-ttu-id="dbc3d-133">可选</span><span class="sxs-lookup"><span data-stu-id="dbc3d-133">optional</span></span>  <br/> |<span data-ttu-id="dbc3d-134">生成连接单元格。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-134">The cell from which a connection originates.</span></span>  <br/> |<span data-ttu-id="dbc3d-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="dbc3d-136">FromPart</span><span class="sxs-lookup"><span data-stu-id="dbc3d-136">FromPart</span></span>  <br/> |<span data-ttu-id="dbc3d-137">xsd:int</span><span class="sxs-lookup"><span data-stu-id="dbc3d-137">xsd:int</span></span>  <br/> |<span data-ttu-id="dbc3d-138">可选</span><span class="sxs-lookup"><span data-stu-id="dbc3d-138">optional</span></span>  <br/> |<span data-ttu-id="dbc3d-139">生成连接形状的一部分。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-139">The part of a shape from which a connection originates.</span></span>  <br/> |<span data-ttu-id="dbc3d-140">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-140">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="dbc3d-141">FromSheet</span><span class="sxs-lookup"><span data-stu-id="dbc3d-141">FromSheet</span></span>  <br/> |<span data-ttu-id="dbc3d-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="dbc3d-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="dbc3d-143">必需</span><span class="sxs-lookup"><span data-stu-id="dbc3d-143">required</span></span>  <br/> |<span data-ttu-id="dbc3d-144">从其连接源自形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-144">The ID of the shape from which a connection or connections originate.</span></span>  <br/> |<span data-ttu-id="dbc3d-145">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="dbc3d-146">ToCell</span><span class="sxs-lookup"><span data-stu-id="dbc3d-146">ToCell</span></span>  <br/> |<span data-ttu-id="dbc3d-147">xsd: string</span><span class="sxs-lookup"><span data-stu-id="dbc3d-147">xsd:string</span></span>  <br/> |<span data-ttu-id="dbc3d-148">可选</span><span class="sxs-lookup"><span data-stu-id="dbc3d-148">optional</span></span>  <br/> |<span data-ttu-id="dbc3d-149">单元格与其建立连接。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-149">The cell to which a connection is made.</span></span>  <br/> |<span data-ttu-id="dbc3d-150">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-150">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="dbc3d-151">ToPart</span><span class="sxs-lookup"><span data-stu-id="dbc3d-151">ToPart</span></span>  <br/> |<span data-ttu-id="dbc3d-152">xsd:int</span><span class="sxs-lookup"><span data-stu-id="dbc3d-152">xsd:int</span></span>  <br/> |<span data-ttu-id="dbc3d-153">可选</span><span class="sxs-lookup"><span data-stu-id="dbc3d-153">optional</span></span>  <br/> |<span data-ttu-id="dbc3d-154">对其进行连接的形状部分。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-154">The part of a shape to which a connection is made.</span></span>  <br/> |<span data-ttu-id="dbc3d-155">Xsd:Int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-155">Values of the xsd:Int type.</span></span>  <br/> |
|<span data-ttu-id="dbc3d-156">ToSheet</span><span class="sxs-lookup"><span data-stu-id="dbc3d-156">ToSheet</span></span>  <br/> |<span data-ttu-id="dbc3d-157">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="dbc3d-157">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="dbc3d-158">必需</span><span class="sxs-lookup"><span data-stu-id="dbc3d-158">required</span></span>  <br/> |<span data-ttu-id="dbc3d-159">向其所做的一个或多个连接的形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-159">The ID of the shape to which one or more connections are made.</span></span>  <br/> |<span data-ttu-id="dbc3d-160">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dbc3d-160">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

