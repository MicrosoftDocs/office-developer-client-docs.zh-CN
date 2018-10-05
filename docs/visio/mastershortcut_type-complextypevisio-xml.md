---
title: MasterShortcut_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0192c733-09b8-d9ce-1d88-b4d97e2e1a36
ms.openlocfilehash: 23d5de92be151b9ab6819296456746087573e7c0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396482"
---
# <a name="mastershortcuttype-complextype-visio-xml"></a><span data-ttu-id="28109-102">MasterShortcut_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="28109-102">MasterShortcut_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="28109-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="28109-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="28109-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="28109-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="28109-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="28109-105">**Schema file**</span></span> <br/> |<span data-ttu-id="28109-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="28109-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="28109-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="28109-107">**Extension base**</span></span> <br/> |<span data-ttu-id="28109-108">无</span><span class="sxs-lookup"><span data-stu-id="28109-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="28109-109">定义</span><span class="sxs-lookup"><span data-stu-id="28109-109">Definition</span></span>

```XML
          <xs:complexType name="MasterShortcut_Type">
          
          <xs:all>
    <xs:element name="Icon"  type="Icon_Type"
     minOccurs="0"
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
    <xs:attribute name="IconSize"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="PatternFlags"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="Prompt"
  type="xsd:string"
    />
    <xs:attribute name="ShortcutURL"
  type="xsd:string"
    />
    <xs:attribute name="ShortcutHelp"
  type="xsd:string"
    />
    <xs:attribute name="AlignName"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="MasterType"
  type="xsd:unsignedShort"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="28109-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="28109-110">Elements and attributes</span></span>

<span data-ttu-id="28109-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="28109-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="28109-112">子元素</span><span class="sxs-lookup"><span data-stu-id="28109-112">Child elements</span></span>

|<span data-ttu-id="28109-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="28109-113">**Element**</span></span>|<span data-ttu-id="28109-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="28109-114">**Type**</span></span>|<span data-ttu-id="28109-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="28109-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="28109-116">图标</span><span class="sxs-lookup"><span data-stu-id="28109-116">Icon</span></span>](icon-element-mastershortcut_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="28109-117">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="28109-117">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="28109-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="28109-118">Attributes</span></span>

|<span data-ttu-id="28109-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="28109-119">**Attribute**</span></span>|<span data-ttu-id="28109-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="28109-120">**Type**</span></span>|<span data-ttu-id="28109-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="28109-121">**Required**</span></span>|<span data-ttu-id="28109-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="28109-122">**Description**</span></span>|<span data-ttu-id="28109-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="28109-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28109-124">AlignName</span><span class="sxs-lookup"><span data-stu-id="28109-124">AlignName</span></span>  <br/> |<span data-ttu-id="28109-125">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="28109-125">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="28109-126">可选</span><span class="sxs-lookup"><span data-stu-id="28109-126">optional</span></span>  <br/> ||<span data-ttu-id="28109-127">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28109-127">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="28109-128">IconSize</span><span class="sxs-lookup"><span data-stu-id="28109-128">IconSize</span></span>  <br/> |<span data-ttu-id="28109-129">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="28109-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="28109-130">可选</span><span class="sxs-lookup"><span data-stu-id="28109-130">optional</span></span>  <br/> ||<span data-ttu-id="28109-131">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28109-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="28109-132">ID</span><span class="sxs-lookup"><span data-stu-id="28109-132">ID</span></span>  <br/> |<span data-ttu-id="28109-133">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="28109-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="28109-134">必需</span><span class="sxs-lookup"><span data-stu-id="28109-134">required</span></span>  <br/> ||<span data-ttu-id="28109-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28109-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="28109-136">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="28109-136">IsCustomName</span></span>  <br/> |<span data-ttu-id="28109-137">化</span><span class="sxs-lookup"><span data-stu-id="28109-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="28109-138">可选</span><span class="sxs-lookup"><span data-stu-id="28109-138">optional</span></span>  <br/> ||<span data-ttu-id="28109-139">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="28109-139">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="28109-140">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="28109-140">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="28109-141">化</span><span class="sxs-lookup"><span data-stu-id="28109-141">xsd:boolean</span></span>  <br/> |<span data-ttu-id="28109-142">可选</span><span class="sxs-lookup"><span data-stu-id="28109-142">optional</span></span>  <br/> ||<span data-ttu-id="28109-143">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="28109-143">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="28109-144">MasterType</span><span class="sxs-lookup"><span data-stu-id="28109-144">MasterType</span></span>  <br/> |<span data-ttu-id="28109-145">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="28109-145">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="28109-146">可选</span><span class="sxs-lookup"><span data-stu-id="28109-146">optional</span></span>  <br/> ||<span data-ttu-id="28109-147">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28109-147">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="28109-148">名称</span><span class="sxs-lookup"><span data-stu-id="28109-148">Name</span></span>  <br/> |<span data-ttu-id="28109-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="28109-149">xsd:string</span></span>  <br/> |<span data-ttu-id="28109-150">可选</span><span class="sxs-lookup"><span data-stu-id="28109-150">optional</span></span>  <br/> ||<span data-ttu-id="28109-151">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28109-151">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="28109-152">NameU</span><span class="sxs-lookup"><span data-stu-id="28109-152">NameU</span></span>  <br/> |<span data-ttu-id="28109-153">xsd: string</span><span class="sxs-lookup"><span data-stu-id="28109-153">xsd:string</span></span>  <br/> |<span data-ttu-id="28109-154">可选</span><span class="sxs-lookup"><span data-stu-id="28109-154">optional</span></span>  <br/> ||<span data-ttu-id="28109-155">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28109-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="28109-156">PatternFlags</span><span class="sxs-lookup"><span data-stu-id="28109-156">PatternFlags</span></span>  <br/> |<span data-ttu-id="28109-157">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="28109-157">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="28109-158">可选</span><span class="sxs-lookup"><span data-stu-id="28109-158">optional</span></span>  <br/> ||<span data-ttu-id="28109-159">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28109-159">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="28109-160">提示</span><span class="sxs-lookup"><span data-stu-id="28109-160">Prompt</span></span>  <br/> |<span data-ttu-id="28109-161">xsd: string</span><span class="sxs-lookup"><span data-stu-id="28109-161">xsd:string</span></span>  <br/> |<span data-ttu-id="28109-162">可选</span><span class="sxs-lookup"><span data-stu-id="28109-162">optional</span></span>  <br/> ||<span data-ttu-id="28109-163">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28109-163">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="28109-164">ShortcutHelp</span><span class="sxs-lookup"><span data-stu-id="28109-164">ShortcutHelp</span></span>  <br/> |<span data-ttu-id="28109-165">xsd: string</span><span class="sxs-lookup"><span data-stu-id="28109-165">xsd:string</span></span>  <br/> |<span data-ttu-id="28109-166">可选</span><span class="sxs-lookup"><span data-stu-id="28109-166">optional</span></span>  <br/> ||<span data-ttu-id="28109-167">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28109-167">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="28109-168">ShortcutURL</span><span class="sxs-lookup"><span data-stu-id="28109-168">ShortcutURL</span></span>  <br/> |<span data-ttu-id="28109-169">xsd: string</span><span class="sxs-lookup"><span data-stu-id="28109-169">xsd:string</span></span>  <br/> |<span data-ttu-id="28109-170">可选</span><span class="sxs-lookup"><span data-stu-id="28109-170">optional</span></span>  <br/> ||<span data-ttu-id="28109-171">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28109-171">Values of the xsd:string type.</span></span>  <br/> |
   

