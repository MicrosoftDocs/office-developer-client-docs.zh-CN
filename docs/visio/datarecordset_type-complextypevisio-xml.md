---
title: DataRecordSet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 59544910-6bd5-2c89-71b3-5c8ee91a1dea
ms.openlocfilehash: 79fe048c578e8b9d8095d3fe7cd456af8ce08549
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780042"
---
# <a name="datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="228d6-102">DataRecordSet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="228d6-102">DataRecordSet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="228d6-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="228d6-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="228d6-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="228d6-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="228d6-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="228d6-105">**Schema file**</span></span> <br/> |<span data-ttu-id="228d6-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="228d6-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="228d6-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="228d6-107">**Extension base**</span></span> <br/> |<span data-ttu-id="228d6-108">无</span><span class="sxs-lookup"><span data-stu-id="228d6-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="228d6-109">定义</span><span class="sxs-lookup"><span data-stu-id="228d6-109">Definition</span></span>

```XML
          <xs:complexType name="DataRecordSet_Type">
          
          <xs:sequence>
    <xs:element name="Rel"  type="Rel_Type"
     minOccurs="1"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="DataColumns"  type="DataColumns_Type"
     minOccurs="1"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="PrimaryKey"  type="PrimaryKey_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="RowMap"  type="RowMap_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="RefreshConflict"  type="RefreshConflict_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="AutoLinkComparison"  type="AutoLinkComparison_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="ConnectionID"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Command"
  type="xsd:string"
    />
    <xs:attribute name="Options"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="TimeRefreshed"
  type="xsd:dateTime"
    />
    <xs:attribute name="NextRowID"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Name"
  type="xsd:string"
    />
    <xs:attribute name="RowOrder"
  type="xsd:boolean"
    />
    <xs:attribute name="RefreshOverwriteAll"
  type="xsd:boolean"
    />
    <xs:attribute name="RefreshNoReconciliationUI"
  type="xsd:boolean"
    />
    <xs:attribute name="RefreshInterval"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="ReplaceLinks"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Checksum"
  type="xsd:unsignedInt"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="228d6-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="228d6-110">Elements and attributes</span></span>

<span data-ttu-id="228d6-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="228d6-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="228d6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="228d6-112">Child elements</span></span>

|<span data-ttu-id="228d6-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="228d6-113">**Element**</span></span>|<span data-ttu-id="228d6-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="228d6-114">**Type**</span></span>|<span data-ttu-id="228d6-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="228d6-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="228d6-116">AutoLinkComparison</span><span class="sxs-lookup"><span data-stu-id="228d6-116">AutoLinkComparison</span></span>](autolinkcomparison-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="228d6-117">AutoLinkComparison_Type</span><span class="sxs-lookup"><span data-stu-id="228d6-117">AutoLinkComparison_Type</span></span>](autolinkcomparison_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="228d6-118">DataColumns</span><span class="sxs-lookup"><span data-stu-id="228d6-118">DataColumns</span></span>](datacolumns-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="228d6-119">DataColumns_Type</span><span class="sxs-lookup"><span data-stu-id="228d6-119">DataColumns_Type</span></span>](datacolumns_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="228d6-120">PrimaryKey</span><span class="sxs-lookup"><span data-stu-id="228d6-120">PrimaryKey</span></span>](primarykey-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="228d6-121">PrimaryKey_Type</span><span class="sxs-lookup"><span data-stu-id="228d6-121">PrimaryKey_Type</span></span>](primarykey_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="228d6-122">RefreshConflict</span><span class="sxs-lookup"><span data-stu-id="228d6-122">RefreshConflict</span></span>](refreshconflict-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="228d6-123">RefreshConflict_Type</span><span class="sxs-lookup"><span data-stu-id="228d6-123">RefreshConflict_Type</span></span>](refreshconflict_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="228d6-124">Rel</span><span class="sxs-lookup"><span data-stu-id="228d6-124">Rel</span></span>](rel-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="228d6-125">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="228d6-125">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="228d6-126">RowMap</span><span class="sxs-lookup"><span data-stu-id="228d6-126">RowMap</span></span>](rowmap-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="228d6-127">RowMap_Type</span><span class="sxs-lookup"><span data-stu-id="228d6-127">RowMap_Type</span></span>](rowmap_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="228d6-128">属性</span><span class="sxs-lookup"><span data-stu-id="228d6-128">Attributes</span></span>

|<span data-ttu-id="228d6-129">**属性**</span><span class="sxs-lookup"><span data-stu-id="228d6-129">**Attribute**</span></span>|<span data-ttu-id="228d6-130">**类型**</span><span class="sxs-lookup"><span data-stu-id="228d6-130">**Type**</span></span>|<span data-ttu-id="228d6-131">**必需**</span><span class="sxs-lookup"><span data-stu-id="228d6-131">**Required**</span></span>|<span data-ttu-id="228d6-132">**说明**</span><span class="sxs-lookup"><span data-stu-id="228d6-132">**Description**</span></span>|<span data-ttu-id="228d6-133">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="228d6-133">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="228d6-134">校验和</span><span class="sxs-lookup"><span data-stu-id="228d6-134">Checksum</span></span>  <br/> |<span data-ttu-id="228d6-135">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="228d6-135">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="228d6-136">可选</span><span class="sxs-lookup"><span data-stu-id="228d6-136">optional</span></span>  <br/> ||<span data-ttu-id="228d6-137">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="228d6-138">命令</span><span class="sxs-lookup"><span data-stu-id="228d6-138">Command</span></span>  <br/> |<span data-ttu-id="228d6-139">xsd: string</span><span class="sxs-lookup"><span data-stu-id="228d6-139">xsd:string</span></span>  <br/> |<span data-ttu-id="228d6-140">可选</span><span class="sxs-lookup"><span data-stu-id="228d6-140">optional</span></span>  <br/> ||<span data-ttu-id="228d6-141">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="228d6-142">ConnectionID</span><span class="sxs-lookup"><span data-stu-id="228d6-142">ConnectionID</span></span>  <br/> |<span data-ttu-id="228d6-143">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="228d6-143">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="228d6-144">可选</span><span class="sxs-lookup"><span data-stu-id="228d6-144">optional</span></span>  <br/> ||<span data-ttu-id="228d6-145">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="228d6-146">ID</span><span class="sxs-lookup"><span data-stu-id="228d6-146">ID</span></span>  <br/> |<span data-ttu-id="228d6-147">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="228d6-147">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="228d6-148">必需</span><span class="sxs-lookup"><span data-stu-id="228d6-148">required</span></span>  <br/> ||<span data-ttu-id="228d6-149">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-149">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="228d6-150">名称</span><span class="sxs-lookup"><span data-stu-id="228d6-150">Name</span></span>  <br/> |<span data-ttu-id="228d6-151">xsd: string</span><span class="sxs-lookup"><span data-stu-id="228d6-151">xsd:string</span></span>  <br/> |<span data-ttu-id="228d6-152">可选</span><span class="sxs-lookup"><span data-stu-id="228d6-152">optional</span></span>  <br/> ||<span data-ttu-id="228d6-153">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-153">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="228d6-154">NextRowID</span><span class="sxs-lookup"><span data-stu-id="228d6-154">NextRowID</span></span>  <br/> |<span data-ttu-id="228d6-155">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="228d6-155">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="228d6-156">可选</span><span class="sxs-lookup"><span data-stu-id="228d6-156">optional</span></span>  <br/> ||<span data-ttu-id="228d6-157">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-157">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="228d6-158">选项</span><span class="sxs-lookup"><span data-stu-id="228d6-158">Options</span></span>  <br/> |<span data-ttu-id="228d6-159">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="228d6-159">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="228d6-160">可选</span><span class="sxs-lookup"><span data-stu-id="228d6-160">optional</span></span>  <br/> ||<span data-ttu-id="228d6-161">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-161">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="228d6-162">RefreshInterval</span><span class="sxs-lookup"><span data-stu-id="228d6-162">RefreshInterval</span></span>  <br/> |<span data-ttu-id="228d6-163">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="228d6-163">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="228d6-164">可选</span><span class="sxs-lookup"><span data-stu-id="228d6-164">optional</span></span>  <br/> ||<span data-ttu-id="228d6-165">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-165">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="228d6-166">RefreshNoReconciliationUI</span><span class="sxs-lookup"><span data-stu-id="228d6-166">RefreshNoReconciliationUI</span></span>  <br/> |<span data-ttu-id="228d6-167">化</span><span class="sxs-lookup"><span data-stu-id="228d6-167">xsd:boolean</span></span>  <br/> |<span data-ttu-id="228d6-168">可选</span><span class="sxs-lookup"><span data-stu-id="228d6-168">optional</span></span>  <br/> ||<span data-ttu-id="228d6-169">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-169">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="228d6-170">RefreshOverwriteAll</span><span class="sxs-lookup"><span data-stu-id="228d6-170">RefreshOverwriteAll</span></span>  <br/> |<span data-ttu-id="228d6-171">化</span><span class="sxs-lookup"><span data-stu-id="228d6-171">xsd:boolean</span></span>  <br/> |<span data-ttu-id="228d6-172">可选</span><span class="sxs-lookup"><span data-stu-id="228d6-172">optional</span></span>  <br/> ||<span data-ttu-id="228d6-173">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-173">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="228d6-174">ReplaceLinks</span><span class="sxs-lookup"><span data-stu-id="228d6-174">ReplaceLinks</span></span>  <br/> |<span data-ttu-id="228d6-175">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="228d6-175">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="228d6-176">可选</span><span class="sxs-lookup"><span data-stu-id="228d6-176">optional</span></span>  <br/> ||<span data-ttu-id="228d6-177">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-177">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="228d6-178">RowOrder</span><span class="sxs-lookup"><span data-stu-id="228d6-178">RowOrder</span></span>  <br/> |<span data-ttu-id="228d6-179">化</span><span class="sxs-lookup"><span data-stu-id="228d6-179">xsd:boolean</span></span>  <br/> |<span data-ttu-id="228d6-180">可选</span><span class="sxs-lookup"><span data-stu-id="228d6-180">optional</span></span>  <br/> ||<span data-ttu-id="228d6-181">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-181">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="228d6-182">TimeRefreshed</span><span class="sxs-lookup"><span data-stu-id="228d6-182">TimeRefreshed</span></span>  <br/> |<span data-ttu-id="228d6-183">化</span><span class="sxs-lookup"><span data-stu-id="228d6-183">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="228d6-184">可选</span><span class="sxs-lookup"><span data-stu-id="228d6-184">optional</span></span>  <br/> ||<span data-ttu-id="228d6-185">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="228d6-185">Values of the xsd:dateTime type.</span></span>  <br/> |
   

