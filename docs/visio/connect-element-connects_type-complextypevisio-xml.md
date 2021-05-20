---
title: '连接 XML (Connects_Type复杂类型)  (Visio元素) '
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
# <a name="connect-element-connects_type-complextype-visio-xml"></a><span data-ttu-id="a012b-103">连接 XML (Connects_Type复杂类型)  (Visio元素) </span><span class="sxs-lookup"><span data-stu-id="a012b-103">Connect element (Connects_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="a012b-104">表示绘图中的两个形状间的连接，如组织结构图中的线和框。</span><span class="sxs-lookup"><span data-stu-id="a012b-104">Represents a connection between two shapes in a drawing, such as a line and a box in an organization chart.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="a012b-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="a012b-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a012b-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="a012b-106">**Element type**</span></span> <br/> |[<span data-ttu-id="a012b-107">Connect_Type</span><span class="sxs-lookup"><span data-stu-id="a012b-107">Connect_Type</span></span>](connect_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="a012b-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="a012b-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="a012b-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="a012b-109">**Schema file**</span></span> <br/> |<span data-ttu-id="a012b-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="a012b-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="a012b-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="a012b-111">**Document parts**</span></span> <br/> |<span data-ttu-id="a012b-112">page#.xml，master#.xml</span><span class="sxs-lookup"><span data-stu-id="a012b-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="a012b-113">定义</span><span class="sxs-lookup"><span data-stu-id="a012b-113">Definition</span></span>

```XML
< xs:element name="Connect" type="Connect_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="a012b-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="a012b-114">Elements and attributes</span></span>

<span data-ttu-id="a012b-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="a012b-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="a012b-116">父元素</span><span class="sxs-lookup"><span data-stu-id="a012b-116">Parent elements</span></span>

|<span data-ttu-id="a012b-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="a012b-117">**Element**</span></span>|<span data-ttu-id="a012b-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="a012b-118">**Type**</span></span>|<span data-ttu-id="a012b-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="a012b-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a012b-120">Connects</span><span class="sxs-lookup"><span data-stu-id="a012b-120">Connects</span></span>](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="a012b-121">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="a012b-121">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="a012b-122">包含一 **连接** 图形中两个形状之间的每个连接的一个属性元素。</span><span class="sxs-lookup"><span data-stu-id="a012b-122">Contains a **Connect** element for each connection between two shapes in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="a012b-123">子元素</span><span class="sxs-lookup"><span data-stu-id="a012b-123">Child elements</span></span>

<span data-ttu-id="a012b-124">无。</span><span class="sxs-lookup"><span data-stu-id="a012b-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="a012b-125">属性</span><span class="sxs-lookup"><span data-stu-id="a012b-125">Attributes</span></span>

|<span data-ttu-id="a012b-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="a012b-126">**Attribute**</span></span>|<span data-ttu-id="a012b-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="a012b-127">**Type**</span></span>|<span data-ttu-id="a012b-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="a012b-128">**Required**</span></span>|<span data-ttu-id="a012b-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="a012b-129">**Description**</span></span>|<span data-ttu-id="a012b-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a012b-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a012b-131">FromCell</span><span class="sxs-lookup"><span data-stu-id="a012b-131">FromCell</span></span>  <br/> |<span data-ttu-id="a012b-132">xsd：string</span><span class="sxs-lookup"><span data-stu-id="a012b-132">xsd:string</span></span>  <br/> |<span data-ttu-id="a012b-133">可选</span><span class="sxs-lookup"><span data-stu-id="a012b-133">optional</span></span>  <br/> |<span data-ttu-id="a012b-134">从其中建立连接的单元格。</span><span class="sxs-lookup"><span data-stu-id="a012b-134">The cell from which a connection originates.</span></span>  <br/> |<span data-ttu-id="a012b-135">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a012b-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="a012b-136">FromPart</span><span class="sxs-lookup"><span data-stu-id="a012b-136">FromPart</span></span>  <br/> |<span data-ttu-id="a012b-137">xsd：int</span><span class="sxs-lookup"><span data-stu-id="a012b-137">xsd:int</span></span>  <br/> |<span data-ttu-id="a012b-138">可选</span><span class="sxs-lookup"><span data-stu-id="a012b-138">optional</span></span>  <br/> |<span data-ttu-id="a012b-139">从形状中产生连接的部分。</span><span class="sxs-lookup"><span data-stu-id="a012b-139">The part of a shape from which a connection originates.</span></span>  <br/> |<span data-ttu-id="a012b-140">xsd：int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a012b-140">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="a012b-141">FromSheet</span><span class="sxs-lookup"><span data-stu-id="a012b-141">FromSheet</span></span>  <br/> |<span data-ttu-id="a012b-142">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="a012b-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="a012b-143">必需</span><span class="sxs-lookup"><span data-stu-id="a012b-143">required</span></span>  <br/> |<span data-ttu-id="a012b-144">产生连接的形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="a012b-144">The ID of the shape from which a connection or connections originate.</span></span>  <br/> |<span data-ttu-id="a012b-145">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a012b-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="a012b-146">ToCell</span><span class="sxs-lookup"><span data-stu-id="a012b-146">ToCell</span></span>  <br/> |<span data-ttu-id="a012b-147">xsd：string</span><span class="sxs-lookup"><span data-stu-id="a012b-147">xsd:string</span></span>  <br/> |<span data-ttu-id="a012b-148">可选</span><span class="sxs-lookup"><span data-stu-id="a012b-148">optional</span></span>  <br/> |<span data-ttu-id="a012b-149">建立连接的单元格。</span><span class="sxs-lookup"><span data-stu-id="a012b-149">The cell to which a connection is made.</span></span>  <br/> |<span data-ttu-id="a012b-150">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a012b-150">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="a012b-151">ToPart</span><span class="sxs-lookup"><span data-stu-id="a012b-151">ToPart</span></span>  <br/> |<span data-ttu-id="a012b-152">xsd：int</span><span class="sxs-lookup"><span data-stu-id="a012b-152">xsd:int</span></span>  <br/> |<span data-ttu-id="a012b-153">可选</span><span class="sxs-lookup"><span data-stu-id="a012b-153">optional</span></span>  <br/> |<span data-ttu-id="a012b-154">要连接到的形状部分。</span><span class="sxs-lookup"><span data-stu-id="a012b-154">The part of a shape to which a connection is made.</span></span>  <br/> |<span data-ttu-id="a012b-155">xsd：Int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a012b-155">Values of the xsd:Int type.</span></span>  <br/> |
|<span data-ttu-id="a012b-156">ToSheet</span><span class="sxs-lookup"><span data-stu-id="a012b-156">ToSheet</span></span>  <br/> |<span data-ttu-id="a012b-157">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="a012b-157">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="a012b-158">必需</span><span class="sxs-lookup"><span data-stu-id="a012b-158">required</span></span>  <br/> |<span data-ttu-id="a012b-159">要建立一个或多个连接的形状的 ID。</span><span class="sxs-lookup"><span data-stu-id="a012b-159">The ID of the shape to which one or more connections are made.</span></span>  <br/> |<span data-ttu-id="a012b-160">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a012b-160">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

