---
title: 'DataColumn_Type XML (Visio complexType) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bee50623-cdf7-b9d7-867a-70c86922cbac
ms.openlocfilehash: 7f35cd2ef1f6d710644033599fe4a90a0f2978ef
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541209"
---
# <a name="datacolumn_type-complextype-visio-xml"></a><span data-ttu-id="73d17-102">DataColumn_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="73d17-102">DataColumn_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="73d17-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="73d17-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="73d17-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="73d17-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="73d17-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="73d17-105">**Schema file**</span></span> <br/> |<span data-ttu-id="73d17-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="73d17-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="73d17-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="73d17-107">**Extension base**</span></span> <br/> |<span data-ttu-id="73d17-108">无</span><span class="sxs-lookup"><span data-stu-id="73d17-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="73d17-109">定义</span><span class="sxs-lookup"><span data-stu-id="73d17-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="73d17-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="73d17-110">Elements and attributes</span></span>

<span data-ttu-id="73d17-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="73d17-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="73d17-112">子元素</span><span class="sxs-lookup"><span data-stu-id="73d17-112">Child elements</span></span>

<span data-ttu-id="73d17-113">无。</span><span class="sxs-lookup"><span data-stu-id="73d17-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="73d17-114">属性</span><span class="sxs-lookup"><span data-stu-id="73d17-114">Attributes</span></span>

