---
title: HeaderFooterFont_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1e4134be-fb18-768e-b477-f9f40f72548d
ms.openlocfilehash: cc51924aa68e3248583be5f717b5813d4a32af2b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335621"
---
# <a name="headerfooterfonttype-complextype-visio-xml"></a><span data-ttu-id="16cb1-102">HeaderFooterFont_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="16cb1-102">HeaderFooterFont_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="16cb1-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="16cb1-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="16cb1-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="16cb1-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="16cb1-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="16cb1-105">**Schema file**</span></span> <br/> |<span data-ttu-id="16cb1-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="16cb1-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="16cb1-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="16cb1-107">**Extension base**</span></span> <br/> |<span data-ttu-id="16cb1-108">无</span><span class="sxs-lookup"><span data-stu-id="16cb1-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="16cb1-109">定义</span><span class="sxs-lookup"><span data-stu-id="16cb1-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="16cb1-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="16cb1-110">Elements and attributes</span></span>

<span data-ttu-id="16cb1-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="16cb1-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="16cb1-112">子元素</span><span class="sxs-lookup"><span data-stu-id="16cb1-112">Child elements</span></span>

<span data-ttu-id="16cb1-113">无。</span><span class="sxs-lookup"><span data-stu-id="16cb1-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="16cb1-114">属性</span><span class="sxs-lookup"><span data-stu-id="16cb1-114">Attributes</span></span>

|<span data-ttu-id="16cb1-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="16cb1-115">**Attribute**</span></span>|<span data-ttu-id="16cb1-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="16cb1-116">**Type**</span></span>|<span data-ttu-id="16cb1-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="16cb1-117">**Required**</span></span>|<span data-ttu-id="16cb1-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="16cb1-118">**Description**</span></span>|<span data-ttu-id="16cb1-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="16cb1-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="16cb1-120">CharSet</span><span class="sxs-lookup"><span data-stu-id="16cb1-120">CharSet</span></span>  <br/> |<span data-ttu-id="16cb1-121">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="16cb1-121">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="16cb1-122">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-122">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-123">xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-123">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-124">ClipPrecision</span><span class="sxs-lookup"><span data-stu-id="16cb1-124">ClipPrecision</span></span>  <br/> |<span data-ttu-id="16cb1-125">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="16cb1-125">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="16cb1-126">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-126">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-127">xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-127">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-128">又</span><span class="sxs-lookup"><span data-stu-id="16cb1-128">Escapement</span></span>  <br/> |<span data-ttu-id="16cb1-129">xsd: int</span><span class="sxs-lookup"><span data-stu-id="16cb1-129">xsd:int</span></span>  <br/> |<span data-ttu-id="16cb1-130">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-130">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-131">xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-131">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-132">FaceName</span><span class="sxs-lookup"><span data-stu-id="16cb1-132">FaceName</span></span>  <br/> |<span data-ttu-id="16cb1-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="16cb1-133">xsd:string</span></span>  <br/> |<span data-ttu-id="16cb1-134">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-134">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-135">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-136">Height</span><span class="sxs-lookup"><span data-stu-id="16cb1-136">Height</span></span>  <br/> |<span data-ttu-id="16cb1-137">xsd: int</span><span class="sxs-lookup"><span data-stu-id="16cb1-137">xsd:int</span></span>  <br/> |<span data-ttu-id="16cb1-138">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-138">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-139">xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-139">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-140">斜体</span><span class="sxs-lookup"><span data-stu-id="16cb1-140">Italic</span></span>  <br/> |<span data-ttu-id="16cb1-141">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="16cb1-141">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="16cb1-142">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-142">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-143">xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-143">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-144">Orientation</span><span class="sxs-lookup"><span data-stu-id="16cb1-144">Orientation</span></span>  <br/> |<span data-ttu-id="16cb1-145">xsd: int</span><span class="sxs-lookup"><span data-stu-id="16cb1-145">xsd:int</span></span>  <br/> |<span data-ttu-id="16cb1-146">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-146">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-147">xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-147">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-148">OutPrecision</span><span class="sxs-lookup"><span data-stu-id="16cb1-148">OutPrecision</span></span>  <br/> |<span data-ttu-id="16cb1-149">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="16cb1-149">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="16cb1-150">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-150">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-151">xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-151">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-152">PitchAndFamily</span><span class="sxs-lookup"><span data-stu-id="16cb1-152">PitchAndFamily</span></span>  <br/> |<span data-ttu-id="16cb1-153">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="16cb1-153">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="16cb1-154">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-154">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-155">xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-155">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-156">Quality</span><span class="sxs-lookup"><span data-stu-id="16cb1-156">Quality</span></span>  <br/> |<span data-ttu-id="16cb1-157">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="16cb1-157">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="16cb1-158">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-158">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-159">xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-159">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-160">删除线</span><span class="sxs-lookup"><span data-stu-id="16cb1-160">StrikeOut</span></span>  <br/> |<span data-ttu-id="16cb1-161">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="16cb1-161">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="16cb1-162">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-162">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-163">xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-163">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-164">下划线</span><span class="sxs-lookup"><span data-stu-id="16cb1-164">Underline</span></span>  <br/> |<span data-ttu-id="16cb1-165">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="16cb1-165">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="16cb1-166">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-166">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-167">xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-167">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-168">粗细</span><span class="sxs-lookup"><span data-stu-id="16cb1-168">Weight</span></span>  <br/> |<span data-ttu-id="16cb1-169">xsd: int</span><span class="sxs-lookup"><span data-stu-id="16cb1-169">xsd:int</span></span>  <br/> |<span data-ttu-id="16cb1-170">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-170">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-171">xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-171">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="16cb1-172">Width</span><span class="sxs-lookup"><span data-stu-id="16cb1-172">Width</span></span>  <br/> |<span data-ttu-id="16cb1-173">xsd: int</span><span class="sxs-lookup"><span data-stu-id="16cb1-173">xsd:int</span></span>  <br/> |<span data-ttu-id="16cb1-174">可选</span><span class="sxs-lookup"><span data-stu-id="16cb1-174">optional</span></span>  <br/> ||<span data-ttu-id="16cb1-175">xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16cb1-175">Values of the xsd:int type.</span></span>  <br/> |
   

