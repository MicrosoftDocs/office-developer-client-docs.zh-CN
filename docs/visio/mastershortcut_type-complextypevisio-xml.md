---
title: MasterShortcut_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0192c733-09b8-d9ce-1d88-b4d97e2e1a36
ms.openlocfilehash: df1e10ff11470cd87fc16efbaba6ad968df6d1b0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780705"
---
# <a name="mastershortcuttype-complextype-visio-xml"></a><span data-ttu-id="4af63-102">MasterShortcut_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="4af63-102">MasterShortcut_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="4af63-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="4af63-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4af63-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4af63-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="4af63-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4af63-105">**Schema file**</span></span> <br/> |<span data-ttu-id="4af63-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="4af63-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="4af63-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="4af63-107">**Extension base**</span></span> <br/> |<span data-ttu-id="4af63-108">无</span><span class="sxs-lookup"><span data-stu-id="4af63-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4af63-109">定义</span><span class="sxs-lookup"><span data-stu-id="4af63-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="4af63-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4af63-110">Elements and attributes</span></span>

<span data-ttu-id="4af63-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4af63-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="4af63-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4af63-112">Child elements</span></span>

|<span data-ttu-id="4af63-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="4af63-113">**Element**</span></span>|<span data-ttu-id="4af63-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="4af63-114">**Type**</span></span>|<span data-ttu-id="4af63-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="4af63-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4af63-116">图标</span><span class="sxs-lookup"><span data-stu-id="4af63-116">Icon</span></span>](icon-element-mastershortcut_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4af63-117">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="4af63-117">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="4af63-118">属性</span><span class="sxs-lookup"><span data-stu-id="4af63-118">Attributes</span></span>

|<span data-ttu-id="4af63-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="4af63-119">**Attribute**</span></span>|<span data-ttu-id="4af63-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="4af63-120">**Type**</span></span>|<span data-ttu-id="4af63-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="4af63-121">**Required**</span></span>|<span data-ttu-id="4af63-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="4af63-122">**Description**</span></span>|<span data-ttu-id="4af63-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4af63-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4af63-124">AlignName</span><span class="sxs-lookup"><span data-stu-id="4af63-124">AlignName</span></span>  <br/> |<span data-ttu-id="4af63-125">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="4af63-125">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="4af63-126">可选</span><span class="sxs-lookup"><span data-stu-id="4af63-126">optional</span></span>  <br/> ||<span data-ttu-id="4af63-127">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4af63-127">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="4af63-128">IconSize</span><span class="sxs-lookup"><span data-stu-id="4af63-128">IconSize</span></span>  <br/> |<span data-ttu-id="4af63-129">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="4af63-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="4af63-130">可选</span><span class="sxs-lookup"><span data-stu-id="4af63-130">optional</span></span>  <br/> ||<span data-ttu-id="4af63-131">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4af63-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="4af63-132">ID</span><span class="sxs-lookup"><span data-stu-id="4af63-132">ID</span></span>  <br/> |<span data-ttu-id="4af63-133">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4af63-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4af63-134">必需</span><span class="sxs-lookup"><span data-stu-id="4af63-134">required</span></span>  <br/> ||<span data-ttu-id="4af63-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4af63-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4af63-136">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="4af63-136">IsCustomName</span></span>  <br/> |<span data-ttu-id="4af63-137">化</span><span class="sxs-lookup"><span data-stu-id="4af63-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="4af63-138">可选</span><span class="sxs-lookup"><span data-stu-id="4af63-138">optional</span></span>  <br/> ||<span data-ttu-id="4af63-139">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="4af63-139">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="4af63-140">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="4af63-140">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="4af63-141">化</span><span class="sxs-lookup"><span data-stu-id="4af63-141">xsd:boolean</span></span>  <br/> |<span data-ttu-id="4af63-142">可选</span><span class="sxs-lookup"><span data-stu-id="4af63-142">optional</span></span>  <br/> ||<span data-ttu-id="4af63-143">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="4af63-143">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="4af63-144">MasterType</span><span class="sxs-lookup"><span data-stu-id="4af63-144">MasterType</span></span>  <br/> |<span data-ttu-id="4af63-145">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="4af63-145">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="4af63-146">可选</span><span class="sxs-lookup"><span data-stu-id="4af63-146">optional</span></span>  <br/> ||<span data-ttu-id="4af63-147">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4af63-147">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="4af63-148">名称</span><span class="sxs-lookup"><span data-stu-id="4af63-148">Name</span></span>  <br/> |<span data-ttu-id="4af63-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4af63-149">xsd:string</span></span>  <br/> |<span data-ttu-id="4af63-150">可选</span><span class="sxs-lookup"><span data-stu-id="4af63-150">optional</span></span>  <br/> ||<span data-ttu-id="4af63-151">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4af63-151">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="4af63-152">NameU</span><span class="sxs-lookup"><span data-stu-id="4af63-152">NameU</span></span>  <br/> |<span data-ttu-id="4af63-153">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4af63-153">xsd:string</span></span>  <br/> |<span data-ttu-id="4af63-154">可选</span><span class="sxs-lookup"><span data-stu-id="4af63-154">optional</span></span>  <br/> ||<span data-ttu-id="4af63-155">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4af63-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="4af63-156">PatternFlags</span><span class="sxs-lookup"><span data-stu-id="4af63-156">PatternFlags</span></span>  <br/> |<span data-ttu-id="4af63-157">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="4af63-157">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="4af63-158">可选</span><span class="sxs-lookup"><span data-stu-id="4af63-158">optional</span></span>  <br/> ||<span data-ttu-id="4af63-159">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4af63-159">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="4af63-160">提示</span><span class="sxs-lookup"><span data-stu-id="4af63-160">Prompt</span></span>  <br/> |<span data-ttu-id="4af63-161">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4af63-161">xsd:string</span></span>  <br/> |<span data-ttu-id="4af63-162">可选</span><span class="sxs-lookup"><span data-stu-id="4af63-162">optional</span></span>  <br/> ||<span data-ttu-id="4af63-163">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4af63-163">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="4af63-164">ShortcutHelp</span><span class="sxs-lookup"><span data-stu-id="4af63-164">ShortcutHelp</span></span>  <br/> |<span data-ttu-id="4af63-165">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4af63-165">xsd:string</span></span>  <br/> |<span data-ttu-id="4af63-166">可选</span><span class="sxs-lookup"><span data-stu-id="4af63-166">optional</span></span>  <br/> ||<span data-ttu-id="4af63-167">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4af63-167">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="4af63-168">ShortcutURL</span><span class="sxs-lookup"><span data-stu-id="4af63-168">ShortcutURL</span></span>  <br/> |<span data-ttu-id="4af63-169">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4af63-169">xsd:string</span></span>  <br/> |<span data-ttu-id="4af63-170">可选</span><span class="sxs-lookup"><span data-stu-id="4af63-170">optional</span></span>  <br/> ||<span data-ttu-id="4af63-171">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4af63-171">Values of the xsd:string type.</span></span>  <br/> |
   

