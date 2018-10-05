---
title: DataColumn_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bee50623-cdf7-b9d7-867a-70c86922cbac
ms.openlocfilehash: 69f994b9516b04ddca8d26a645161772dc77c470
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388656"
---
# <a name="datacolumntype-complextype-visio-xml"></a><span data-ttu-id="5d9e3-102">DataColumn_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="5d9e3-102">DataColumn_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="5d9e3-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="5d9e3-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5d9e3-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5d9e3-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="5d9e3-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5d9e3-105">**Schema file**</span></span> <br/> |<span data-ttu-id="5d9e3-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="5d9e3-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="5d9e3-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="5d9e3-107">**Extension base**</span></span> <br/> |<span data-ttu-id="5d9e3-108">无</span><span class="sxs-lookup"><span data-stu-id="5d9e3-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5d9e3-109">定义</span><span class="sxs-lookup"><span data-stu-id="5d9e3-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="5d9e3-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5d9e3-110">Elements and attributes</span></span>

<span data-ttu-id="5d9e3-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="5d9e3-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5d9e3-112">Child elements</span></span>

<span data-ttu-id="5d9e3-113">无。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="5d9e3-114">属性</span><span class="sxs-lookup"><span data-stu-id="5d9e3-114">Attributes</span></span>

|<span data-ttu-id="5d9e3-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="5d9e3-115">**Attribute**</span></span>|<span data-ttu-id="5d9e3-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="5d9e3-116">**Type**</span></span>|<span data-ttu-id="5d9e3-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="5d9e3-117">**Required**</span></span>|<span data-ttu-id="5d9e3-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="5d9e3-118">**Description**</span></span>|<span data-ttu-id="5d9e3-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="5d9e3-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5d9e3-120">日历</span><span class="sxs-lookup"><span data-stu-id="5d9e3-120">Calendar</span></span>  <br/> |<span data-ttu-id="5d9e3-121">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="5d9e3-121">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="5d9e3-122">可选</span><span class="sxs-lookup"><span data-stu-id="5d9e3-122">optional</span></span>  <br/> ||<span data-ttu-id="5d9e3-123">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-123">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-124">ColumnNameID</span><span class="sxs-lookup"><span data-stu-id="5d9e3-124">ColumnNameID</span></span>  <br/> |<span data-ttu-id="5d9e3-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5d9e3-125">xsd:string</span></span>  <br/> |<span data-ttu-id="5d9e3-126">必需</span><span class="sxs-lookup"><span data-stu-id="5d9e3-126">required</span></span>  <br/> ||<span data-ttu-id="5d9e3-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-128">货币</span><span class="sxs-lookup"><span data-stu-id="5d9e3-128">Currency</span></span>  <br/> |<span data-ttu-id="5d9e3-129">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="5d9e3-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="5d9e3-130">可选</span><span class="sxs-lookup"><span data-stu-id="5d9e3-130">optional</span></span>  <br/> ||<span data-ttu-id="5d9e3-131">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-132">DataType</span><span class="sxs-lookup"><span data-stu-id="5d9e3-132">DataType</span></span>  <br/> |<span data-ttu-id="5d9e3-133">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="5d9e3-133">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="5d9e3-134">可选</span><span class="sxs-lookup"><span data-stu-id="5d9e3-134">optional</span></span>  <br/> ||<span data-ttu-id="5d9e3-135">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-135">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-136">Degree</span><span class="sxs-lookup"><span data-stu-id="5d9e3-136">Degree</span></span>  <br/> |<span data-ttu-id="5d9e3-137">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5d9e3-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5d9e3-138">可选</span><span class="sxs-lookup"><span data-stu-id="5d9e3-138">optional</span></span>  <br/> ||<span data-ttu-id="5d9e3-139">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-139">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-140">DisplayOrder</span><span class="sxs-lookup"><span data-stu-id="5d9e3-140">DisplayOrder</span></span>  <br/> |<span data-ttu-id="5d9e3-141">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5d9e3-141">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5d9e3-142">可选</span><span class="sxs-lookup"><span data-stu-id="5d9e3-142">optional</span></span>  <br/> ||<span data-ttu-id="5d9e3-143">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-144">DisplayWidth</span><span class="sxs-lookup"><span data-stu-id="5d9e3-144">DisplayWidth</span></span>  <br/> |<span data-ttu-id="5d9e3-145">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5d9e3-145">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5d9e3-146">可选</span><span class="sxs-lookup"><span data-stu-id="5d9e3-146">optional</span></span>  <br/> ||<span data-ttu-id="5d9e3-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-148">超链接</span><span class="sxs-lookup"><span data-stu-id="5d9e3-148">Hyperlink</span></span>  <br/> |<span data-ttu-id="5d9e3-149">化</span><span class="sxs-lookup"><span data-stu-id="5d9e3-149">xsd:boolean</span></span>  <br/> |<span data-ttu-id="5d9e3-150">可选</span><span class="sxs-lookup"><span data-stu-id="5d9e3-150">optional</span></span>  <br/> ||<span data-ttu-id="5d9e3-151">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-151">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-152">标签</span><span class="sxs-lookup"><span data-stu-id="5d9e3-152">Label</span></span>  <br/> |<span data-ttu-id="5d9e3-153">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5d9e3-153">xsd:string</span></span>  <br/> |<span data-ttu-id="5d9e3-154">必需</span><span class="sxs-lookup"><span data-stu-id="5d9e3-154">required</span></span>  <br/> ||<span data-ttu-id="5d9e3-155">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-156">LangID</span><span class="sxs-lookup"><span data-stu-id="5d9e3-156">LangID</span></span>  <br/> |<span data-ttu-id="5d9e3-157">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5d9e3-157">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5d9e3-158">可选</span><span class="sxs-lookup"><span data-stu-id="5d9e3-158">optional</span></span>  <br/> ||<span data-ttu-id="5d9e3-159">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-159">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-160">映射</span><span class="sxs-lookup"><span data-stu-id="5d9e3-160">Mapped</span></span>  <br/> |<span data-ttu-id="5d9e3-161">化</span><span class="sxs-lookup"><span data-stu-id="5d9e3-161">xsd:boolean</span></span>  <br/> |<span data-ttu-id="5d9e3-162">可选</span><span class="sxs-lookup"><span data-stu-id="5d9e3-162">optional</span></span>  <br/> ||<span data-ttu-id="5d9e3-163">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-163">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-164">名称</span><span class="sxs-lookup"><span data-stu-id="5d9e3-164">Name</span></span>  <br/> |<span data-ttu-id="5d9e3-165">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5d9e3-165">xsd:string</span></span>  <br/> |<span data-ttu-id="5d9e3-166">必需</span><span class="sxs-lookup"><span data-stu-id="5d9e3-166">required</span></span>  <br/> ||<span data-ttu-id="5d9e3-167">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-167">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-168">OrigLabel</span><span class="sxs-lookup"><span data-stu-id="5d9e3-168">OrigLabel</span></span>  <br/> |<span data-ttu-id="5d9e3-169">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5d9e3-169">xsd:string</span></span>  <br/> |<span data-ttu-id="5d9e3-170">可选</span><span class="sxs-lookup"><span data-stu-id="5d9e3-170">optional</span></span>  <br/> ||<span data-ttu-id="5d9e3-171">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-171">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="5d9e3-172">UnitType</span><span class="sxs-lookup"><span data-stu-id="5d9e3-172">UnitType</span></span>  <br/> |<span data-ttu-id="5d9e3-173">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5d9e3-173">xsd:string</span></span>  <br/> |<span data-ttu-id="5d9e3-174">可选</span><span class="sxs-lookup"><span data-stu-id="5d9e3-174">optional</span></span>  <br/> ||<span data-ttu-id="5d9e3-175">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-175">Values of the xsd:string type.</span></span>  <br/> |
   

