---
title: HeaderFooterFont_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1e4134be-fb18-768e-b477-f9f40f72548d
ms.openlocfilehash: 1d7c4d6850e4a8ea1933ae751c580d09e0dd67bd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780377"
---
# <a name="headerfooterfonttype-complextype-visio-xml"></a><span data-ttu-id="953dc-102">HeaderFooterFont_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="953dc-102">HeaderFooterFont_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="953dc-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="953dc-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="953dc-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="953dc-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="953dc-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="953dc-105">**Schema file**</span></span> <br/> |<span data-ttu-id="953dc-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="953dc-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="953dc-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="953dc-107">**Extension base**</span></span> <br/> |<span data-ttu-id="953dc-108">无</span><span class="sxs-lookup"><span data-stu-id="953dc-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="953dc-109">定义</span><span class="sxs-lookup"><span data-stu-id="953dc-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="953dc-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="953dc-110">Elements and attributes</span></span>

<span data-ttu-id="953dc-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="953dc-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="953dc-112">子元素</span><span class="sxs-lookup"><span data-stu-id="953dc-112">Child elements</span></span>

<span data-ttu-id="953dc-113">无。</span><span class="sxs-lookup"><span data-stu-id="953dc-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="953dc-114">属性</span><span class="sxs-lookup"><span data-stu-id="953dc-114">Attributes</span></span>

|<span data-ttu-id="953dc-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="953dc-115">**Attribute**</span></span>|<span data-ttu-id="953dc-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="953dc-116">**Type**</span></span>|<span data-ttu-id="953dc-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="953dc-117">**Required**</span></span>|<span data-ttu-id="953dc-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="953dc-118">**Description**</span></span>|<span data-ttu-id="953dc-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="953dc-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="953dc-120">字符集</span><span class="sxs-lookup"><span data-stu-id="953dc-120">CharSet</span></span>  <br/> |<span data-ttu-id="953dc-121">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="953dc-121">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="953dc-122">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-122">optional</span></span>  <br/> ||<span data-ttu-id="953dc-123">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-123">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="953dc-124">ClipPrecision</span><span class="sxs-lookup"><span data-stu-id="953dc-124">ClipPrecision</span></span>  <br/> |<span data-ttu-id="953dc-125">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="953dc-125">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="953dc-126">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-126">optional</span></span>  <br/> ||<span data-ttu-id="953dc-127">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-127">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="953dc-128">行距</span><span class="sxs-lookup"><span data-stu-id="953dc-128">Escapement</span></span>  <br/> |<span data-ttu-id="953dc-129">xsd:int</span><span class="sxs-lookup"><span data-stu-id="953dc-129">xsd:int</span></span>  <br/> |<span data-ttu-id="953dc-130">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-130">optional</span></span>  <br/> ||<span data-ttu-id="953dc-131">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-131">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="953dc-132">FaceName</span><span class="sxs-lookup"><span data-stu-id="953dc-132">FaceName</span></span>  <br/> |<span data-ttu-id="953dc-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="953dc-133">xsd:string</span></span>  <br/> |<span data-ttu-id="953dc-134">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-134">optional</span></span>  <br/> ||<span data-ttu-id="953dc-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="953dc-136">高度</span><span class="sxs-lookup"><span data-stu-id="953dc-136">Height</span></span>  <br/> |<span data-ttu-id="953dc-137">xsd:int</span><span class="sxs-lookup"><span data-stu-id="953dc-137">xsd:int</span></span>  <br/> |<span data-ttu-id="953dc-138">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-138">optional</span></span>  <br/> ||<span data-ttu-id="953dc-139">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-139">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="953dc-140">斜体</span><span class="sxs-lookup"><span data-stu-id="953dc-140">Italic</span></span>  <br/> |<span data-ttu-id="953dc-141">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="953dc-141">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="953dc-142">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-142">optional</span></span>  <br/> ||<span data-ttu-id="953dc-143">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-143">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="953dc-144">Orientation</span><span class="sxs-lookup"><span data-stu-id="953dc-144">Orientation</span></span>  <br/> |<span data-ttu-id="953dc-145">xsd:int</span><span class="sxs-lookup"><span data-stu-id="953dc-145">xsd:int</span></span>  <br/> |<span data-ttu-id="953dc-146">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-146">optional</span></span>  <br/> ||<span data-ttu-id="953dc-147">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-147">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="953dc-148">OutPrecision</span><span class="sxs-lookup"><span data-stu-id="953dc-148">OutPrecision</span></span>  <br/> |<span data-ttu-id="953dc-149">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="953dc-149">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="953dc-150">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-150">optional</span></span>  <br/> ||<span data-ttu-id="953dc-151">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-151">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="953dc-152">PitchAndFamily</span><span class="sxs-lookup"><span data-stu-id="953dc-152">PitchAndFamily</span></span>  <br/> |<span data-ttu-id="953dc-153">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="953dc-153">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="953dc-154">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-154">optional</span></span>  <br/> ||<span data-ttu-id="953dc-155">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-155">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="953dc-156">质量</span><span class="sxs-lookup"><span data-stu-id="953dc-156">Quality</span></span>  <br/> |<span data-ttu-id="953dc-157">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="953dc-157">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="953dc-158">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-158">optional</span></span>  <br/> ||<span data-ttu-id="953dc-159">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-159">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="953dc-160">删除线</span><span class="sxs-lookup"><span data-stu-id="953dc-160">StrikeOut</span></span>  <br/> |<span data-ttu-id="953dc-161">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="953dc-161">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="953dc-162">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-162">optional</span></span>  <br/> ||<span data-ttu-id="953dc-163">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-163">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="953dc-164">下划线</span><span class="sxs-lookup"><span data-stu-id="953dc-164">Underline</span></span>  <br/> |<span data-ttu-id="953dc-165">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="953dc-165">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="953dc-166">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-166">optional</span></span>  <br/> ||<span data-ttu-id="953dc-167">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-167">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="953dc-168">权重</span><span class="sxs-lookup"><span data-stu-id="953dc-168">Weight</span></span>  <br/> |<span data-ttu-id="953dc-169">xsd:int</span><span class="sxs-lookup"><span data-stu-id="953dc-169">xsd:int</span></span>  <br/> |<span data-ttu-id="953dc-170">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-170">optional</span></span>  <br/> ||<span data-ttu-id="953dc-171">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-171">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="953dc-172">宽度</span><span class="sxs-lookup"><span data-stu-id="953dc-172">Width</span></span>  <br/> |<span data-ttu-id="953dc-173">xsd:int</span><span class="sxs-lookup"><span data-stu-id="953dc-173">xsd:int</span></span>  <br/> |<span data-ttu-id="953dc-174">可选</span><span class="sxs-lookup"><span data-stu-id="953dc-174">optional</span></span>  <br/> ||<span data-ttu-id="953dc-175">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="953dc-175">Values of the xsd:int type.</span></span>  <br/> |
   

