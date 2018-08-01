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
# <a name="datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="32205-102">DataRecordSet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="32205-102">DataRecordSet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="32205-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="32205-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="32205-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="32205-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="32205-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="32205-105">**Schema file**</span></span> <br/> |<span data-ttu-id="32205-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="32205-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="32205-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="32205-107">**Extension base**</span></span> <br/> |<span data-ttu-id="32205-108">无</span><span class="sxs-lookup"><span data-stu-id="32205-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="32205-109">定义</span><span class="sxs-lookup"><span data-stu-id="32205-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="32205-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="32205-110">Elements and attributes</span></span>

<span data-ttu-id="32205-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="32205-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="32205-112">子元素</span><span class="sxs-lookup"><span data-stu-id="32205-112">Child elements</span></span>

|<span data-ttu-id="32205-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="32205-113">**Element**</span></span>|<span data-ttu-id="32205-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="32205-114">**Type**</span></span>|<span data-ttu-id="32205-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="32205-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="32205-116">AutoLinkComparison</span><span class="sxs-lookup"><span data-stu-id="32205-116">AutoLinkComparison</span></span>](autolinkcomparison-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="32205-117">AutoLinkComparison_Type</span><span class="sxs-lookup"><span data-stu-id="32205-117">AutoLinkComparison_Type</span></span>](autolinkcomparison_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="32205-118">DataColumns</span><span class="sxs-lookup"><span data-stu-id="32205-118">DataColumns</span></span>](datacolumns-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="32205-119">DataColumns_Type</span><span class="sxs-lookup"><span data-stu-id="32205-119">DataColumns_Type</span></span>](datacolumns_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="32205-120">PrimaryKey</span><span class="sxs-lookup"><span data-stu-id="32205-120">PrimaryKey</span></span>](primarykey-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="32205-121">PrimaryKey_Type</span><span class="sxs-lookup"><span data-stu-id="32205-121">PrimaryKey_Type</span></span>](primarykey_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="32205-122">RefreshConflict</span><span class="sxs-lookup"><span data-stu-id="32205-122">RefreshConflict</span></span>](refreshconflict-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="32205-123">RefreshConflict_Type</span><span class="sxs-lookup"><span data-stu-id="32205-123">RefreshConflict_Type</span></span>](refreshconflict_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="32205-124">Rel</span><span class="sxs-lookup"><span data-stu-id="32205-124">Rel</span></span>](rel-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="32205-125">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="32205-125">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="32205-126">RowMap</span><span class="sxs-lookup"><span data-stu-id="32205-126">RowMap</span></span>](rowmap-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="32205-127">RowMap_Type</span><span class="sxs-lookup"><span data-stu-id="32205-127">RowMap_Type</span></span>](rowmap_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="32205-128">Attributes</span><span class="sxs-lookup"><span data-stu-id="32205-128">Attributes</span></span>

|<span data-ttu-id="32205-129">**属性**</span><span class="sxs-lookup"><span data-stu-id="32205-129">**Attribute**</span></span>|<span data-ttu-id="32205-130">**类型**</span><span class="sxs-lookup"><span data-stu-id="32205-130">**Type**</span></span>|<span data-ttu-id="32205-131">**必需**</span><span class="sxs-lookup"><span data-stu-id="32205-131">**Required**</span></span>|<span data-ttu-id="32205-132">**说明**</span><span class="sxs-lookup"><span data-stu-id="32205-132">**Description**</span></span>|<span data-ttu-id="32205-133">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="32205-133">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="32205-134">校验和</span><span class="sxs-lookup"><span data-stu-id="32205-134">Checksum</span></span>  <br/> |<span data-ttu-id="32205-135">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="32205-135">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="32205-136">可选</span><span class="sxs-lookup"><span data-stu-id="32205-136">optional</span></span>  <br/> ||<span data-ttu-id="32205-137">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="32205-138">命令</span><span class="sxs-lookup"><span data-stu-id="32205-138">Command</span></span>  <br/> |<span data-ttu-id="32205-139">xsd: string</span><span class="sxs-lookup"><span data-stu-id="32205-139">xsd:string</span></span>  <br/> |<span data-ttu-id="32205-140">可选</span><span class="sxs-lookup"><span data-stu-id="32205-140">optional</span></span>  <br/> ||<span data-ttu-id="32205-141">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="32205-142">ConnectionID</span><span class="sxs-lookup"><span data-stu-id="32205-142">ConnectionID</span></span>  <br/> |<span data-ttu-id="32205-143">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="32205-143">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="32205-144">可选</span><span class="sxs-lookup"><span data-stu-id="32205-144">optional</span></span>  <br/> ||<span data-ttu-id="32205-145">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="32205-146">ID</span><span class="sxs-lookup"><span data-stu-id="32205-146">ID</span></span>  <br/> |<span data-ttu-id="32205-147">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="32205-147">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="32205-148">必需</span><span class="sxs-lookup"><span data-stu-id="32205-148">required</span></span>  <br/> ||<span data-ttu-id="32205-149">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-149">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="32205-150">名称</span><span class="sxs-lookup"><span data-stu-id="32205-150">Name</span></span>  <br/> |<span data-ttu-id="32205-151">xsd: string</span><span class="sxs-lookup"><span data-stu-id="32205-151">xsd:string</span></span>  <br/> |<span data-ttu-id="32205-152">可选</span><span class="sxs-lookup"><span data-stu-id="32205-152">optional</span></span>  <br/> ||<span data-ttu-id="32205-153">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-153">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="32205-154">NextRowID</span><span class="sxs-lookup"><span data-stu-id="32205-154">NextRowID</span></span>  <br/> |<span data-ttu-id="32205-155">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="32205-155">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="32205-156">可选</span><span class="sxs-lookup"><span data-stu-id="32205-156">optional</span></span>  <br/> ||<span data-ttu-id="32205-157">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-157">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="32205-158">选项</span><span class="sxs-lookup"><span data-stu-id="32205-158">Options</span></span>  <br/> |<span data-ttu-id="32205-159">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="32205-159">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="32205-160">可选</span><span class="sxs-lookup"><span data-stu-id="32205-160">optional</span></span>  <br/> ||<span data-ttu-id="32205-161">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-161">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="32205-162">RefreshInterval</span><span class="sxs-lookup"><span data-stu-id="32205-162">RefreshInterval</span></span>  <br/> |<span data-ttu-id="32205-163">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="32205-163">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="32205-164">可选</span><span class="sxs-lookup"><span data-stu-id="32205-164">optional</span></span>  <br/> ||<span data-ttu-id="32205-165">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-165">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="32205-166">RefreshNoReconciliationUI</span><span class="sxs-lookup"><span data-stu-id="32205-166">RefreshNoReconciliationUI</span></span>  <br/> |<span data-ttu-id="32205-167">化</span><span class="sxs-lookup"><span data-stu-id="32205-167">xsd:boolean</span></span>  <br/> |<span data-ttu-id="32205-168">可选</span><span class="sxs-lookup"><span data-stu-id="32205-168">optional</span></span>  <br/> ||<span data-ttu-id="32205-169">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-169">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="32205-170">RefreshOverwriteAll</span><span class="sxs-lookup"><span data-stu-id="32205-170">RefreshOverwriteAll</span></span>  <br/> |<span data-ttu-id="32205-171">化</span><span class="sxs-lookup"><span data-stu-id="32205-171">xsd:boolean</span></span>  <br/> |<span data-ttu-id="32205-172">可选</span><span class="sxs-lookup"><span data-stu-id="32205-172">optional</span></span>  <br/> ||<span data-ttu-id="32205-173">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-173">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="32205-174">ReplaceLinks</span><span class="sxs-lookup"><span data-stu-id="32205-174">ReplaceLinks</span></span>  <br/> |<span data-ttu-id="32205-175">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="32205-175">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="32205-176">可选</span><span class="sxs-lookup"><span data-stu-id="32205-176">optional</span></span>  <br/> ||<span data-ttu-id="32205-177">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-177">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="32205-178">RowOrder</span><span class="sxs-lookup"><span data-stu-id="32205-178">RowOrder</span></span>  <br/> |<span data-ttu-id="32205-179">化</span><span class="sxs-lookup"><span data-stu-id="32205-179">xsd:boolean</span></span>  <br/> |<span data-ttu-id="32205-180">可选</span><span class="sxs-lookup"><span data-stu-id="32205-180">optional</span></span>  <br/> ||<span data-ttu-id="32205-181">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-181">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="32205-182">TimeRefreshed</span><span class="sxs-lookup"><span data-stu-id="32205-182">TimeRefreshed</span></span>  <br/> |<span data-ttu-id="32205-183">化</span><span class="sxs-lookup"><span data-stu-id="32205-183">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="32205-184">可选</span><span class="sxs-lookup"><span data-stu-id="32205-184">optional</span></span>  <br/> ||<span data-ttu-id="32205-185">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="32205-185">Values of the xsd:dateTime type.</span></span>  <br/> |
   

