---
title: 'HeaderFooterFont_Type COMPLEXType (Visio XML) '
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
# <a name="headerfooterfont_type-complextype-visio-xml"></a><span data-ttu-id="39479-102">HeaderFooterFont_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="39479-102">HeaderFooterFont_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="39479-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="39479-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="39479-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="39479-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="39479-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="39479-105">**Schema file**</span></span> <br/> |<span data-ttu-id="39479-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="39479-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="39479-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="39479-107">**Extension base**</span></span> <br/> |<span data-ttu-id="39479-108">无</span><span class="sxs-lookup"><span data-stu-id="39479-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="39479-109">定义</span><span class="sxs-lookup"><span data-stu-id="39479-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="39479-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="39479-110">Elements and attributes</span></span>

<span data-ttu-id="39479-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="39479-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="39479-112">子元素</span><span class="sxs-lookup"><span data-stu-id="39479-112">Child elements</span></span>

<span data-ttu-id="39479-113">无。</span><span class="sxs-lookup"><span data-stu-id="39479-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="39479-114">属性</span><span class="sxs-lookup"><span data-stu-id="39479-114">Attributes</span></span>

|<span data-ttu-id="39479-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="39479-115">**Attribute**</span></span>|<span data-ttu-id="39479-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="39479-116">**Type**</span></span>|<span data-ttu-id="39479-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="39479-117">**Required**</span></span>|<span data-ttu-id="39479-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="39479-118">**Description**</span></span>|<span data-ttu-id="39479-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="39479-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39479-120">CharSet</span><span class="sxs-lookup"><span data-stu-id="39479-120">CharSet</span></span>  <br/> |<span data-ttu-id="39479-121">xsd：unsignedByte</span><span class="sxs-lookup"><span data-stu-id="39479-121">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="39479-122">可选</span><span class="sxs-lookup"><span data-stu-id="39479-122">optional</span></span>  <br/> ||<span data-ttu-id="39479-123">xsd：unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-123">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="39479-124">ClipPrecision</span><span class="sxs-lookup"><span data-stu-id="39479-124">ClipPrecision</span></span>  <br/> |<span data-ttu-id="39479-125">xsd：unsignedByte</span><span class="sxs-lookup"><span data-stu-id="39479-125">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="39479-126">可选</span><span class="sxs-lookup"><span data-stu-id="39479-126">optional</span></span>  <br/> ||<span data-ttu-id="39479-127">xsd：unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-127">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="39479-128">转义</span><span class="sxs-lookup"><span data-stu-id="39479-128">Escapement</span></span>  <br/> |<span data-ttu-id="39479-129">xsd：int</span><span class="sxs-lookup"><span data-stu-id="39479-129">xsd:int</span></span>  <br/> |<span data-ttu-id="39479-130">可选</span><span class="sxs-lookup"><span data-stu-id="39479-130">optional</span></span>  <br/> ||<span data-ttu-id="39479-131">xsd：int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-131">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="39479-132">FaceName</span><span class="sxs-lookup"><span data-stu-id="39479-132">FaceName</span></span>  <br/> |<span data-ttu-id="39479-133">xsd：string</span><span class="sxs-lookup"><span data-stu-id="39479-133">xsd:string</span></span>  <br/> |<span data-ttu-id="39479-134">可选</span><span class="sxs-lookup"><span data-stu-id="39479-134">optional</span></span>  <br/> ||<span data-ttu-id="39479-135">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="39479-136">Height</span><span class="sxs-lookup"><span data-stu-id="39479-136">Height</span></span>  <br/> |<span data-ttu-id="39479-137">xsd：int</span><span class="sxs-lookup"><span data-stu-id="39479-137">xsd:int</span></span>  <br/> |<span data-ttu-id="39479-138">可选</span><span class="sxs-lookup"><span data-stu-id="39479-138">optional</span></span>  <br/> ||<span data-ttu-id="39479-139">xsd：int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-139">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="39479-140">斜体</span><span class="sxs-lookup"><span data-stu-id="39479-140">Italic</span></span>  <br/> |<span data-ttu-id="39479-141">xsd：unsignedByte</span><span class="sxs-lookup"><span data-stu-id="39479-141">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="39479-142">可选</span><span class="sxs-lookup"><span data-stu-id="39479-142">optional</span></span>  <br/> ||<span data-ttu-id="39479-143">xsd：unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-143">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="39479-144">Orientation</span><span class="sxs-lookup"><span data-stu-id="39479-144">Orientation</span></span>  <br/> |<span data-ttu-id="39479-145">xsd：int</span><span class="sxs-lookup"><span data-stu-id="39479-145">xsd:int</span></span>  <br/> |<span data-ttu-id="39479-146">可选</span><span class="sxs-lookup"><span data-stu-id="39479-146">optional</span></span>  <br/> ||<span data-ttu-id="39479-147">xsd：int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-147">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="39479-148">OutPrecision</span><span class="sxs-lookup"><span data-stu-id="39479-148">OutPrecision</span></span>  <br/> |<span data-ttu-id="39479-149">xsd：unsignedByte</span><span class="sxs-lookup"><span data-stu-id="39479-149">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="39479-150">可选</span><span class="sxs-lookup"><span data-stu-id="39479-150">optional</span></span>  <br/> ||<span data-ttu-id="39479-151">xsd：unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-151">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="39479-152">PitchAndFamily</span><span class="sxs-lookup"><span data-stu-id="39479-152">PitchAndFamily</span></span>  <br/> |<span data-ttu-id="39479-153">xsd：unsignedByte</span><span class="sxs-lookup"><span data-stu-id="39479-153">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="39479-154">可选</span><span class="sxs-lookup"><span data-stu-id="39479-154">optional</span></span>  <br/> ||<span data-ttu-id="39479-155">xsd：unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-155">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="39479-156">质量</span><span class="sxs-lookup"><span data-stu-id="39479-156">Quality</span></span>  <br/> |<span data-ttu-id="39479-157">xsd：unsignedByte</span><span class="sxs-lookup"><span data-stu-id="39479-157">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="39479-158">可选</span><span class="sxs-lookup"><span data-stu-id="39479-158">optional</span></span>  <br/> ||<span data-ttu-id="39479-159">xsd：unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-159">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="39479-160">StrikeOut</span><span class="sxs-lookup"><span data-stu-id="39479-160">StrikeOut</span></span>  <br/> |<span data-ttu-id="39479-161">xsd：unsignedByte</span><span class="sxs-lookup"><span data-stu-id="39479-161">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="39479-162">可选</span><span class="sxs-lookup"><span data-stu-id="39479-162">optional</span></span>  <br/> ||<span data-ttu-id="39479-163">xsd：unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-163">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="39479-164">下划线</span><span class="sxs-lookup"><span data-stu-id="39479-164">Underline</span></span>  <br/> |<span data-ttu-id="39479-165">xsd：unsignedByte</span><span class="sxs-lookup"><span data-stu-id="39479-165">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="39479-166">可选</span><span class="sxs-lookup"><span data-stu-id="39479-166">optional</span></span>  <br/> ||<span data-ttu-id="39479-167">xsd：unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-167">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="39479-168">粗细</span><span class="sxs-lookup"><span data-stu-id="39479-168">Weight</span></span>  <br/> |<span data-ttu-id="39479-169">xsd：int</span><span class="sxs-lookup"><span data-stu-id="39479-169">xsd:int</span></span>  <br/> |<span data-ttu-id="39479-170">可选</span><span class="sxs-lookup"><span data-stu-id="39479-170">optional</span></span>  <br/> ||<span data-ttu-id="39479-171">xsd：int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-171">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="39479-172">Width</span><span class="sxs-lookup"><span data-stu-id="39479-172">Width</span></span>  <br/> |<span data-ttu-id="39479-173">xsd：int</span><span class="sxs-lookup"><span data-stu-id="39479-173">xsd:int</span></span>  <br/> |<span data-ttu-id="39479-174">可选</span><span class="sxs-lookup"><span data-stu-id="39479-174">optional</span></span>  <br/> ||<span data-ttu-id="39479-175">xsd：int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39479-175">Values of the xsd:int type.</span></span>  <br/> |
   

