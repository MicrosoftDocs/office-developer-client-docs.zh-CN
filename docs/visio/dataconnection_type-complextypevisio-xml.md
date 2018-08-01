---
title: DataConnection_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 13683c47-2bc8-1345-ed0e-4175a06ea452
ms.openlocfilehash: 3a900e22fd36c936f689081149b484bd5e7460fe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780044"
---
# <a name="dataconnectiontype-complextype-visio-xml"></a><span data-ttu-id="d51d6-102">DataConnection_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d51d6-102">DataConnection_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="d51d6-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="d51d6-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d51d6-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d51d6-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="d51d6-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d51d6-105">**Schema file**</span></span> <br/> |<span data-ttu-id="d51d6-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="d51d6-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="d51d6-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="d51d6-107">**Extension base**</span></span> <br/> |<span data-ttu-id="d51d6-108">无</span><span class="sxs-lookup"><span data-stu-id="d51d6-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d51d6-109">定义</span><span class="sxs-lookup"><span data-stu-id="d51d6-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="d51d6-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d51d6-110">Elements and attributes</span></span>

<span data-ttu-id="d51d6-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d51d6-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="d51d6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d51d6-112">Child elements</span></span>

<span data-ttu-id="d51d6-113">无。</span><span class="sxs-lookup"><span data-stu-id="d51d6-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d51d6-114">属性</span><span class="sxs-lookup"><span data-stu-id="d51d6-114">Attributes</span></span>

|<span data-ttu-id="d51d6-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="d51d6-115">**Attribute**</span></span>|<span data-ttu-id="d51d6-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="d51d6-116">**Type**</span></span>|<span data-ttu-id="d51d6-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="d51d6-117">**Required**</span></span>|<span data-ttu-id="d51d6-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="d51d6-118">**Description**</span></span>|<span data-ttu-id="d51d6-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d51d6-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d51d6-120">AlwaysUseConnectionFile</span><span class="sxs-lookup"><span data-stu-id="d51d6-120">AlwaysUseConnectionFile</span></span>  <br/> |<span data-ttu-id="d51d6-121">化</span><span class="sxs-lookup"><span data-stu-id="d51d6-121">xsd:boolean</span></span>  <br/> |<span data-ttu-id="d51d6-122">可选</span><span class="sxs-lookup"><span data-stu-id="d51d6-122">optional</span></span>  <br/> ||<span data-ttu-id="d51d6-123">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="d51d6-123">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="d51d6-124">命令</span><span class="sxs-lookup"><span data-stu-id="d51d6-124">Command</span></span>  <br/> |<span data-ttu-id="d51d6-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d51d6-125">xsd:string</span></span>  <br/> |<span data-ttu-id="d51d6-126">可选</span><span class="sxs-lookup"><span data-stu-id="d51d6-126">optional</span></span>  <br/> ||<span data-ttu-id="d51d6-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d51d6-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d51d6-128">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="d51d6-128">ConnectionString</span></span>  <br/> |<span data-ttu-id="d51d6-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d51d6-129">xsd:string</span></span>  <br/> |<span data-ttu-id="d51d6-130">可选</span><span class="sxs-lookup"><span data-stu-id="d51d6-130">optional</span></span>  <br/> ||<span data-ttu-id="d51d6-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d51d6-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d51d6-132">FileName</span><span class="sxs-lookup"><span data-stu-id="d51d6-132">FileName</span></span>  <br/> |<span data-ttu-id="d51d6-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d51d6-133">xsd:string</span></span>  <br/> |<span data-ttu-id="d51d6-134">必需</span><span class="sxs-lookup"><span data-stu-id="d51d6-134">required</span></span>  <br/> ||<span data-ttu-id="d51d6-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d51d6-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d51d6-136">FriendlyName</span><span class="sxs-lookup"><span data-stu-id="d51d6-136">FriendlyName</span></span>  <br/> |<span data-ttu-id="d51d6-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d51d6-137">xsd:string</span></span>  <br/> |<span data-ttu-id="d51d6-138">可选</span><span class="sxs-lookup"><span data-stu-id="d51d6-138">optional</span></span>  <br/> ||<span data-ttu-id="d51d6-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d51d6-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d51d6-140">ID</span><span class="sxs-lookup"><span data-stu-id="d51d6-140">ID</span></span>  <br/> |<span data-ttu-id="d51d6-141">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d51d6-141">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d51d6-142">必需</span><span class="sxs-lookup"><span data-stu-id="d51d6-142">required</span></span>  <br/> ||<span data-ttu-id="d51d6-143">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d51d6-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d51d6-144">Timeout</span><span class="sxs-lookup"><span data-stu-id="d51d6-144">Timeout</span></span>  <br/> |<span data-ttu-id="d51d6-145">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d51d6-145">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d51d6-146">可选</span><span class="sxs-lookup"><span data-stu-id="d51d6-146">optional</span></span>  <br/> ||<span data-ttu-id="d51d6-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d51d6-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

