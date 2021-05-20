---
title: 'FaceName_Type XML (Visio complexType) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d24f350c-35bf-ab16-2469-39fd5344e5fe
ms.openlocfilehash: f0a136cec6d620ba7001ed0e6fae01af82c2180d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542896"
---
# <a name="facename_type-complextype-visio-xml"></a><span data-ttu-id="16bab-102">FaceName_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="16bab-102">FaceName_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="16bab-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="16bab-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="16bab-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="16bab-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="16bab-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="16bab-105">**Schema file**</span></span> <br/> |<span data-ttu-id="16bab-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="16bab-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="16bab-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="16bab-107">**Extension base**</span></span> <br/> |<span data-ttu-id="16bab-108">无</span><span class="sxs-lookup"><span data-stu-id="16bab-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="16bab-109">定义</span><span class="sxs-lookup"><span data-stu-id="16bab-109">Definition</span></span>

```XML
      <xs:complexType name="FaceName_Type">
    <xs:attribute name="NameU"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="UnicodeRanges"
  type="xsd:string"
    />
    <xs:attribute name="CharSets"
  type="xsd:string"
    />
    <xs:attribute name="Panos"
  type="xsd:string"
    />
    <xs:attribute name="Panose"
  type="xsd:string"
    />
    <xs:attribute name="Flags"
  type="xsd:unsignedInt"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="16bab-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="16bab-110">Elements and attributes</span></span>

<span data-ttu-id="16bab-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="16bab-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="16bab-112">子元素</span><span class="sxs-lookup"><span data-stu-id="16bab-112">Child elements</span></span>

<span data-ttu-id="16bab-113">无。</span><span class="sxs-lookup"><span data-stu-id="16bab-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="16bab-114">属性</span><span class="sxs-lookup"><span data-stu-id="16bab-114">Attributes</span></span>

|<span data-ttu-id="16bab-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="16bab-115">**Attribute**</span></span>|<span data-ttu-id="16bab-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="16bab-116">**Type**</span></span>|<span data-ttu-id="16bab-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="16bab-117">**Required**</span></span>|<span data-ttu-id="16bab-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="16bab-118">**Description**</span></span>|<span data-ttu-id="16bab-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="16bab-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="16bab-120">CharSets</span><span class="sxs-lookup"><span data-stu-id="16bab-120">CharSets</span></span>  <br/> |<span data-ttu-id="16bab-121">xsd：string</span><span class="sxs-lookup"><span data-stu-id="16bab-121">xsd:string</span></span>  <br/> |<span data-ttu-id="16bab-122">可选</span><span class="sxs-lookup"><span data-stu-id="16bab-122">optional</span></span>  <br/> ||<span data-ttu-id="16bab-123">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16bab-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="16bab-124">Flags</span><span class="sxs-lookup"><span data-stu-id="16bab-124">Flags</span></span>  <br/> |<span data-ttu-id="16bab-125">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="16bab-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="16bab-126">可选</span><span class="sxs-lookup"><span data-stu-id="16bab-126">optional</span></span>  <br/> ||<span data-ttu-id="16bab-127">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16bab-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="16bab-128">NameU</span><span class="sxs-lookup"><span data-stu-id="16bab-128">NameU</span></span>  <br/> |<span data-ttu-id="16bab-129">xsd：string</span><span class="sxs-lookup"><span data-stu-id="16bab-129">xsd:string</span></span>  <br/> |<span data-ttu-id="16bab-130">必需</span><span class="sxs-lookup"><span data-stu-id="16bab-130">required</span></span>  <br/> ||<span data-ttu-id="16bab-131">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16bab-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="16bab-132">Panos</span><span class="sxs-lookup"><span data-stu-id="16bab-132">Panos</span></span>  <br/> |<span data-ttu-id="16bab-133">xsd：string</span><span class="sxs-lookup"><span data-stu-id="16bab-133">xsd:string</span></span>  <br/> |<span data-ttu-id="16bab-134">可选</span><span class="sxs-lookup"><span data-stu-id="16bab-134">optional</span></span>  <br/> ||<span data-ttu-id="16bab-135">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16bab-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="16bab-136">Panose</span><span class="sxs-lookup"><span data-stu-id="16bab-136">Panose</span></span>  <br/> |<span data-ttu-id="16bab-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="16bab-137">xsd:string</span></span>  <br/> |<span data-ttu-id="16bab-138">可选</span><span class="sxs-lookup"><span data-stu-id="16bab-138">optional</span></span>  <br/> ||<span data-ttu-id="16bab-139">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16bab-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="16bab-140">UnicodeRanges</span><span class="sxs-lookup"><span data-stu-id="16bab-140">UnicodeRanges</span></span>  <br/> |<span data-ttu-id="16bab-141">xsd：string</span><span class="sxs-lookup"><span data-stu-id="16bab-141">xsd:string</span></span>  <br/> |<span data-ttu-id="16bab-142">可选</span><span class="sxs-lookup"><span data-stu-id="16bab-142">optional</span></span>  <br/> ||<span data-ttu-id="16bab-143">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="16bab-143">Values of the xsd:string type.</span></span>  <br/> |
   

