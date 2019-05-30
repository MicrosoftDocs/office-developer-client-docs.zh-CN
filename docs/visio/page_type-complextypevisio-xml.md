---
title: Page_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4bc5c0c4-3ee3-7f63-541a-1f1854d4201c
ms.openlocfilehash: 3a0153b724539136fe142c2489badcf9895af765
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537981"
---
# <a name="pagetype-complextype-visio-xml"></a><span data-ttu-id="1d630-102">Page_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="1d630-102">Page_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="1d630-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="1d630-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1d630-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1d630-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="1d630-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1d630-105">**Schema file**</span></span> <br/> |<span data-ttu-id="1d630-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="1d630-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="1d630-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="1d630-107">**Extension base**</span></span> <br/> |<span data-ttu-id="1d630-108">无</span><span class="sxs-lookup"><span data-stu-id="1d630-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1d630-109">定义</span><span class="sxs-lookup"><span data-stu-id="1d630-109">Definition</span></span>

```XML
          <xs:complexType name="Page_Type">
          
          <xs:all>
    <xs:element name="PageSheet"  type="PageSheet_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Rel"  type="Rel_Type"
     minOccurs="1"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:all>
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="Name"
  type="xsd:string"
    />
    <xs:attribute name="NameU"
  type="xsd:string"
    />
    <xs:attribute name="IsCustomName"
  type="xsd:boolean"
    />
    <xs:attribute name="IsCustomNameU"
  type="xsd:boolean"
    />
    <xs:attribute name="Background"
  type="xsd:boolean"
    />
    <xs:attribute name="BackPage"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="ViewScale"
  type="xsd:double"
    />
    <xs:attribute name="ViewCenterX"
  type="xsd:double"
    />
    <xs:attribute name="ViewCenterY"
  type="xsd:double"
    />
    <xs:attribute name="ReviewerID"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="AssociatedPage"
  type="xsd:unsignedInt"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="1d630-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1d630-110">Elements and attributes</span></span>

<span data-ttu-id="1d630-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="1d630-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="1d630-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1d630-112">Child elements</span></span>

|<span data-ttu-id="1d630-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="1d630-113">**Element**</span></span>|<span data-ttu-id="1d630-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="1d630-114">**Type**</span></span>|<span data-ttu-id="1d630-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="1d630-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1d630-116">PageSheet</span><span class="sxs-lookup"><span data-stu-id="1d630-116">PageSheet</span></span>](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1d630-117">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="1d630-117">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="1d630-118">相对</span><span class="sxs-lookup"><span data-stu-id="1d630-118">Rel</span></span>](rel-element-page_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1d630-119">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="1d630-119">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="1d630-120">属性</span><span class="sxs-lookup"><span data-stu-id="1d630-120">Attributes</span></span>

|<span data-ttu-id="1d630-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="1d630-121">**Attribute**</span></span>|<span data-ttu-id="1d630-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="1d630-122">**Type**</span></span>|<span data-ttu-id="1d630-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="1d630-123">**Required**</span></span>|<span data-ttu-id="1d630-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="1d630-124">**Description**</span></span>|<span data-ttu-id="1d630-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1d630-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1d630-126">AssociatedPage</span><span class="sxs-lookup"><span data-stu-id="1d630-126">AssociatedPage</span></span>  <br/> |<span data-ttu-id="1d630-127">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="1d630-127">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="1d630-128">可选</span><span class="sxs-lookup"><span data-stu-id="1d630-128">optional</span></span>  <br/> ||<span data-ttu-id="1d630-129">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1d630-129">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="1d630-130">背景</span><span class="sxs-lookup"><span data-stu-id="1d630-130">Background</span></span>  <br/> |<span data-ttu-id="1d630-131">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="1d630-131">xsd:boolean</span></span>  <br/> |<span data-ttu-id="1d630-132">可选</span><span class="sxs-lookup"><span data-stu-id="1d630-132">optional</span></span>  <br/> ||<span data-ttu-id="1d630-133">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1d630-133">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="1d630-134">BackPage</span><span class="sxs-lookup"><span data-stu-id="1d630-134">BackPage</span></span>  <br/> |<span data-ttu-id="1d630-135">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="1d630-135">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="1d630-136">可选</span><span class="sxs-lookup"><span data-stu-id="1d630-136">optional</span></span>  <br/> ||<span data-ttu-id="1d630-137">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1d630-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="1d630-138">ID</span><span class="sxs-lookup"><span data-stu-id="1d630-138">ID</span></span>  <br/> |<span data-ttu-id="1d630-139">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="1d630-139">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="1d630-140">必需</span><span class="sxs-lookup"><span data-stu-id="1d630-140">required</span></span>  <br/> ||<span data-ttu-id="1d630-141">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1d630-141">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="1d630-142">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="1d630-142">IsCustomName</span></span>  <br/> |<span data-ttu-id="1d630-143">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="1d630-143">xsd:boolean</span></span>  <br/> |<span data-ttu-id="1d630-144">可选</span><span class="sxs-lookup"><span data-stu-id="1d630-144">optional</span></span>  <br/> ||<span data-ttu-id="1d630-145">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1d630-145">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="1d630-146">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="1d630-146">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="1d630-147">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="1d630-147">xsd:boolean</span></span>  <br/> |<span data-ttu-id="1d630-148">可选</span><span class="sxs-lookup"><span data-stu-id="1d630-148">optional</span></span>  <br/> ||<span data-ttu-id="1d630-149">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1d630-149">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="1d630-150">名称</span><span class="sxs-lookup"><span data-stu-id="1d630-150">Name</span></span>  <br/> |<span data-ttu-id="1d630-151">xsd: string</span><span class="sxs-lookup"><span data-stu-id="1d630-151">xsd:string</span></span>  <br/> |<span data-ttu-id="1d630-152">可选</span><span class="sxs-lookup"><span data-stu-id="1d630-152">optional</span></span>  <br/> ||<span data-ttu-id="1d630-153">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1d630-153">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="1d630-154">NameU</span><span class="sxs-lookup"><span data-stu-id="1d630-154">NameU</span></span>  <br/> |<span data-ttu-id="1d630-155">xsd: string</span><span class="sxs-lookup"><span data-stu-id="1d630-155">xsd:string</span></span>  <br/> |<span data-ttu-id="1d630-156">可选</span><span class="sxs-lookup"><span data-stu-id="1d630-156">optional</span></span>  <br/> ||<span data-ttu-id="1d630-157">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1d630-157">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="1d630-158">ReviewerID</span><span class="sxs-lookup"><span data-stu-id="1d630-158">ReviewerID</span></span>  <br/> |<span data-ttu-id="1d630-159">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="1d630-159">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="1d630-160">可选</span><span class="sxs-lookup"><span data-stu-id="1d630-160">optional</span></span>  <br/> ||<span data-ttu-id="1d630-161">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1d630-161">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="1d630-162">ViewCenterX</span><span class="sxs-lookup"><span data-stu-id="1d630-162">ViewCenterX</span></span>  <br/> |<span data-ttu-id="1d630-163">xsd: double</span><span class="sxs-lookup"><span data-stu-id="1d630-163">xsd:double</span></span>  <br/> |<span data-ttu-id="1d630-164">可选</span><span class="sxs-lookup"><span data-stu-id="1d630-164">optional</span></span>  <br/> ||<span data-ttu-id="1d630-165">Xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1d630-165">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="1d630-166">ViewCenterY</span><span class="sxs-lookup"><span data-stu-id="1d630-166">ViewCenterY</span></span>  <br/> |<span data-ttu-id="1d630-167">xsd: double</span><span class="sxs-lookup"><span data-stu-id="1d630-167">xsd:double</span></span>  <br/> |<span data-ttu-id="1d630-168">可选</span><span class="sxs-lookup"><span data-stu-id="1d630-168">optional</span></span>  <br/> ||<span data-ttu-id="1d630-169">Xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1d630-169">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="1d630-170">ViewScale</span><span class="sxs-lookup"><span data-stu-id="1d630-170">ViewScale</span></span>  <br/> |<span data-ttu-id="1d630-171">xsd: double</span><span class="sxs-lookup"><span data-stu-id="1d630-171">xsd:double</span></span>  <br/> |<span data-ttu-id="1d630-172">可选</span><span class="sxs-lookup"><span data-stu-id="1d630-172">optional</span></span>  <br/> ||<span data-ttu-id="1d630-173">Xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1d630-173">Values of the xsd:double type.</span></span>  <br/> |
   

