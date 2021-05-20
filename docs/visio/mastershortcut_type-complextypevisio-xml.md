---
title: 'MasterShortcut_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0192c733-09b8-d9ce-1d88-b4d97e2e1a36
ms.openlocfilehash: ed8dd8ef985c814e41017526144bd7ec8cb63424
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538058"
---
# <a name="mastershortcut_type-complextype-visio-xml"></a><span data-ttu-id="30136-102">MasterShortcut_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="30136-102">MasterShortcut_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="30136-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="30136-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="30136-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="30136-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="30136-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="30136-105">**Schema file**</span></span> <br/> |<span data-ttu-id="30136-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="30136-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="30136-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="30136-107">**Extension base**</span></span> <br/> |<span data-ttu-id="30136-108">无</span><span class="sxs-lookup"><span data-stu-id="30136-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="30136-109">定义</span><span class="sxs-lookup"><span data-stu-id="30136-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="30136-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="30136-110">Elements and attributes</span></span>

<span data-ttu-id="30136-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="30136-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="30136-112">子元素</span><span class="sxs-lookup"><span data-stu-id="30136-112">Child elements</span></span>

|<span data-ttu-id="30136-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="30136-113">**Element**</span></span>|<span data-ttu-id="30136-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="30136-114">**Type**</span></span>|<span data-ttu-id="30136-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="30136-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="30136-116">Icon</span><span class="sxs-lookup"><span data-stu-id="30136-116">Icon</span></span>](icon-element-mastershortcut_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="30136-117">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="30136-117">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="30136-118">属性</span><span class="sxs-lookup"><span data-stu-id="30136-118">Attributes</span></span>

|<span data-ttu-id="30136-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="30136-119">**Attribute**</span></span>|<span data-ttu-id="30136-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="30136-120">**Type**</span></span>|<span data-ttu-id="30136-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="30136-121">**Required**</span></span>|<span data-ttu-id="30136-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="30136-122">**Description**</span></span>|<span data-ttu-id="30136-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="30136-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="30136-124">AlignName</span><span class="sxs-lookup"><span data-stu-id="30136-124">AlignName</span></span>  <br/> |<span data-ttu-id="30136-125">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="30136-125">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="30136-126">可选</span><span class="sxs-lookup"><span data-stu-id="30136-126">optional</span></span>  <br/> ||<span data-ttu-id="30136-127">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30136-127">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="30136-128">IconSize</span><span class="sxs-lookup"><span data-stu-id="30136-128">IconSize</span></span>  <br/> |<span data-ttu-id="30136-129">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="30136-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="30136-130">可选</span><span class="sxs-lookup"><span data-stu-id="30136-130">optional</span></span>  <br/> ||<span data-ttu-id="30136-131">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30136-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="30136-132">ID</span><span class="sxs-lookup"><span data-stu-id="30136-132">ID</span></span>  <br/> |<span data-ttu-id="30136-133">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="30136-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="30136-134">必需</span><span class="sxs-lookup"><span data-stu-id="30136-134">required</span></span>  <br/> ||<span data-ttu-id="30136-135">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30136-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="30136-136">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="30136-136">IsCustomName</span></span>  <br/> |<span data-ttu-id="30136-137">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="30136-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="30136-138">可选</span><span class="sxs-lookup"><span data-stu-id="30136-138">optional</span></span>  <br/> ||<span data-ttu-id="30136-139">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30136-139">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="30136-140">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="30136-140">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="30136-141">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="30136-141">xsd:boolean</span></span>  <br/> |<span data-ttu-id="30136-142">可选</span><span class="sxs-lookup"><span data-stu-id="30136-142">optional</span></span>  <br/> ||<span data-ttu-id="30136-143">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30136-143">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="30136-144">MasterType</span><span class="sxs-lookup"><span data-stu-id="30136-144">MasterType</span></span>  <br/> |<span data-ttu-id="30136-145">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="30136-145">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="30136-146">可选</span><span class="sxs-lookup"><span data-stu-id="30136-146">optional</span></span>  <br/> ||<span data-ttu-id="30136-147">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30136-147">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="30136-148">名称</span><span class="sxs-lookup"><span data-stu-id="30136-148">Name</span></span>  <br/> |<span data-ttu-id="30136-149">xsd：string</span><span class="sxs-lookup"><span data-stu-id="30136-149">xsd:string</span></span>  <br/> |<span data-ttu-id="30136-150">可选</span><span class="sxs-lookup"><span data-stu-id="30136-150">optional</span></span>  <br/> ||<span data-ttu-id="30136-151">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30136-151">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="30136-152">NameU</span><span class="sxs-lookup"><span data-stu-id="30136-152">NameU</span></span>  <br/> |<span data-ttu-id="30136-153">xsd：string</span><span class="sxs-lookup"><span data-stu-id="30136-153">xsd:string</span></span>  <br/> |<span data-ttu-id="30136-154">可选</span><span class="sxs-lookup"><span data-stu-id="30136-154">optional</span></span>  <br/> ||<span data-ttu-id="30136-155">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30136-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="30136-156">PatternFlags</span><span class="sxs-lookup"><span data-stu-id="30136-156">PatternFlags</span></span>  <br/> |<span data-ttu-id="30136-157">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="30136-157">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="30136-158">可选</span><span class="sxs-lookup"><span data-stu-id="30136-158">optional</span></span>  <br/> ||<span data-ttu-id="30136-159">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30136-159">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="30136-160">Prompt</span><span class="sxs-lookup"><span data-stu-id="30136-160">Prompt</span></span>  <br/> |<span data-ttu-id="30136-161">xsd：string</span><span class="sxs-lookup"><span data-stu-id="30136-161">xsd:string</span></span>  <br/> |<span data-ttu-id="30136-162">可选</span><span class="sxs-lookup"><span data-stu-id="30136-162">optional</span></span>  <br/> ||<span data-ttu-id="30136-163">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30136-163">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="30136-164">ShortcutHelp</span><span class="sxs-lookup"><span data-stu-id="30136-164">ShortcutHelp</span></span>  <br/> |<span data-ttu-id="30136-165">xsd：string</span><span class="sxs-lookup"><span data-stu-id="30136-165">xsd:string</span></span>  <br/> |<span data-ttu-id="30136-166">可选</span><span class="sxs-lookup"><span data-stu-id="30136-166">optional</span></span>  <br/> ||<span data-ttu-id="30136-167">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30136-167">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="30136-168">ShortcutURL</span><span class="sxs-lookup"><span data-stu-id="30136-168">ShortcutURL</span></span>  <br/> |<span data-ttu-id="30136-169">xsd：string</span><span class="sxs-lookup"><span data-stu-id="30136-169">xsd:string</span></span>  <br/> |<span data-ttu-id="30136-170">可选</span><span class="sxs-lookup"><span data-stu-id="30136-170">optional</span></span>  <br/> ||<span data-ttu-id="30136-171">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="30136-171">Values of the xsd:string type.</span></span>  <br/> |
   

