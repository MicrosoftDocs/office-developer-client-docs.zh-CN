---
title: FaceName_Type 复杂类型 (Visio XML)
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
# <a name="facenametype-complextype-visio-xml"></a><span data-ttu-id="2b32c-102">FaceName_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="2b32c-102">FaceName_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="2b32c-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="2b32c-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2b32c-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2b32c-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="2b32c-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2b32c-105">**Schema file**</span></span> <br/> |<span data-ttu-id="2b32c-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="2b32c-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="2b32c-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="2b32c-107">**Extension base**</span></span> <br/> |<span data-ttu-id="2b32c-108">无</span><span class="sxs-lookup"><span data-stu-id="2b32c-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2b32c-109">定义</span><span class="sxs-lookup"><span data-stu-id="2b32c-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="2b32c-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2b32c-110">Elements and attributes</span></span>

<span data-ttu-id="2b32c-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="2b32c-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="2b32c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2b32c-112">Child elements</span></span>

<span data-ttu-id="2b32c-113">无。</span><span class="sxs-lookup"><span data-stu-id="2b32c-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="2b32c-114">属性</span><span class="sxs-lookup"><span data-stu-id="2b32c-114">Attributes</span></span>

|<span data-ttu-id="2b32c-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="2b32c-115">**Attribute**</span></span>|<span data-ttu-id="2b32c-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="2b32c-116">**Type**</span></span>|<span data-ttu-id="2b32c-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="2b32c-117">**Required**</span></span>|<span data-ttu-id="2b32c-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="2b32c-118">**Description**</span></span>|<span data-ttu-id="2b32c-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="2b32c-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b32c-120">CharSets</span><span class="sxs-lookup"><span data-stu-id="2b32c-120">CharSets</span></span>  <br/> |<span data-ttu-id="2b32c-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2b32c-121">xsd:string</span></span>  <br/> |<span data-ttu-id="2b32c-122">可选</span><span class="sxs-lookup"><span data-stu-id="2b32c-122">optional</span></span>  <br/> ||<span data-ttu-id="2b32c-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b32c-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2b32c-124">Flags</span><span class="sxs-lookup"><span data-stu-id="2b32c-124">Flags</span></span>  <br/> |<span data-ttu-id="2b32c-125">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="2b32c-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="2b32c-126">可选</span><span class="sxs-lookup"><span data-stu-id="2b32c-126">optional</span></span>  <br/> ||<span data-ttu-id="2b32c-127">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b32c-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="2b32c-128">NameU</span><span class="sxs-lookup"><span data-stu-id="2b32c-128">NameU</span></span>  <br/> |<span data-ttu-id="2b32c-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2b32c-129">xsd:string</span></span>  <br/> |<span data-ttu-id="2b32c-130">必需</span><span class="sxs-lookup"><span data-stu-id="2b32c-130">required</span></span>  <br/> ||<span data-ttu-id="2b32c-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b32c-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2b32c-132">Panos</span><span class="sxs-lookup"><span data-stu-id="2b32c-132">Panos</span></span>  <br/> |<span data-ttu-id="2b32c-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2b32c-133">xsd:string</span></span>  <br/> |<span data-ttu-id="2b32c-134">可选</span><span class="sxs-lookup"><span data-stu-id="2b32c-134">optional</span></span>  <br/> ||<span data-ttu-id="2b32c-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b32c-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2b32c-136">Panose</span><span class="sxs-lookup"><span data-stu-id="2b32c-136">Panose</span></span>  <br/> |<span data-ttu-id="2b32c-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2b32c-137">xsd:string</span></span>  <br/> |<span data-ttu-id="2b32c-138">可选</span><span class="sxs-lookup"><span data-stu-id="2b32c-138">optional</span></span>  <br/> ||<span data-ttu-id="2b32c-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b32c-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2b32c-140">UnicodeRanges</span><span class="sxs-lookup"><span data-stu-id="2b32c-140">UnicodeRanges</span></span>  <br/> |<span data-ttu-id="2b32c-141">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2b32c-141">xsd:string</span></span>  <br/> |<span data-ttu-id="2b32c-142">可选</span><span class="sxs-lookup"><span data-stu-id="2b32c-142">optional</span></span>  <br/> ||<span data-ttu-id="2b32c-143">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b32c-143">Values of the xsd:string type.</span></span>  <br/> |
   