|<span data-ttu-id="73d17-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="73d17-115">**Attribute**</span></span>|<span data-ttu-id="73d17-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="73d17-116">**Type**</span></span>|<span data-ttu-id="73d17-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="73d17-117">**Required**</span></span>|<span data-ttu-id="73d17-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="73d17-118">**Description**</span></span>|<span data-ttu-id="73d17-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="73d17-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="73d17-120">日历</span><span class="sxs-lookup"><span data-stu-id="73d17-120">Calendar</span></span>  <br/> |<span data-ttu-id="73d17-121">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="73d17-121">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="73d17-122">可选</span><span class="sxs-lookup"><span data-stu-id="73d17-122">optional</span></span>  <br/> ||<span data-ttu-id="73d17-123">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-123">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="73d17-124">ColumnNameID</span><span class="sxs-lookup"><span data-stu-id="73d17-124">ColumnNameID</span></span>  <br/> |<span data-ttu-id="73d17-125">xsd：string</span><span class="sxs-lookup"><span data-stu-id="73d17-125">xsd:string</span></span>  <br/> |<span data-ttu-id="73d17-126">必需</span><span class="sxs-lookup"><span data-stu-id="73d17-126">required</span></span>  <br/> ||<span data-ttu-id="73d17-127">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="73d17-128">货币</span><span class="sxs-lookup"><span data-stu-id="73d17-128">Currency</span></span>  <br/> |<span data-ttu-id="73d17-129">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="73d17-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="73d17-130">可选</span><span class="sxs-lookup"><span data-stu-id="73d17-130">optional</span></span>  <br/> ||<span data-ttu-id="73d17-131">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="73d17-132">DataType</span><span class="sxs-lookup"><span data-stu-id="73d17-132">DataType</span></span>  <br/> |<span data-ttu-id="73d17-133">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="73d17-133">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="73d17-134">可选</span><span class="sxs-lookup"><span data-stu-id="73d17-134">optional</span></span>  <br/> ||<span data-ttu-id="73d17-135">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-135">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="73d17-136">Degree</span><span class="sxs-lookup"><span data-stu-id="73d17-136">Degree</span></span>  <br/> |<span data-ttu-id="73d17-137">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="73d17-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="73d17-138">可选</span><span class="sxs-lookup"><span data-stu-id="73d17-138">optional</span></span>  <br/> ||<span data-ttu-id="73d17-139">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-139">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="73d17-140">DisplayOrder</span><span class="sxs-lookup"><span data-stu-id="73d17-140">DisplayOrder</span></span>  <br/> |<span data-ttu-id="73d17-141">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="73d17-141">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="73d17-142">可选</span><span class="sxs-lookup"><span data-stu-id="73d17-142">optional</span></span>  <br/> ||<span data-ttu-id="73d17-143">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="73d17-144">DisplayWidth</span><span class="sxs-lookup"><span data-stu-id="73d17-144">DisplayWidth</span></span>  <br/> |<span data-ttu-id="73d17-145">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="73d17-145">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="73d17-146">可选</span><span class="sxs-lookup"><span data-stu-id="73d17-146">optional</span></span>  <br/> ||<span data-ttu-id="73d17-147">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="73d17-148">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="73d17-148">Hyperlink</span></span>  <br/> |<span data-ttu-id="73d17-149">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="73d17-149">xsd:boolean</span></span>  <br/> |<span data-ttu-id="73d17-150">可选</span><span class="sxs-lookup"><span data-stu-id="73d17-150">optional</span></span>  <br/> ||<span data-ttu-id="73d17-151">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-151">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="73d17-152">标签</span><span class="sxs-lookup"><span data-stu-id="73d17-152">Label</span></span>  <br/> |<span data-ttu-id="73d17-153">xsd：string</span><span class="sxs-lookup"><span data-stu-id="73d17-153">xsd:string</span></span>  <br/> |<span data-ttu-id="73d17-154">必需</span><span class="sxs-lookup"><span data-stu-id="73d17-154">required</span></span>  <br/> ||<span data-ttu-id="73d17-155">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="73d17-156">LangID</span><span class="sxs-lookup"><span data-stu-id="73d17-156">LangID</span></span>  <br/> |<span data-ttu-id="73d17-157">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="73d17-157">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="73d17-158">可选</span><span class="sxs-lookup"><span data-stu-id="73d17-158">optional</span></span>  <br/> ||<span data-ttu-id="73d17-159">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-159">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="73d17-160">映射</span><span class="sxs-lookup"><span data-stu-id="73d17-160">Mapped</span></span>  <br/> |<span data-ttu-id="73d17-161">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="73d17-161">xsd:boolean</span></span>  <br/> |<span data-ttu-id="73d17-162">可选</span><span class="sxs-lookup"><span data-stu-id="73d17-162">optional</span></span>  <br/> ||<span data-ttu-id="73d17-163">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-163">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="73d17-164">名称</span><span class="sxs-lookup"><span data-stu-id="73d17-164">Name</span></span>  <br/> |<span data-ttu-id="73d17-165">xsd：string</span><span class="sxs-lookup"><span data-stu-id="73d17-165">xsd:string</span></span>  <br/> |<span data-ttu-id="73d17-166">必需</span><span class="sxs-lookup"><span data-stu-id="73d17-166">required</span></span>  <br/> ||<span data-ttu-id="73d17-167">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-167">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="73d17-168">OrigLabel</span><span class="sxs-lookup"><span data-stu-id="73d17-168">OrigLabel</span></span>  <br/> |<span data-ttu-id="73d17-169">xsd：string</span><span class="sxs-lookup"><span data-stu-id="73d17-169">xsd:string</span></span>  <br/> |<span data-ttu-id="73d17-170">可选</span><span class="sxs-lookup"><span data-stu-id="73d17-170">optional</span></span>  <br/> ||<span data-ttu-id="73d17-171">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-171">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="73d17-172">UnitType</span><span class="sxs-lookup"><span data-stu-id="73d17-172">UnitType</span></span>  <br/> |<span data-ttu-id="73d17-173">xsd：string</span><span class="sxs-lookup"><span data-stu-id="73d17-173">xsd:string</span></span>  <br/> |<span data-ttu-id="73d17-174">可选</span><span class="sxs-lookup"><span data-stu-id="73d17-174">optional</span></span>  <br/> ||<span data-ttu-id="73d17-175">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73d17-175">Values of the xsd:string type.</span></span>  <br/> |
   

