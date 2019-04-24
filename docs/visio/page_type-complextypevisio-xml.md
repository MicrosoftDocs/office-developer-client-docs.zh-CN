---
title: Page_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4bc5c0c4-3ee3-7f63-541a-1f1854d4201c
ms.openlocfilehash: d0c364164d2453c9dc64290db24890224a3c70e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334396"
---
# <a name="pagetype-complextype-visio-xml"></a><span data-ttu-id="e2b93-102">Page_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="e2b93-102">Page_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="e2b93-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="e2b93-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e2b93-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e2b93-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="e2b93-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e2b93-105">**Schema file**</span></span> <br/> |<span data-ttu-id="e2b93-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="e2b93-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="e2b93-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="e2b93-107">**Extension base**</span></span> <br/> |<span data-ttu-id="e2b93-108">无</span><span class="sxs-lookup"><span data-stu-id="e2b93-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e2b93-109">定义</span><span class="sxs-lookup"><span data-stu-id="e2b93-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="e2b93-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e2b93-110">Elements and attributes</span></span>

<span data-ttu-id="e2b93-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="e2b93-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="e2b93-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e2b93-112">Child elements</span></span>

|<span data-ttu-id="e2b93-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="e2b93-113">**Element**</span></span>|<span data-ttu-id="e2b93-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="e2b93-114">**Type**</span></span>|<span data-ttu-id="e2b93-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="e2b93-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e2b93-116">PageSheet</span><span class="sxs-lookup"><span data-stu-id="e2b93-116">PageSheet</span></span>](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e2b93-117">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="e2b93-117">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="e2b93-118">相对</span><span class="sxs-lookup"><span data-stu-id="e2b93-118">Rel</span></span>](rel-element-page_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e2b93-119">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="e2b93-119">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="e2b93-120">属性</span><span class="sxs-lookup"><span data-stu-id="e2b93-120">Attributes</span></span>

|<span data-ttu-id="e2b93-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="e2b93-121">**Attribute**</span></span>|<span data-ttu-id="e2b93-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="e2b93-122">**Type**</span></span>|<span data-ttu-id="e2b93-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="e2b93-123">**Required**</span></span>|<span data-ttu-id="e2b93-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="e2b93-124">**Description**</span></span>|<span data-ttu-id="e2b93-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e2b93-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e2b93-126">AssociatedPage</span><span class="sxs-lookup"><span data-stu-id="e2b93-126">AssociatedPage</span></span>  <br/> |<span data-ttu-id="e2b93-127">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e2b93-127">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e2b93-128">可选</span><span class="sxs-lookup"><span data-stu-id="e2b93-128">optional</span></span>  <br/> ||<span data-ttu-id="e2b93-129">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e2b93-129">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="e2b93-130">背景</span><span class="sxs-lookup"><span data-stu-id="e2b93-130">Background</span></span>  <br/> |<span data-ttu-id="e2b93-131">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="e2b93-131">xsd:boolean</span></span>  <br/> |<span data-ttu-id="e2b93-132">可选</span><span class="sxs-lookup"><span data-stu-id="e2b93-132">optional</span></span>  <br/> ||<span data-ttu-id="e2b93-133">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e2b93-133">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="e2b93-134">BackPage</span><span class="sxs-lookup"><span data-stu-id="e2b93-134">BackPage</span></span>  <br/> |<span data-ttu-id="e2b93-135">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e2b93-135">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e2b93-136">可选</span><span class="sxs-lookup"><span data-stu-id="e2b93-136">optional</span></span>  <br/> ||<span data-ttu-id="e2b93-137">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e2b93-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="e2b93-138">ID</span><span class="sxs-lookup"><span data-stu-id="e2b93-138">ID</span></span>  <br/> |<span data-ttu-id="e2b93-139">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e2b93-139">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e2b93-140">必需</span><span class="sxs-lookup"><span data-stu-id="e2b93-140">required</span></span>  <br/> ||<span data-ttu-id="e2b93-141">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e2b93-141">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="e2b93-142">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="e2b93-142">IsCustomName</span></span>  <br/> |<span data-ttu-id="e2b93-143">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="e2b93-143">xsd:boolean</span></span>  <br/> |<span data-ttu-id="e2b93-144">可选</span><span class="sxs-lookup"><span data-stu-id="e2b93-144">optional</span></span>  <br/> ||<span data-ttu-id="e2b93-145">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e2b93-145">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="e2b93-146">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="e2b93-146">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="e2b93-147">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="e2b93-147">xsd:boolean</span></span>  <br/> |<span data-ttu-id="e2b93-148">可选</span><span class="sxs-lookup"><span data-stu-id="e2b93-148">optional</span></span>  <br/> ||<span data-ttu-id="e2b93-149">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e2b93-149">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="e2b93-150">名称</span><span class="sxs-lookup"><span data-stu-id="e2b93-150">Name</span></span>  <br/> |<span data-ttu-id="e2b93-151">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e2b93-151">xsd:string</span></span>  <br/> |<span data-ttu-id="e2b93-152">可选</span><span class="sxs-lookup"><span data-stu-id="e2b93-152">optional</span></span>  <br/> ||<span data-ttu-id="e2b93-153">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e2b93-153">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e2b93-154">NameU</span><span class="sxs-lookup"><span data-stu-id="e2b93-154">NameU</span></span>  <br/> |<span data-ttu-id="e2b93-155">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e2b93-155">xsd:string</span></span>  <br/> |<span data-ttu-id="e2b93-156">可选</span><span class="sxs-lookup"><span data-stu-id="e2b93-156">optional</span></span>  <br/> ||<span data-ttu-id="e2b93-157">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e2b93-157">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e2b93-158">ReviewerID</span><span class="sxs-lookup"><span data-stu-id="e2b93-158">ReviewerID</span></span>  <br/> |<span data-ttu-id="e2b93-159">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e2b93-159">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e2b93-160">可选</span><span class="sxs-lookup"><span data-stu-id="e2b93-160">optional</span></span>  <br/> ||<span data-ttu-id="e2b93-161">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e2b93-161">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="e2b93-162">ViewCenterX</span><span class="sxs-lookup"><span data-stu-id="e2b93-162">ViewCenterX</span></span>  <br/> |<span data-ttu-id="e2b93-163">xsd: double</span><span class="sxs-lookup"><span data-stu-id="e2b93-163">xsd:double</span></span>  <br/> |<span data-ttu-id="e2b93-164">可选</span><span class="sxs-lookup"><span data-stu-id="e2b93-164">optional</span></span>  <br/> ||<span data-ttu-id="e2b93-165">xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e2b93-165">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="e2b93-166">ViewCenterY</span><span class="sxs-lookup"><span data-stu-id="e2b93-166">ViewCenterY</span></span>  <br/> |<span data-ttu-id="e2b93-167">xsd: double</span><span class="sxs-lookup"><span data-stu-id="e2b93-167">xsd:double</span></span>  <br/> |<span data-ttu-id="e2b93-168">可选</span><span class="sxs-lookup"><span data-stu-id="e2b93-168">optional</span></span>  <br/> ||<span data-ttu-id="e2b93-169">xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e2b93-169">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="e2b93-170">ViewScale</span><span class="sxs-lookup"><span data-stu-id="e2b93-170">ViewScale</span></span>  <br/> |<span data-ttu-id="e2b93-171">xsd: double</span><span class="sxs-lookup"><span data-stu-id="e2b93-171">xsd:double</span></span>  <br/> |<span data-ttu-id="e2b93-172">可选</span><span class="sxs-lookup"><span data-stu-id="e2b93-172">optional</span></span>  <br/> ||<span data-ttu-id="e2b93-173">xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e2b93-173">Values of the xsd:double type.</span></span>  <br/> |
   

