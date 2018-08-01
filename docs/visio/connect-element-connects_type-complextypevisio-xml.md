---
title: 连接元素 （Connects_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6e1ad47b-ee28-6b9a-f2f9-642e09ca28d4
description: "\n			表示绘图中的两个形状间的连接，如组织结构图中的线和框。\n"
ms.openlocfilehash: 1bd3e1f006afe8d5bbb698e0b3a2179b74728315
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779959"
---
# <a name="connect-element-connectstype-complextype-visio-xml"></a><span data-ttu-id="a754c-103">连接元素 （Connects_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="a754c-103">Connect element (Connects_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="a754c-104">
			表示绘图中的两个形状间的连接，如组织结构图中的线和框。
</span><span class="sxs-lookup"><span data-stu-id="a754c-104">Represents a connection between two shapes in a drawing, such as a line and a box in an organization chart.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="a754c-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="a754c-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a754c-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="a754c-106">**Element type**</span></span> <br/> |[<span data-ttu-id="a754c-107">Connect_Type</span><span class="sxs-lookup"><span data-stu-id="a754c-107">Connect_Type</span></span>](connect_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="a754c-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="a754c-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="a754c-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="a754c-109">**Schema file**</span></span> <br/> |<span data-ttu-id="a754c-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="a754c-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="a754c-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="a754c-111">**Document parts**</span></span> <br/> |<span data-ttu-id="a754c-112">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="a754c-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="a754c-113">定义</span><span class="sxs-lookup"><span data-stu-id="a754c-113">Definition</span></span>

```XML
< xs:element name="Connect" type="Connect_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="a754c-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="a754c-114">Elements and attributes</span></span>

<span data-ttu-id="a754c-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="a754c-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="a754c-116">父元素</span><span class="sxs-lookup"><span data-stu-id="a754c-116">Parent elements</span></span>

|<span data-ttu-id="a754c-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="a754c-117">**Element**</span></span>|<span data-ttu-id="a754c-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="a754c-118">**Type**</span></span>|<span data-ttu-id="a754c-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="a754c-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a754c-120">Connects</span><span class="sxs-lookup"><span data-stu-id="a754c-120">Connects</span></span>](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="a754c-121">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="a754c-121">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="a754c-122">包含与绘图中的两个形状间的每个连接的**Connect**元素。</span><span class="sxs-lookup"><span data-stu-id="a754c-122">Contains a **Connect** element for each connection between two shapes in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="a754c-123">子元素</span><span class="sxs-lookup"><span data-stu-id="a754c-123">Child elements</span></span>

<span data-ttu-id="a754c-124">无。</span><span class="sxs-lookup"><span data-stu-id="a754c-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="a754c-125">属性</span><span class="sxs-lookup"><span data-stu-id="a754c-125">Attributes</span></span>

|<span data-ttu-id="a754c-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="a754c-126">**Attribute**</span></span>|<span data-ttu-id="a754c-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="a754c-127">**Type**</span></span>|<span data-ttu-id="a754c-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="a754c-128">**Required**</span></span>|<span data-ttu-id="a754c-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="a754c-129">**Description**</span></span>|<span data-ttu-id="a754c-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a754c-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a754c-131">FromCell</span><span class="sxs-lookup"><span data-stu-id="a754c-131">FromCell</span></span>  <br/> |<span data-ttu-id="a754c-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="a754c-132">xsd:string</span></span>  <br/> |<span data-ttu-id="a754c-133">可选</span><span class="sxs-lookup"><span data-stu-id="a754c-133">optional</span></span>  <br/> |<span data-ttu-id="a754c-134">生成连接单元格。</span><span class="sxs-lookup"><span data-stu-id="a754c-134">The cell from which a connection originates.</span></span>  <br/> |<span data-ttu-id="a754c-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a754c-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="a754c-136">FromPart</span><span class="sxs-lookup"><span data-stu-id="a754c-136">FromPart</span></span>  <br/> |<span data-ttu-id="a754c-137">xsd:int</span><span class="sxs-lookup"><span data-stu-id="a754c-137">xsd:int</span></span>  <br/> |<span data-ttu-id="a754c-138">可选</span><span class="sxs-lookup"><span data-stu-id="a754c-138">optional</span></span>  <br/> |<span data-ttu-id="a754c-139">生成连接形状的一部分。</span><span class="sxs-lookup"><span data-stu-id="a754c-139">The part of a shape from which a connection originates.</span></span>  <br/> |<span data-ttu-id="a754c-140">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a754c-140">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="a754c-141">FromSheet</span><span class="sxs-lookup"><span data-stu-id="a754c-141">FromSheet</span></span>  <br/> |<span data-ttu-id="a754c-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="a754c-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="a754c-143">必需</span><span class="sxs-lookup"><span data-stu-id="a754c-143">required</span></span>  <br/> |<span data-ttu-id="a754c-144">从其连接源自形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="a754c-144">The ID of the shape from which a connection or connections originate.</span></span>  <br/> |<span data-ttu-id="a754c-145">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a754c-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="a754c-146">ToCell</span><span class="sxs-lookup"><span data-stu-id="a754c-146">ToCell</span></span>  <br/> |<span data-ttu-id="a754c-147">xsd: string</span><span class="sxs-lookup"><span data-stu-id="a754c-147">xsd:string</span></span>  <br/> |<span data-ttu-id="a754c-148">可选</span><span class="sxs-lookup"><span data-stu-id="a754c-148">optional</span></span>  <br/> |<span data-ttu-id="a754c-149">单元格与其建立连接。</span><span class="sxs-lookup"><span data-stu-id="a754c-149">The cell to which a connection is made.</span></span>  <br/> |<span data-ttu-id="a754c-150">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a754c-150">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="a754c-151">ToPart</span><span class="sxs-lookup"><span data-stu-id="a754c-151">ToPart</span></span>  <br/> |<span data-ttu-id="a754c-152">xsd:int</span><span class="sxs-lookup"><span data-stu-id="a754c-152">xsd:int</span></span>  <br/> |<span data-ttu-id="a754c-153">可选</span><span class="sxs-lookup"><span data-stu-id="a754c-153">optional</span></span>  <br/> |<span data-ttu-id="a754c-154">对其进行连接的形状部分。</span><span class="sxs-lookup"><span data-stu-id="a754c-154">The part of a shape to which a connection is made.</span></span>  <br/> |<span data-ttu-id="a754c-155">Xsd:Int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a754c-155">Values of the xsd:Int type.</span></span>  <br/> |
|<span data-ttu-id="a754c-156">ToSheet</span><span class="sxs-lookup"><span data-stu-id="a754c-156">ToSheet</span></span>  <br/> |<span data-ttu-id="a754c-157">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="a754c-157">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="a754c-158">必需</span><span class="sxs-lookup"><span data-stu-id="a754c-158">required</span></span>  <br/> |<span data-ttu-id="a754c-159">向其所做的一个或多个连接的形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="a754c-159">The ID of the shape to which one or more connections are made.</span></span>  <br/> |<span data-ttu-id="a754c-160">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a754c-160">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

