---
title: HeaderFooterFont_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1e4134be-fb18-768e-b477-f9f40f72548d
ms.openlocfilehash: dd99d87e0d80aad3bcde31e4834337ee59088da2
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541069"
---
# <a name="headerfooterfonttype-complextype-visio-xml"></a><span data-ttu-id="57aad-102">HeaderFooterFont_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="57aad-102">HeaderFooterFont_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="57aad-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="57aad-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="57aad-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="57aad-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="57aad-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="57aad-105">**Schema file**</span></span> <br/> |<span data-ttu-id="57aad-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="57aad-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="57aad-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="57aad-107">**Extension base**</span></span> <br/> |<span data-ttu-id="57aad-108">无</span><span class="sxs-lookup"><span data-stu-id="57aad-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="57aad-109">定义</span><span class="sxs-lookup"><span data-stu-id="57aad-109">Definition</span></span>

```XML
      <xs:complexType name="HeaderFooterFont_Type">
    <xs:attribute name="Height"
  type="xsd:int"
    />
    <xs:attribute name="Width"
  type="xsd:int"
    />
    <xs:attribute name="Escapement"
  type="xsd:int"
    />
    <xs:attribute name="Orientation"
  type="xsd:int"
    />
    <xs:attribute name="Weight"
  type="xsd:int"
    />
    <xs:attribute name="Italic"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="Underline"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="StrikeOut"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="CharSet"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="OutPrecision"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="ClipPrecision"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="Quality"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="PitchAndFamily"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="FaceName"
  type="xsd:string"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="57aad-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="57aad-110">Elements and attributes</span></span>

<span data-ttu-id="57aad-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="57aad-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="57aad-112">子元素</span><span class="sxs-lookup"><span data-stu-id="57aad-112">Child elements</span></span>

<span data-ttu-id="57aad-113">无。</span><span class="sxs-lookup"><span data-stu-id="57aad-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="57aad-114">属性</span><span class="sxs-lookup"><span data-stu-id="57aad-114">Attributes</span></span>

|<span data-ttu-id="57aad-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="57aad-115">**Attribute**</span></span>|<span data-ttu-id="57aad-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="57aad-116">**Type**</span></span>|<span data-ttu-id="57aad-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="57aad-117">**Required**</span></span>|<span data-ttu-id="57aad-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="57aad-118">**Description**</span></span>|<span data-ttu-id="57aad-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="57aad-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="57aad-120">CharSet</span><span class="sxs-lookup"><span data-stu-id="57aad-120">CharSet</span></span>  <br/> |<span data-ttu-id="57aad-121">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="57aad-121">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="57aad-122">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-122">optional</span></span>  <br/> ||<span data-ttu-id="57aad-123">Xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-123">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="57aad-124">ClipPrecision</span><span class="sxs-lookup"><span data-stu-id="57aad-124">ClipPrecision</span></span>  <br/> |<span data-ttu-id="57aad-125">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="57aad-125">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="57aad-126">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-126">optional</span></span>  <br/> ||<span data-ttu-id="57aad-127">Xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-127">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="57aad-128">又</span><span class="sxs-lookup"><span data-stu-id="57aad-128">Escapement</span></span>  <br/> |<span data-ttu-id="57aad-129">xsd: int</span><span class="sxs-lookup"><span data-stu-id="57aad-129">xsd:int</span></span>  <br/> |<span data-ttu-id="57aad-130">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-130">optional</span></span>  <br/> ||<span data-ttu-id="57aad-131">Xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-131">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="57aad-132">FaceName</span><span class="sxs-lookup"><span data-stu-id="57aad-132">FaceName</span></span>  <br/> |<span data-ttu-id="57aad-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="57aad-133">xsd:string</span></span>  <br/> |<span data-ttu-id="57aad-134">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-134">optional</span></span>  <br/> ||<span data-ttu-id="57aad-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="57aad-136">Height</span><span class="sxs-lookup"><span data-stu-id="57aad-136">Height</span></span>  <br/> |<span data-ttu-id="57aad-137">xsd: int</span><span class="sxs-lookup"><span data-stu-id="57aad-137">xsd:int</span></span>  <br/> |<span data-ttu-id="57aad-138">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-138">optional</span></span>  <br/> ||<span data-ttu-id="57aad-139">Xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-139">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="57aad-140">斜体</span><span class="sxs-lookup"><span data-stu-id="57aad-140">Italic</span></span>  <br/> |<span data-ttu-id="57aad-141">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="57aad-141">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="57aad-142">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-142">optional</span></span>  <br/> ||<span data-ttu-id="57aad-143">Xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-143">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="57aad-144">Orientation</span><span class="sxs-lookup"><span data-stu-id="57aad-144">Orientation</span></span>  <br/> |<span data-ttu-id="57aad-145">xsd: int</span><span class="sxs-lookup"><span data-stu-id="57aad-145">xsd:int</span></span>  <br/> |<span data-ttu-id="57aad-146">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-146">optional</span></span>  <br/> ||<span data-ttu-id="57aad-147">Xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-147">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="57aad-148">OutPrecision</span><span class="sxs-lookup"><span data-stu-id="57aad-148">OutPrecision</span></span>  <br/> |<span data-ttu-id="57aad-149">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="57aad-149">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="57aad-150">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-150">optional</span></span>  <br/> ||<span data-ttu-id="57aad-151">Xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-151">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="57aad-152">PitchAndFamily</span><span class="sxs-lookup"><span data-stu-id="57aad-152">PitchAndFamily</span></span>  <br/> |<span data-ttu-id="57aad-153">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="57aad-153">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="57aad-154">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-154">optional</span></span>  <br/> ||<span data-ttu-id="57aad-155">Xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-155">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="57aad-156">Quality</span><span class="sxs-lookup"><span data-stu-id="57aad-156">Quality</span></span>  <br/> |<span data-ttu-id="57aad-157">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="57aad-157">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="57aad-158">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-158">optional</span></span>  <br/> ||<span data-ttu-id="57aad-159">Xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-159">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="57aad-160">删除线</span><span class="sxs-lookup"><span data-stu-id="57aad-160">StrikeOut</span></span>  <br/> |<span data-ttu-id="57aad-161">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="57aad-161">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="57aad-162">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-162">optional</span></span>  <br/> ||<span data-ttu-id="57aad-163">Xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-163">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="57aad-164">下划线</span><span class="sxs-lookup"><span data-stu-id="57aad-164">Underline</span></span>  <br/> |<span data-ttu-id="57aad-165">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="57aad-165">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="57aad-166">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-166">optional</span></span>  <br/> ||<span data-ttu-id="57aad-167">Xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-167">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="57aad-168">粗细</span><span class="sxs-lookup"><span data-stu-id="57aad-168">Weight</span></span>  <br/> |<span data-ttu-id="57aad-169">xsd: int</span><span class="sxs-lookup"><span data-stu-id="57aad-169">xsd:int</span></span>  <br/> |<span data-ttu-id="57aad-170">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-170">optional</span></span>  <br/> ||<span data-ttu-id="57aad-171">Xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-171">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="57aad-172">Width</span><span class="sxs-lookup"><span data-stu-id="57aad-172">Width</span></span>  <br/> |<span data-ttu-id="57aad-173">xsd: int</span><span class="sxs-lookup"><span data-stu-id="57aad-173">xsd:int</span></span>  <br/> |<span data-ttu-id="57aad-174">可选</span><span class="sxs-lookup"><span data-stu-id="57aad-174">optional</span></span>  <br/> ||<span data-ttu-id="57aad-175">Xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57aad-175">Values of the xsd:int type.</span></span>  <br/> |
   

