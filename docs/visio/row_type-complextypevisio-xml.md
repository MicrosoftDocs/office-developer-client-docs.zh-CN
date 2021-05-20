---
title: 'Row_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5e5c420e-f384-7b62-c862-35aea16e6d55
ms.openlocfilehash: d728363e6a3e7cd7fca2b95d91469f0d50ae1c39
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538156"
---
# <a name="row_type-complextype-visio-xml"></a><span data-ttu-id="b06e3-102">Row_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="b06e3-102">Row_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="b06e3-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="b06e3-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b06e3-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b06e3-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="b06e3-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b06e3-105">**Schema file**</span></span> <br/> |<span data-ttu-id="b06e3-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="b06e3-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="b06e3-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="b06e3-107">**Extension base**</span></span> <br/> |<span data-ttu-id="b06e3-108">无</span><span class="sxs-lookup"><span data-stu-id="b06e3-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b06e3-109">定义</span><span class="sxs-lookup"><span data-stu-id="b06e3-109">Definition</span></span>

```XML
          <xs:complexType name="Row_Type">
          
          <xs:sequence>
    <xs:element name="Cell"  type="Cell_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="Trigger"  type="Trigger_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="N"
  type="xsd:string"
    />
    <xs:attribute name="LocalName"
  type="xsd:string"
    />
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="T"
  type="xsd:string"
    />
    <xs:attribute name="Del"
  type="xsd:boolean"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b06e3-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b06e3-110">Elements and attributes</span></span>

<span data-ttu-id="b06e3-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="b06e3-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="b06e3-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b06e3-112">Child elements</span></span>

|<span data-ttu-id="b06e3-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="b06e3-113">**Element**</span></span>|<span data-ttu-id="b06e3-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="b06e3-114">**Type**</span></span>|<span data-ttu-id="b06e3-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="b06e3-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b06e3-116">Cell</span><span class="sxs-lookup"><span data-stu-id="b06e3-116">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="b06e3-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="b06e3-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b06e3-118">Trigger</span><span class="sxs-lookup"><span data-stu-id="b06e3-118">Trigger</span></span>](trigger-elementvisio-xml.md) <br/> |[<span data-ttu-id="b06e3-119">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="b06e3-119">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="b06e3-120">属性</span><span class="sxs-lookup"><span data-stu-id="b06e3-120">Attributes</span></span>

|<span data-ttu-id="b06e3-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="b06e3-121">**Attribute**</span></span>|<span data-ttu-id="b06e3-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="b06e3-122">**Type**</span></span>|<span data-ttu-id="b06e3-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="b06e3-123">**Required**</span></span>|<span data-ttu-id="b06e3-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="b06e3-124">**Description**</span></span>|<span data-ttu-id="b06e3-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b06e3-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b06e3-126">Del</span><span class="sxs-lookup"><span data-stu-id="b06e3-126">Del</span></span>  <br/> |<span data-ttu-id="b06e3-127">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="b06e3-127">xsd:boolean</span></span>  <br/> |<span data-ttu-id="b06e3-128">可选</span><span class="sxs-lookup"><span data-stu-id="b06e3-128">optional</span></span>  <br/> ||<span data-ttu-id="b06e3-129">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b06e3-129">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="b06e3-130">IX</span><span class="sxs-lookup"><span data-stu-id="b06e3-130">IX</span></span>  <br/> |<span data-ttu-id="b06e3-131">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b06e3-131">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b06e3-132">可选</span><span class="sxs-lookup"><span data-stu-id="b06e3-132">optional</span></span>  <br/> ||<span data-ttu-id="b06e3-133">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b06e3-133">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b06e3-134">LocalName</span><span class="sxs-lookup"><span data-stu-id="b06e3-134">LocalName</span></span>  <br/> |<span data-ttu-id="b06e3-135">xsd：string</span><span class="sxs-lookup"><span data-stu-id="b06e3-135">xsd:string</span></span>  <br/> |<span data-ttu-id="b06e3-136">可选</span><span class="sxs-lookup"><span data-stu-id="b06e3-136">optional</span></span>  <br/> ||<span data-ttu-id="b06e3-137">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b06e3-137">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="b06e3-138">N</span><span class="sxs-lookup"><span data-stu-id="b06e3-138">N</span></span>  <br/> |<span data-ttu-id="b06e3-139">xsd：string</span><span class="sxs-lookup"><span data-stu-id="b06e3-139">xsd:string</span></span>  <br/> |<span data-ttu-id="b06e3-140">可选</span><span class="sxs-lookup"><span data-stu-id="b06e3-140">optional</span></span>  <br/> ||<span data-ttu-id="b06e3-141">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b06e3-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="b06e3-142">T</span><span class="sxs-lookup"><span data-stu-id="b06e3-142">T</span></span>  <br/> |<span data-ttu-id="b06e3-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="b06e3-143">xsd:string</span></span>  <br/> |<span data-ttu-id="b06e3-144">可选</span><span class="sxs-lookup"><span data-stu-id="b06e3-144">optional</span></span>  <br/> ||<span data-ttu-id="b06e3-145">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b06e3-145">Values of the xsd:string type.</span></span>  <br/> |
   

