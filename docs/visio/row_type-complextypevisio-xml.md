---
title: Row_Type 复杂类型 (Visio XML)
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
# <a name="rowtype-complextype-visio-xml"></a><span data-ttu-id="b75d7-102">Row_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b75d7-102">Row_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="b75d7-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="b75d7-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b75d7-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b75d7-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="b75d7-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b75d7-105">**Schema file**</span></span> <br/> |<span data-ttu-id="b75d7-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="b75d7-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="b75d7-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="b75d7-107">**Extension base**</span></span> <br/> |<span data-ttu-id="b75d7-108">无</span><span class="sxs-lookup"><span data-stu-id="b75d7-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b75d7-109">定义</span><span class="sxs-lookup"><span data-stu-id="b75d7-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="b75d7-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b75d7-110">Elements and attributes</span></span>

<span data-ttu-id="b75d7-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="b75d7-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="b75d7-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b75d7-112">Child elements</span></span>

|<span data-ttu-id="b75d7-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="b75d7-113">**Element**</span></span>|<span data-ttu-id="b75d7-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="b75d7-114">**Type**</span></span>|<span data-ttu-id="b75d7-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="b75d7-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b75d7-116">Cell</span><span class="sxs-lookup"><span data-stu-id="b75d7-116">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="b75d7-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="b75d7-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b75d7-118">Trigger</span><span class="sxs-lookup"><span data-stu-id="b75d7-118">Trigger</span></span>](trigger-elementvisio-xml.md) <br/> |[<span data-ttu-id="b75d7-119">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="b75d7-119">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="b75d7-120">属性</span><span class="sxs-lookup"><span data-stu-id="b75d7-120">Attributes</span></span>

|<span data-ttu-id="b75d7-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="b75d7-121">**Attribute**</span></span>|<span data-ttu-id="b75d7-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="b75d7-122">**Type**</span></span>|<span data-ttu-id="b75d7-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="b75d7-123">**Required**</span></span>|<span data-ttu-id="b75d7-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="b75d7-124">**Description**</span></span>|<span data-ttu-id="b75d7-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b75d7-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b75d7-126">键</span><span class="sxs-lookup"><span data-stu-id="b75d7-126">Del</span></span>  <br/> |<span data-ttu-id="b75d7-127">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="b75d7-127">xsd:boolean</span></span>  <br/> |<span data-ttu-id="b75d7-128">可选</span><span class="sxs-lookup"><span data-stu-id="b75d7-128">optional</span></span>  <br/> ||<span data-ttu-id="b75d7-129">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b75d7-129">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="b75d7-130">IX</span><span class="sxs-lookup"><span data-stu-id="b75d7-130">IX</span></span>  <br/> |<span data-ttu-id="b75d7-131">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b75d7-131">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b75d7-132">可选</span><span class="sxs-lookup"><span data-stu-id="b75d7-132">optional</span></span>  <br/> ||<span data-ttu-id="b75d7-133">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b75d7-133">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b75d7-134">LocalName</span><span class="sxs-lookup"><span data-stu-id="b75d7-134">LocalName</span></span>  <br/> |<span data-ttu-id="b75d7-135">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b75d7-135">xsd:string</span></span>  <br/> |<span data-ttu-id="b75d7-136">可选</span><span class="sxs-lookup"><span data-stu-id="b75d7-136">optional</span></span>  <br/> ||<span data-ttu-id="b75d7-137">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b75d7-137">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="b75d7-138">N</span><span class="sxs-lookup"><span data-stu-id="b75d7-138">N</span></span>  <br/> |<span data-ttu-id="b75d7-139">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b75d7-139">xsd:string</span></span>  <br/> |<span data-ttu-id="b75d7-140">可选</span><span class="sxs-lookup"><span data-stu-id="b75d7-140">optional</span></span>  <br/> ||<span data-ttu-id="b75d7-141">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b75d7-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="b75d7-142">T</span><span class="sxs-lookup"><span data-stu-id="b75d7-142">T</span></span>  <br/> |<span data-ttu-id="b75d7-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b75d7-143">xsd:string</span></span>  <br/> |<span data-ttu-id="b75d7-144">可选</span><span class="sxs-lookup"><span data-stu-id="b75d7-144">optional</span></span>  <br/> ||<span data-ttu-id="b75d7-145">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b75d7-145">Values of the xsd:string type.</span></span>  <br/> |
   

