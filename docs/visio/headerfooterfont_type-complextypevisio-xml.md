---
title: HeaderFooterFont_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1e4134be-fb18-768e-b477-f9f40f72548d
ms.openlocfilehash: cc51924aa68e3248583be5f717b5813d4a32af2b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397245"
---
# <a name="headerfooterfonttype-complextype-visio-xml"></a><span data-ttu-id="0824f-102">HeaderFooterFont_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="0824f-102">HeaderFooterFont_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="0824f-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="0824f-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0824f-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0824f-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="0824f-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0824f-105">**Schema file**</span></span> <br/> |<span data-ttu-id="0824f-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="0824f-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="0824f-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="0824f-107">**Extension base**</span></span> <br/> |<span data-ttu-id="0824f-108">无</span><span class="sxs-lookup"><span data-stu-id="0824f-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0824f-109">定义</span><span class="sxs-lookup"><span data-stu-id="0824f-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="0824f-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0824f-110">Elements and attributes</span></span>

<span data-ttu-id="0824f-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="0824f-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="0824f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="0824f-112">Child elements</span></span>

<span data-ttu-id="0824f-113">无。</span><span class="sxs-lookup"><span data-stu-id="0824f-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="0824f-114">属性</span><span class="sxs-lookup"><span data-stu-id="0824f-114">Attributes</span></span>

|<span data-ttu-id="0824f-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="0824f-115">**Attribute**</span></span>|<span data-ttu-id="0824f-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="0824f-116">**Type**</span></span>|<span data-ttu-id="0824f-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="0824f-117">**Required**</span></span>|<span data-ttu-id="0824f-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="0824f-118">**Description**</span></span>|<span data-ttu-id="0824f-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="0824f-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0824f-120">字符集</span><span class="sxs-lookup"><span data-stu-id="0824f-120">CharSet</span></span>  <br/> |<span data-ttu-id="0824f-121">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0824f-121">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="0824f-122">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-122">optional</span></span>  <br/> ||<span data-ttu-id="0824f-123">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-123">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="0824f-124">ClipPrecision</span><span class="sxs-lookup"><span data-stu-id="0824f-124">ClipPrecision</span></span>  <br/> |<span data-ttu-id="0824f-125">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0824f-125">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="0824f-126">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-126">optional</span></span>  <br/> ||<span data-ttu-id="0824f-127">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-127">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="0824f-128">行距</span><span class="sxs-lookup"><span data-stu-id="0824f-128">Escapement</span></span>  <br/> |<span data-ttu-id="0824f-129">xsd:int</span><span class="sxs-lookup"><span data-stu-id="0824f-129">xsd:int</span></span>  <br/> |<span data-ttu-id="0824f-130">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-130">optional</span></span>  <br/> ||<span data-ttu-id="0824f-131">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-131">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="0824f-132">FaceName</span><span class="sxs-lookup"><span data-stu-id="0824f-132">FaceName</span></span>  <br/> |<span data-ttu-id="0824f-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="0824f-133">xsd:string</span></span>  <br/> |<span data-ttu-id="0824f-134">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-134">optional</span></span>  <br/> ||<span data-ttu-id="0824f-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="0824f-136">高度</span><span class="sxs-lookup"><span data-stu-id="0824f-136">Height</span></span>  <br/> |<span data-ttu-id="0824f-137">xsd:int</span><span class="sxs-lookup"><span data-stu-id="0824f-137">xsd:int</span></span>  <br/> |<span data-ttu-id="0824f-138">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-138">optional</span></span>  <br/> ||<span data-ttu-id="0824f-139">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-139">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="0824f-140">斜体</span><span class="sxs-lookup"><span data-stu-id="0824f-140">Italic</span></span>  <br/> |<span data-ttu-id="0824f-141">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0824f-141">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="0824f-142">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-142">optional</span></span>  <br/> ||<span data-ttu-id="0824f-143">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-143">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="0824f-144">Orientation</span><span class="sxs-lookup"><span data-stu-id="0824f-144">Orientation</span></span>  <br/> |<span data-ttu-id="0824f-145">xsd:int</span><span class="sxs-lookup"><span data-stu-id="0824f-145">xsd:int</span></span>  <br/> |<span data-ttu-id="0824f-146">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-146">optional</span></span>  <br/> ||<span data-ttu-id="0824f-147">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-147">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="0824f-148">OutPrecision</span><span class="sxs-lookup"><span data-stu-id="0824f-148">OutPrecision</span></span>  <br/> |<span data-ttu-id="0824f-149">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0824f-149">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="0824f-150">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-150">optional</span></span>  <br/> ||<span data-ttu-id="0824f-151">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-151">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="0824f-152">PitchAndFamily</span><span class="sxs-lookup"><span data-stu-id="0824f-152">PitchAndFamily</span></span>  <br/> |<span data-ttu-id="0824f-153">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0824f-153">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="0824f-154">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-154">optional</span></span>  <br/> ||<span data-ttu-id="0824f-155">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-155">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="0824f-156">质量</span><span class="sxs-lookup"><span data-stu-id="0824f-156">Quality</span></span>  <br/> |<span data-ttu-id="0824f-157">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0824f-157">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="0824f-158">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-158">optional</span></span>  <br/> ||<span data-ttu-id="0824f-159">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-159">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="0824f-160">删除线</span><span class="sxs-lookup"><span data-stu-id="0824f-160">StrikeOut</span></span>  <br/> |<span data-ttu-id="0824f-161">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0824f-161">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="0824f-162">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-162">optional</span></span>  <br/> ||<span data-ttu-id="0824f-163">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-163">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="0824f-164">下划线</span><span class="sxs-lookup"><span data-stu-id="0824f-164">Underline</span></span>  <br/> |<span data-ttu-id="0824f-165">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0824f-165">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="0824f-166">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-166">optional</span></span>  <br/> ||<span data-ttu-id="0824f-167">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-167">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="0824f-168">权重</span><span class="sxs-lookup"><span data-stu-id="0824f-168">Weight</span></span>  <br/> |<span data-ttu-id="0824f-169">xsd:int</span><span class="sxs-lookup"><span data-stu-id="0824f-169">xsd:int</span></span>  <br/> |<span data-ttu-id="0824f-170">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-170">optional</span></span>  <br/> ||<span data-ttu-id="0824f-171">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-171">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="0824f-172">宽度</span><span class="sxs-lookup"><span data-stu-id="0824f-172">Width</span></span>  <br/> |<span data-ttu-id="0824f-173">xsd:int</span><span class="sxs-lookup"><span data-stu-id="0824f-173">xsd:int</span></span>  <br/> |<span data-ttu-id="0824f-174">可选</span><span class="sxs-lookup"><span data-stu-id="0824f-174">optional</span></span>  <br/> ||<span data-ttu-id="0824f-175">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0824f-175">Values of the xsd:int type.</span></span>  <br/> |
   

