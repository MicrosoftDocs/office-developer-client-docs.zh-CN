---
title: Page_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4bc5c0c4-3ee3-7f63-541a-1f1854d4201c
ms.openlocfilehash: d0c364164d2453c9dc64290db24890224a3c70e1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401550"
---
# <a name="pagetype-complextype-visio-xml"></a><span data-ttu-id="a3614-102">Page_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="a3614-102">Page_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="a3614-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="a3614-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a3614-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="a3614-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="a3614-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="a3614-105">**Schema file**</span></span> <br/> |<span data-ttu-id="a3614-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="a3614-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="a3614-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="a3614-107">**Extension base**</span></span> <br/> |<span data-ttu-id="a3614-108">无</span><span class="sxs-lookup"><span data-stu-id="a3614-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="a3614-109">定义</span><span class="sxs-lookup"><span data-stu-id="a3614-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="a3614-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="a3614-110">Elements and attributes</span></span>

<span data-ttu-id="a3614-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="a3614-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="a3614-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a3614-112">Child elements</span></span>

|<span data-ttu-id="a3614-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="a3614-113">**Element**</span></span>|<span data-ttu-id="a3614-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="a3614-114">**Type**</span></span>|<span data-ttu-id="a3614-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="a3614-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a3614-116">PageSheet</span><span class="sxs-lookup"><span data-stu-id="a3614-116">PageSheet</span></span>](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="a3614-117">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="a3614-117">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="a3614-118">Rel</span><span class="sxs-lookup"><span data-stu-id="a3614-118">Rel</span></span>](rel-element-page_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="a3614-119">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="a3614-119">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="a3614-120">Attributes</span><span class="sxs-lookup"><span data-stu-id="a3614-120">Attributes</span></span>

|<span data-ttu-id="a3614-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="a3614-121">**Attribute**</span></span>|<span data-ttu-id="a3614-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="a3614-122">**Type**</span></span>|<span data-ttu-id="a3614-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="a3614-123">**Required**</span></span>|<span data-ttu-id="a3614-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="a3614-124">**Description**</span></span>|<span data-ttu-id="a3614-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a3614-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a3614-126">AssociatedPage</span><span class="sxs-lookup"><span data-stu-id="a3614-126">AssociatedPage</span></span>  <br/> |<span data-ttu-id="a3614-127">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="a3614-127">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="a3614-128">可选</span><span class="sxs-lookup"><span data-stu-id="a3614-128">optional</span></span>  <br/> ||<span data-ttu-id="a3614-129">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a3614-129">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="a3614-130">背景</span><span class="sxs-lookup"><span data-stu-id="a3614-130">Background</span></span>  <br/> |<span data-ttu-id="a3614-131">化</span><span class="sxs-lookup"><span data-stu-id="a3614-131">xsd:boolean</span></span>  <br/> |<span data-ttu-id="a3614-132">可选</span><span class="sxs-lookup"><span data-stu-id="a3614-132">optional</span></span>  <br/> ||<span data-ttu-id="a3614-133">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="a3614-133">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="a3614-134">BackPage</span><span class="sxs-lookup"><span data-stu-id="a3614-134">BackPage</span></span>  <br/> |<span data-ttu-id="a3614-135">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="a3614-135">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="a3614-136">可选</span><span class="sxs-lookup"><span data-stu-id="a3614-136">optional</span></span>  <br/> ||<span data-ttu-id="a3614-137">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a3614-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="a3614-138">ID</span><span class="sxs-lookup"><span data-stu-id="a3614-138">ID</span></span>  <br/> |<span data-ttu-id="a3614-139">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="a3614-139">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="a3614-140">必需</span><span class="sxs-lookup"><span data-stu-id="a3614-140">required</span></span>  <br/> ||<span data-ttu-id="a3614-141">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a3614-141">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="a3614-142">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="a3614-142">IsCustomName</span></span>  <br/> |<span data-ttu-id="a3614-143">化</span><span class="sxs-lookup"><span data-stu-id="a3614-143">xsd:boolean</span></span>  <br/> |<span data-ttu-id="a3614-144">可选</span><span class="sxs-lookup"><span data-stu-id="a3614-144">optional</span></span>  <br/> ||<span data-ttu-id="a3614-145">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="a3614-145">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="a3614-146">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="a3614-146">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="a3614-147">化</span><span class="sxs-lookup"><span data-stu-id="a3614-147">xsd:boolean</span></span>  <br/> |<span data-ttu-id="a3614-148">可选</span><span class="sxs-lookup"><span data-stu-id="a3614-148">optional</span></span>  <br/> ||<span data-ttu-id="a3614-149">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="a3614-149">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="a3614-150">名称</span><span class="sxs-lookup"><span data-stu-id="a3614-150">Name</span></span>  <br/> |<span data-ttu-id="a3614-151">xsd: string</span><span class="sxs-lookup"><span data-stu-id="a3614-151">xsd:string</span></span>  <br/> |<span data-ttu-id="a3614-152">可选</span><span class="sxs-lookup"><span data-stu-id="a3614-152">optional</span></span>  <br/> ||<span data-ttu-id="a3614-153">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a3614-153">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="a3614-154">NameU</span><span class="sxs-lookup"><span data-stu-id="a3614-154">NameU</span></span>  <br/> |<span data-ttu-id="a3614-155">xsd: string</span><span class="sxs-lookup"><span data-stu-id="a3614-155">xsd:string</span></span>  <br/> |<span data-ttu-id="a3614-156">可选</span><span class="sxs-lookup"><span data-stu-id="a3614-156">optional</span></span>  <br/> ||<span data-ttu-id="a3614-157">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a3614-157">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="a3614-158">ReviewerID</span><span class="sxs-lookup"><span data-stu-id="a3614-158">ReviewerID</span></span>  <br/> |<span data-ttu-id="a3614-159">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="a3614-159">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="a3614-160">可选</span><span class="sxs-lookup"><span data-stu-id="a3614-160">optional</span></span>  <br/> ||<span data-ttu-id="a3614-161">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a3614-161">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="a3614-162">ViewCenterX</span><span class="sxs-lookup"><span data-stu-id="a3614-162">ViewCenterX</span></span>  <br/> |<span data-ttu-id="a3614-163">化</span><span class="sxs-lookup"><span data-stu-id="a3614-163">xsd:double</span></span>  <br/> |<span data-ttu-id="a3614-164">可选</span><span class="sxs-lookup"><span data-stu-id="a3614-164">optional</span></span>  <br/> ||<span data-ttu-id="a3614-165">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="a3614-165">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="a3614-166">ViewCenterY</span><span class="sxs-lookup"><span data-stu-id="a3614-166">ViewCenterY</span></span>  <br/> |<span data-ttu-id="a3614-167">化</span><span class="sxs-lookup"><span data-stu-id="a3614-167">xsd:double</span></span>  <br/> |<span data-ttu-id="a3614-168">可选</span><span class="sxs-lookup"><span data-stu-id="a3614-168">optional</span></span>  <br/> ||<span data-ttu-id="a3614-169">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="a3614-169">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="a3614-170">ViewScale</span><span class="sxs-lookup"><span data-stu-id="a3614-170">ViewScale</span></span>  <br/> |<span data-ttu-id="a3614-171">化</span><span class="sxs-lookup"><span data-stu-id="a3614-171">xsd:double</span></span>  <br/> |<span data-ttu-id="a3614-172">可选</span><span class="sxs-lookup"><span data-stu-id="a3614-172">optional</span></span>  <br/> ||<span data-ttu-id="a3614-173">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="a3614-173">Values of the xsd:double type.</span></span>  <br/> |
   

