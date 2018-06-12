---
title: DataColumn_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bee50623-cdf7-b9d7-867a-70c86922cbac
ms.openlocfilehash: 9d334190b686f3b2c5e25a31336c668c957e820f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780025"
---
# <a name="datacolumntype-complextype-visio-xml"></a><span data-ttu-id="f3914-102">DataColumn_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f3914-102">DataColumn_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="f3914-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="f3914-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f3914-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f3914-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="f3914-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f3914-105">**Schema file**</span></span> <br/> |<span data-ttu-id="f3914-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="f3914-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="f3914-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="f3914-107">**Extension base**</span></span> <br/> |<span data-ttu-id="f3914-108">无</span><span class="sxs-lookup"><span data-stu-id="f3914-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f3914-109">定义</span><span class="sxs-lookup"><span data-stu-id="f3914-109">Definition</span></span>

```XML
      <xs:complexType name="DataColumn_Type">
    <xs:attribute name="ColumnNameID"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="Name"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="Label"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="OrigLabel"
  type="xsd:string"
    />
    <xs:attribute name="LangID"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Calendar"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="DataType"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="UnitType"
  type="xsd:string"
    />
    <xs:attribute name="Currency"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="Degree"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="DisplayWidth"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="DisplayOrder"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Mapped"
  type="xsd:boolean"
    />
    <xs:attribute name="Hyperlink"
  type="xsd:boolean"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f3914-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f3914-110">Elements and attributes</span></span>

<span data-ttu-id="f3914-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f3914-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="f3914-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f3914-112">Child elements</span></span>

<span data-ttu-id="f3914-113">无。</span><span class="sxs-lookup"><span data-stu-id="f3914-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="f3914-114">属性</span><span class="sxs-lookup"><span data-stu-id="f3914-114">Attributes</span></span>

|<span data-ttu-id="f3914-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="f3914-115">**Attribute**</span></span>|<span data-ttu-id="f3914-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="f3914-116">**Type**</span></span>|<span data-ttu-id="f3914-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="f3914-117">**Required**</span></span>|<span data-ttu-id="f3914-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="f3914-118">**Description**</span></span>|<span data-ttu-id="f3914-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f3914-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f3914-120">日历</span><span class="sxs-lookup"><span data-stu-id="f3914-120">Calendar</span></span>  <br/> |<span data-ttu-id="f3914-121">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="f3914-121">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="f3914-122">可选</span><span class="sxs-lookup"><span data-stu-id="f3914-122">optional</span></span>  <br/> ||<span data-ttu-id="f3914-123">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-123">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="f3914-124">ColumnNameID</span><span class="sxs-lookup"><span data-stu-id="f3914-124">ColumnNameID</span></span>  <br/> |<span data-ttu-id="f3914-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f3914-125">xsd:string</span></span>  <br/> |<span data-ttu-id="f3914-126">必需</span><span class="sxs-lookup"><span data-stu-id="f3914-126">required</span></span>  <br/> ||<span data-ttu-id="f3914-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="f3914-128">货币</span><span class="sxs-lookup"><span data-stu-id="f3914-128">Currency</span></span>  <br/> |<span data-ttu-id="f3914-129">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="f3914-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="f3914-130">可选</span><span class="sxs-lookup"><span data-stu-id="f3914-130">optional</span></span>  <br/> ||<span data-ttu-id="f3914-131">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="f3914-132">DataType</span><span class="sxs-lookup"><span data-stu-id="f3914-132">DataType</span></span>  <br/> |<span data-ttu-id="f3914-133">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="f3914-133">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="f3914-134">可选</span><span class="sxs-lookup"><span data-stu-id="f3914-134">optional</span></span>  <br/> ||<span data-ttu-id="f3914-135">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-135">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="f3914-136">度</span><span class="sxs-lookup"><span data-stu-id="f3914-136">Degree</span></span>  <br/> |<span data-ttu-id="f3914-137">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="f3914-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="f3914-138">可选</span><span class="sxs-lookup"><span data-stu-id="f3914-138">optional</span></span>  <br/> ||<span data-ttu-id="f3914-139">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-139">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="f3914-140">DisplayOrder</span><span class="sxs-lookup"><span data-stu-id="f3914-140">DisplayOrder</span></span>  <br/> |<span data-ttu-id="f3914-141">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="f3914-141">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="f3914-142">可选</span><span class="sxs-lookup"><span data-stu-id="f3914-142">optional</span></span>  <br/> ||<span data-ttu-id="f3914-143">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="f3914-144">DisplayWidth</span><span class="sxs-lookup"><span data-stu-id="f3914-144">DisplayWidth</span></span>  <br/> |<span data-ttu-id="f3914-145">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="f3914-145">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="f3914-146">可选</span><span class="sxs-lookup"><span data-stu-id="f3914-146">optional</span></span>  <br/> ||<span data-ttu-id="f3914-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="f3914-148">超链接</span><span class="sxs-lookup"><span data-stu-id="f3914-148">Hyperlink</span></span>  <br/> |<span data-ttu-id="f3914-149">化</span><span class="sxs-lookup"><span data-stu-id="f3914-149">xsd:boolean</span></span>  <br/> |<span data-ttu-id="f3914-150">可选</span><span class="sxs-lookup"><span data-stu-id="f3914-150">optional</span></span>  <br/> ||<span data-ttu-id="f3914-151">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-151">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="f3914-152">标签</span><span class="sxs-lookup"><span data-stu-id="f3914-152">Label</span></span>  <br/> |<span data-ttu-id="f3914-153">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f3914-153">xsd:string</span></span>  <br/> |<span data-ttu-id="f3914-154">必需</span><span class="sxs-lookup"><span data-stu-id="f3914-154">required</span></span>  <br/> ||<span data-ttu-id="f3914-155">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="f3914-156">LangID</span><span class="sxs-lookup"><span data-stu-id="f3914-156">LangID</span></span>  <br/> |<span data-ttu-id="f3914-157">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="f3914-157">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="f3914-158">可选</span><span class="sxs-lookup"><span data-stu-id="f3914-158">optional</span></span>  <br/> ||<span data-ttu-id="f3914-159">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-159">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="f3914-160">映射</span><span class="sxs-lookup"><span data-stu-id="f3914-160">Mapped</span></span>  <br/> |<span data-ttu-id="f3914-161">化</span><span class="sxs-lookup"><span data-stu-id="f3914-161">xsd:boolean</span></span>  <br/> |<span data-ttu-id="f3914-162">可选</span><span class="sxs-lookup"><span data-stu-id="f3914-162">optional</span></span>  <br/> ||<span data-ttu-id="f3914-163">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-163">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="f3914-164">名称</span><span class="sxs-lookup"><span data-stu-id="f3914-164">Name</span></span>  <br/> |<span data-ttu-id="f3914-165">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f3914-165">xsd:string</span></span>  <br/> |<span data-ttu-id="f3914-166">必需</span><span class="sxs-lookup"><span data-stu-id="f3914-166">required</span></span>  <br/> ||<span data-ttu-id="f3914-167">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-167">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="f3914-168">OrigLabel</span><span class="sxs-lookup"><span data-stu-id="f3914-168">OrigLabel</span></span>  <br/> |<span data-ttu-id="f3914-169">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f3914-169">xsd:string</span></span>  <br/> |<span data-ttu-id="f3914-170">可选</span><span class="sxs-lookup"><span data-stu-id="f3914-170">optional</span></span>  <br/> ||<span data-ttu-id="f3914-171">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-171">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="f3914-172">UnitType</span><span class="sxs-lookup"><span data-stu-id="f3914-172">UnitType</span></span>  <br/> |<span data-ttu-id="f3914-173">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f3914-173">xsd:string</span></span>  <br/> |<span data-ttu-id="f3914-174">可选</span><span class="sxs-lookup"><span data-stu-id="f3914-174">optional</span></span>  <br/> ||<span data-ttu-id="f3914-175">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f3914-175">Values of the xsd:string type.</span></span>  <br/> |
   

