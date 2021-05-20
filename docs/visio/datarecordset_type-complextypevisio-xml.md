---
title: 'DataRecordSet_Type XML (Visio complexType) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 59544910-6bd5-2c89-71b3-5c8ee91a1dea
ms.openlocfilehash: 132261ae823d1749676b7bdc28cdd1cb94f6ef5b
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539142"
---
# <a name="datarecordset_type-complextype-visio-xml"></a><span data-ttu-id="d848c-102">DataRecordSet_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="d848c-102">DataRecordSet_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="d848c-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="d848c-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d848c-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d848c-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="d848c-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d848c-105">**Schema file**</span></span> <br/> |<span data-ttu-id="d848c-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="d848c-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="d848c-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="d848c-107">**Extension base**</span></span> <br/> |<span data-ttu-id="d848c-108">无</span><span class="sxs-lookup"><span data-stu-id="d848c-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d848c-109">定义</span><span class="sxs-lookup"><span data-stu-id="d848c-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="d848c-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d848c-110">Elements and attributes</span></span>

<span data-ttu-id="d848c-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d848c-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="d848c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d848c-112">Child elements</span></span>

|<span data-ttu-id="d848c-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="d848c-113">**Element**</span></span>|<span data-ttu-id="d848c-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="d848c-114">**Type**</span></span>|<span data-ttu-id="d848c-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="d848c-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d848c-116">AutoLinkComparison</span><span class="sxs-lookup"><span data-stu-id="d848c-116">AutoLinkComparison</span></span>](autolinkcomparison-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d848c-117">AutoLinkComparison_Type</span><span class="sxs-lookup"><span data-stu-id="d848c-117">AutoLinkComparison_Type</span></span>](autolinkcomparison_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d848c-118">DataColumns</span><span class="sxs-lookup"><span data-stu-id="d848c-118">DataColumns</span></span>](datacolumns-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d848c-119">DataColumns_Type</span><span class="sxs-lookup"><span data-stu-id="d848c-119">DataColumns_Type</span></span>](datacolumns_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d848c-120">PrimaryKey</span><span class="sxs-lookup"><span data-stu-id="d848c-120">PrimaryKey</span></span>](primarykey-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d848c-121">PrimaryKey_Type</span><span class="sxs-lookup"><span data-stu-id="d848c-121">PrimaryKey_Type</span></span>](primarykey_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d848c-122">RefreshConflict</span><span class="sxs-lookup"><span data-stu-id="d848c-122">RefreshConflict</span></span>](refreshconflict-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d848c-123">RefreshConflict_Type</span><span class="sxs-lookup"><span data-stu-id="d848c-123">RefreshConflict_Type</span></span>](refreshconflict_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d848c-124">Rel</span><span class="sxs-lookup"><span data-stu-id="d848c-124">Rel</span></span>](rel-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d848c-125">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="d848c-125">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d848c-126">RowMap</span><span class="sxs-lookup"><span data-stu-id="d848c-126">RowMap</span></span>](rowmap-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d848c-127">RowMap_Type</span><span class="sxs-lookup"><span data-stu-id="d848c-127">RowMap_Type</span></span>](rowmap_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="d848c-128">属性</span><span class="sxs-lookup"><span data-stu-id="d848c-128">Attributes</span></span>

|<span data-ttu-id="d848c-129">**属性**</span><span class="sxs-lookup"><span data-stu-id="d848c-129">**Attribute**</span></span>|<span data-ttu-id="d848c-130">**类型**</span><span class="sxs-lookup"><span data-stu-id="d848c-130">**Type**</span></span>|<span data-ttu-id="d848c-131">**必需**</span><span class="sxs-lookup"><span data-stu-id="d848c-131">**Required**</span></span>|<span data-ttu-id="d848c-132">**描述**</span><span class="sxs-lookup"><span data-stu-id="d848c-132">**Description**</span></span>|<span data-ttu-id="d848c-133">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d848c-133">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d848c-134">校验和</span><span class="sxs-lookup"><span data-stu-id="d848c-134">Checksum</span></span>  <br/> |<span data-ttu-id="d848c-135">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d848c-135">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d848c-136">可选</span><span class="sxs-lookup"><span data-stu-id="d848c-136">optional</span></span>  <br/> ||<span data-ttu-id="d848c-137">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d848c-138">Command</span><span class="sxs-lookup"><span data-stu-id="d848c-138">Command</span></span>  <br/> |<span data-ttu-id="d848c-139">xsd：string</span><span class="sxs-lookup"><span data-stu-id="d848c-139">xsd:string</span></span>  <br/> |<span data-ttu-id="d848c-140">可选</span><span class="sxs-lookup"><span data-stu-id="d848c-140">optional</span></span>  <br/> ||<span data-ttu-id="d848c-141">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d848c-142">ConnectionID</span><span class="sxs-lookup"><span data-stu-id="d848c-142">ConnectionID</span></span>  <br/> |<span data-ttu-id="d848c-143">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d848c-143">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d848c-144">可选</span><span class="sxs-lookup"><span data-stu-id="d848c-144">optional</span></span>  <br/> ||<span data-ttu-id="d848c-145">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-145">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d848c-146">ID</span><span class="sxs-lookup"><span data-stu-id="d848c-146">ID</span></span>  <br/> |<span data-ttu-id="d848c-147">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d848c-147">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d848c-148">必需</span><span class="sxs-lookup"><span data-stu-id="d848c-148">required</span></span>  <br/> ||<span data-ttu-id="d848c-149">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-149">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d848c-150">名称</span><span class="sxs-lookup"><span data-stu-id="d848c-150">Name</span></span>  <br/> |<span data-ttu-id="d848c-151">xsd：string</span><span class="sxs-lookup"><span data-stu-id="d848c-151">xsd:string</span></span>  <br/> |<span data-ttu-id="d848c-152">可选</span><span class="sxs-lookup"><span data-stu-id="d848c-152">optional</span></span>  <br/> ||<span data-ttu-id="d848c-153">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-153">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d848c-154">NextRowID</span><span class="sxs-lookup"><span data-stu-id="d848c-154">NextRowID</span></span>  <br/> |<span data-ttu-id="d848c-155">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d848c-155">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d848c-156">可选</span><span class="sxs-lookup"><span data-stu-id="d848c-156">optional</span></span>  <br/> ||<span data-ttu-id="d848c-157">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-157">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d848c-158">选项</span><span class="sxs-lookup"><span data-stu-id="d848c-158">Options</span></span>  <br/> |<span data-ttu-id="d848c-159">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d848c-159">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d848c-160">可选</span><span class="sxs-lookup"><span data-stu-id="d848c-160">optional</span></span>  <br/> ||<span data-ttu-id="d848c-161">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-161">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d848c-162">RefreshInterval</span><span class="sxs-lookup"><span data-stu-id="d848c-162">RefreshInterval</span></span>  <br/> |<span data-ttu-id="d848c-163">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d848c-163">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d848c-164">可选</span><span class="sxs-lookup"><span data-stu-id="d848c-164">optional</span></span>  <br/> ||<span data-ttu-id="d848c-165">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-165">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d848c-166">RefreshNoReconciliationUI</span><span class="sxs-lookup"><span data-stu-id="d848c-166">RefreshNoReconciliationUI</span></span>  <br/> |<span data-ttu-id="d848c-167">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="d848c-167">xsd:boolean</span></span>  <br/> |<span data-ttu-id="d848c-168">可选</span><span class="sxs-lookup"><span data-stu-id="d848c-168">optional</span></span>  <br/> ||<span data-ttu-id="d848c-169">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-169">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="d848c-170">RefreshOverwriteAll</span><span class="sxs-lookup"><span data-stu-id="d848c-170">RefreshOverwriteAll</span></span>  <br/> |<span data-ttu-id="d848c-171">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="d848c-171">xsd:boolean</span></span>  <br/> |<span data-ttu-id="d848c-172">可选</span><span class="sxs-lookup"><span data-stu-id="d848c-172">optional</span></span>  <br/> ||<span data-ttu-id="d848c-173">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-173">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="d848c-174">ReplaceLinks</span><span class="sxs-lookup"><span data-stu-id="d848c-174">ReplaceLinks</span></span>  <br/> |<span data-ttu-id="d848c-175">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d848c-175">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d848c-176">可选</span><span class="sxs-lookup"><span data-stu-id="d848c-176">optional</span></span>  <br/> ||<span data-ttu-id="d848c-177">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-177">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d848c-178">RowOrder</span><span class="sxs-lookup"><span data-stu-id="d848c-178">RowOrder</span></span>  <br/> |<span data-ttu-id="d848c-179">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="d848c-179">xsd:boolean</span></span>  <br/> |<span data-ttu-id="d848c-180">可选</span><span class="sxs-lookup"><span data-stu-id="d848c-180">optional</span></span>  <br/> ||<span data-ttu-id="d848c-181">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-181">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="d848c-182">TimeRefreshed</span><span class="sxs-lookup"><span data-stu-id="d848c-182">TimeRefreshed</span></span>  <br/> |<span data-ttu-id="d848c-183">xsd：dateTime</span><span class="sxs-lookup"><span data-stu-id="d848c-183">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="d848c-184">可选</span><span class="sxs-lookup"><span data-stu-id="d848c-184">optional</span></span>  <br/> ||<span data-ttu-id="d848c-185">xsd：dateTime 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d848c-185">Values of the xsd:dateTime type.</span></span>  <br/> |
   

