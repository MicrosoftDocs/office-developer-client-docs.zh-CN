---
title: DataColumn_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bee50623-cdf7-b9d7-867a-70c86922cbac
ms.openlocfilehash: 69f994b9516b04ddca8d26a645161772dc77c470
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344700"
---
# <a name="datacolumntype-complextype-visio-xml"></a><span data-ttu-id="68205-102">DataColumn_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="68205-102">DataColumn_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="68205-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="68205-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="68205-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="68205-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="68205-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="68205-105">**Schema file**</span></span> <br/> |<span data-ttu-id="68205-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="68205-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="68205-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="68205-107">**Extension base**</span></span> <br/> |<span data-ttu-id="68205-108">无</span><span class="sxs-lookup"><span data-stu-id="68205-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="68205-109">定义</span><span class="sxs-lookup"><span data-stu-id="68205-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="68205-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="68205-110">Elements and attributes</span></span>

<span data-ttu-id="68205-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="68205-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="68205-112">子元素</span><span class="sxs-lookup"><span data-stu-id="68205-112">Child elements</span></span>

<span data-ttu-id="68205-113">无。</span><span class="sxs-lookup"><span data-stu-id="68205-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="68205-114">属性</span><span class="sxs-lookup"><span data-stu-id="68205-114">Attributes</span></span>

|<span data-ttu-id="68205-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="68205-115">**Attribute**</span></span>|<span data-ttu-id="68205-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="68205-116">**Type**</span></span>|<span data-ttu-id="68205-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="68205-117">**Required**</span></span>|<span data-ttu-id="68205-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="68205-118">**Description**</span></span>|<span data-ttu-id="68205-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="68205-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="68205-120">日历</span><span class="sxs-lookup"><span data-stu-id="68205-120">Calendar</span></span>  <br/> |<span data-ttu-id="68205-121">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="68205-121">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="68205-122">可选</span><span class="sxs-lookup"><span data-stu-id="68205-122">optional</span></span>  <br/> ||<span data-ttu-id="68205-123">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-123">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="68205-124">ColumnNameID</span><span class="sxs-lookup"><span data-stu-id="68205-124">ColumnNameID</span></span>  <br/> |<span data-ttu-id="68205-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="68205-125">xsd:string</span></span>  <br/> |<span data-ttu-id="68205-126">必需</span><span class="sxs-lookup"><span data-stu-id="68205-126">required</span></span>  <br/> ||<span data-ttu-id="68205-127">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="68205-128">货币</span><span class="sxs-lookup"><span data-stu-id="68205-128">Currency</span></span>  <br/> |<span data-ttu-id="68205-129">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="68205-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="68205-130">可选</span><span class="sxs-lookup"><span data-stu-id="68205-130">optional</span></span>  <br/> ||<span data-ttu-id="68205-131">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="68205-132">DataType</span><span class="sxs-lookup"><span data-stu-id="68205-132">DataType</span></span>  <br/> |<span data-ttu-id="68205-133">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="68205-133">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="68205-134">可选</span><span class="sxs-lookup"><span data-stu-id="68205-134">optional</span></span>  <br/> ||<span data-ttu-id="68205-135">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-135">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="68205-136">Degree</span><span class="sxs-lookup"><span data-stu-id="68205-136">Degree</span></span>  <br/> |<span data-ttu-id="68205-137">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="68205-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="68205-138">可选</span><span class="sxs-lookup"><span data-stu-id="68205-138">optional</span></span>  <br/> ||<span data-ttu-id="68205-139">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-139">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="68205-140">DisplayOrder</span><span class="sxs-lookup"><span data-stu-id="68205-140">DisplayOrder</span></span>  <br/> |<span data-ttu-id="68205-141">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="68205-141">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="68205-142">可选</span><span class="sxs-lookup"><span data-stu-id="68205-142">optional</span></span>  <br/> ||<span data-ttu-id="68205-143">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="68205-144">DisplayWidth</span><span class="sxs-lookup"><span data-stu-id="68205-144">DisplayWidth</span></span>  <br/> |<span data-ttu-id="68205-145">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="68205-145">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="68205-146">可选</span><span class="sxs-lookup"><span data-stu-id="68205-146">optional</span></span>  <br/> ||<span data-ttu-id="68205-147">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="68205-148">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="68205-148">Hyperlink</span></span>  <br/> |<span data-ttu-id="68205-149">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="68205-149">xsd:boolean</span></span>  <br/> |<span data-ttu-id="68205-150">可选</span><span class="sxs-lookup"><span data-stu-id="68205-150">optional</span></span>  <br/> ||<span data-ttu-id="68205-151">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-151">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="68205-152">标签</span><span class="sxs-lookup"><span data-stu-id="68205-152">Label</span></span>  <br/> |<span data-ttu-id="68205-153">xsd: string</span><span class="sxs-lookup"><span data-stu-id="68205-153">xsd:string</span></span>  <br/> |<span data-ttu-id="68205-154">必需</span><span class="sxs-lookup"><span data-stu-id="68205-154">required</span></span>  <br/> ||<span data-ttu-id="68205-155">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="68205-156">LangID</span><span class="sxs-lookup"><span data-stu-id="68205-156">LangID</span></span>  <br/> |<span data-ttu-id="68205-157">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="68205-157">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="68205-158">可选</span><span class="sxs-lookup"><span data-stu-id="68205-158">optional</span></span>  <br/> ||<span data-ttu-id="68205-159">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-159">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="68205-160">分区</span><span class="sxs-lookup"><span data-stu-id="68205-160">Mapped</span></span>  <br/> |<span data-ttu-id="68205-161">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="68205-161">xsd:boolean</span></span>  <br/> |<span data-ttu-id="68205-162">可选</span><span class="sxs-lookup"><span data-stu-id="68205-162">optional</span></span>  <br/> ||<span data-ttu-id="68205-163">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-163">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="68205-164">名称</span><span class="sxs-lookup"><span data-stu-id="68205-164">Name</span></span>  <br/> |<span data-ttu-id="68205-165">xsd: string</span><span class="sxs-lookup"><span data-stu-id="68205-165">xsd:string</span></span>  <br/> |<span data-ttu-id="68205-166">必需</span><span class="sxs-lookup"><span data-stu-id="68205-166">required</span></span>  <br/> ||<span data-ttu-id="68205-167">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-167">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="68205-168">OrigLabel</span><span class="sxs-lookup"><span data-stu-id="68205-168">OrigLabel</span></span>  <br/> |<span data-ttu-id="68205-169">xsd: string</span><span class="sxs-lookup"><span data-stu-id="68205-169">xsd:string</span></span>  <br/> |<span data-ttu-id="68205-170">可选</span><span class="sxs-lookup"><span data-stu-id="68205-170">optional</span></span>  <br/> ||<span data-ttu-id="68205-171">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-171">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="68205-172">UnitType</span><span class="sxs-lookup"><span data-stu-id="68205-172">UnitType</span></span>  <br/> |<span data-ttu-id="68205-173">xsd: string</span><span class="sxs-lookup"><span data-stu-id="68205-173">xsd:string</span></span>  <br/> |<span data-ttu-id="68205-174">可选</span><span class="sxs-lookup"><span data-stu-id="68205-174">optional</span></span>  <br/> ||<span data-ttu-id="68205-175">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="68205-175">Values of the xsd:string type.</span></span>  <br/> |
   

