---
title: 'DataConnection_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 13683c47-2bc8-1345-ed0e-4175a06ea452
ms.openlocfilehash: 44dceee9a9ef43557e9bc02828f91c2c29d345d6
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539647"
---
# <a name="dataconnection_type-complextype-visio-xml"></a><span data-ttu-id="74bb4-102">DataConnection_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="74bb4-102">DataConnection_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="74bb4-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="74bb4-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="74bb4-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="74bb4-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="74bb4-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="74bb4-105">**Schema file**</span></span> <br/> |<span data-ttu-id="74bb4-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="74bb4-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="74bb4-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="74bb4-107">**Extension base**</span></span> <br/> |<span data-ttu-id="74bb4-108">无</span><span class="sxs-lookup"><span data-stu-id="74bb4-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="74bb4-109">定义</span><span class="sxs-lookup"><span data-stu-id="74bb4-109">Definition</span></span>

```XML
      <xs:complexType name="DataConnection_Type">
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="FileName"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="ConnectionString"
  type="xsd:string"
    />
    <xs:attribute name="Command"
  type="xsd:string"
    />
    <xs:attribute name="FriendlyName"
  type="xsd:string"
    />
    <xs:attribute name="Timeout"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="AlwaysUseConnectionFile"
  type="xsd:boolean"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="74bb4-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="74bb4-110">Elements and attributes</span></span>

<span data-ttu-id="74bb4-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="74bb4-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="74bb4-112">子元素</span><span class="sxs-lookup"><span data-stu-id="74bb4-112">Child elements</span></span>

<span data-ttu-id="74bb4-113">无。</span><span class="sxs-lookup"><span data-stu-id="74bb4-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="74bb4-114">属性</span><span class="sxs-lookup"><span data-stu-id="74bb4-114">Attributes</span></span>

|<span data-ttu-id="74bb4-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="74bb4-115">**Attribute**</span></span>|<span data-ttu-id="74bb4-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="74bb4-116">**Type**</span></span>|<span data-ttu-id="74bb4-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="74bb4-117">**Required**</span></span>|<span data-ttu-id="74bb4-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="74bb4-118">**Description**</span></span>|<span data-ttu-id="74bb4-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="74bb4-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="74bb4-120">AlwaysUseConnectionFile</span><span class="sxs-lookup"><span data-stu-id="74bb4-120">AlwaysUseConnectionFile</span></span>  <br/> |<span data-ttu-id="74bb4-121">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="74bb4-121">xsd:boolean</span></span>  <br/> |<span data-ttu-id="74bb4-122">可选</span><span class="sxs-lookup"><span data-stu-id="74bb4-122">optional</span></span>  <br/> ||<span data-ttu-id="74bb4-123">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="74bb4-123">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="74bb4-124">Command</span><span class="sxs-lookup"><span data-stu-id="74bb4-124">Command</span></span>  <br/> |<span data-ttu-id="74bb4-125">xsd：string</span><span class="sxs-lookup"><span data-stu-id="74bb4-125">xsd:string</span></span>  <br/> |<span data-ttu-id="74bb4-126">可选</span><span class="sxs-lookup"><span data-stu-id="74bb4-126">optional</span></span>  <br/> ||<span data-ttu-id="74bb4-127">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="74bb4-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="74bb4-128">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="74bb4-128">ConnectionString</span></span>  <br/> |<span data-ttu-id="74bb4-129">xsd：string</span><span class="sxs-lookup"><span data-stu-id="74bb4-129">xsd:string</span></span>  <br/> |<span data-ttu-id="74bb4-130">可选</span><span class="sxs-lookup"><span data-stu-id="74bb4-130">optional</span></span>  <br/> ||<span data-ttu-id="74bb4-131">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="74bb4-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="74bb4-132">FileName</span><span class="sxs-lookup"><span data-stu-id="74bb4-132">FileName</span></span>  <br/> |<span data-ttu-id="74bb4-133">xsd：string</span><span class="sxs-lookup"><span data-stu-id="74bb4-133">xsd:string</span></span>  <br/> |<span data-ttu-id="74bb4-134">必需</span><span class="sxs-lookup"><span data-stu-id="74bb4-134">required</span></span>  <br/> ||<span data-ttu-id="74bb4-135">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="74bb4-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="74bb4-136">FriendlyName</span><span class="sxs-lookup"><span data-stu-id="74bb4-136">FriendlyName</span></span>  <br/> |<span data-ttu-id="74bb4-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="74bb4-137">xsd:string</span></span>  <br/> |<span data-ttu-id="74bb4-138">可选</span><span class="sxs-lookup"><span data-stu-id="74bb4-138">optional</span></span>  <br/> ||<span data-ttu-id="74bb4-139">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="74bb4-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="74bb4-140">ID</span><span class="sxs-lookup"><span data-stu-id="74bb4-140">ID</span></span>  <br/> |<span data-ttu-id="74bb4-141">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="74bb4-141">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="74bb4-142">必需</span><span class="sxs-lookup"><span data-stu-id="74bb4-142">required</span></span>  <br/> ||<span data-ttu-id="74bb4-143">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="74bb4-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="74bb4-144">Timeout</span><span class="sxs-lookup"><span data-stu-id="74bb4-144">Timeout</span></span>  <br/> |<span data-ttu-id="74bb4-145">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="74bb4-145">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="74bb4-146">可选</span><span class="sxs-lookup"><span data-stu-id="74bb4-146">optional</span></span>  <br/> ||<span data-ttu-id="74bb4-147">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="74bb4-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

