---
title: EventItem_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f157db03-e7d0-d39f-cbde-2a22f45b40ed
ms.openlocfilehash: f0fd618cc2a86d3695d0d6f6c446f118475ffc1f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541790"
---
# <a name="eventitemtype-complextype-visio-xml"></a><span data-ttu-id="28857-102">EventItem_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="28857-102">EventItem_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="28857-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="28857-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="28857-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="28857-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="28857-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="28857-105">**Schema file**</span></span> <br/> |<span data-ttu-id="28857-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="28857-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="28857-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="28857-107">**Extension base**</span></span> <br/> |<span data-ttu-id="28857-108">无</span><span class="sxs-lookup"><span data-stu-id="28857-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="28857-109">定义</span><span class="sxs-lookup"><span data-stu-id="28857-109">Definition</span></span>

```XML
      <xs:complexType name="EventItem_Type">
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="Action"
  type="xsd:unsignedShort"
     use="required"
    />
    <xs:attribute name="EventCode"
  type="xsd:unsignedShort"
     use="required"
    />
    <xs:attribute name="Enabled"
  type="xsd:boolean"
    />
    <xs:attribute name="Target"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="TargetArgs"
  type="xsd:string"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="28857-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="28857-110">Elements and attributes</span></span>

<span data-ttu-id="28857-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="28857-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="28857-112">子元素</span><span class="sxs-lookup"><span data-stu-id="28857-112">Child elements</span></span>

<span data-ttu-id="28857-113">无。</span><span class="sxs-lookup"><span data-stu-id="28857-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="28857-114">属性</span><span class="sxs-lookup"><span data-stu-id="28857-114">Attributes</span></span>

|<span data-ttu-id="28857-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="28857-115">**Attribute**</span></span>|<span data-ttu-id="28857-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="28857-116">**Type**</span></span>|<span data-ttu-id="28857-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="28857-117">**Required**</span></span>|<span data-ttu-id="28857-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="28857-118">**Description**</span></span>|<span data-ttu-id="28857-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="28857-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28857-120">操作</span><span class="sxs-lookup"><span data-stu-id="28857-120">Action</span></span>  <br/> |<span data-ttu-id="28857-121">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="28857-121">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="28857-122">必需</span><span class="sxs-lookup"><span data-stu-id="28857-122">required</span></span>  <br/> ||<span data-ttu-id="28857-123">Xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28857-123">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="28857-124">已启用</span><span class="sxs-lookup"><span data-stu-id="28857-124">Enabled</span></span>  <br/> |<span data-ttu-id="28857-125">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="28857-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="28857-126">可选</span><span class="sxs-lookup"><span data-stu-id="28857-126">optional</span></span>  <br/> ||<span data-ttu-id="28857-127">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28857-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="28857-128">EventCode</span><span class="sxs-lookup"><span data-stu-id="28857-128">EventCode</span></span>  <br/> |<span data-ttu-id="28857-129">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="28857-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="28857-130">必需</span><span class="sxs-lookup"><span data-stu-id="28857-130">required</span></span>  <br/> ||<span data-ttu-id="28857-131">Xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28857-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="28857-132">ID</span><span class="sxs-lookup"><span data-stu-id="28857-132">ID</span></span>  <br/> |<span data-ttu-id="28857-133">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="28857-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="28857-134">必需</span><span class="sxs-lookup"><span data-stu-id="28857-134">required</span></span>  <br/> ||<span data-ttu-id="28857-135">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28857-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="28857-136">Target</span><span class="sxs-lookup"><span data-stu-id="28857-136">Target</span></span>  <br/> |<span data-ttu-id="28857-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="28857-137">xsd:string</span></span>  <br/> |<span data-ttu-id="28857-138">必需</span><span class="sxs-lookup"><span data-stu-id="28857-138">required</span></span>  <br/> ||<span data-ttu-id="28857-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28857-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="28857-140">TargetArgs</span><span class="sxs-lookup"><span data-stu-id="28857-140">TargetArgs</span></span>  <br/> |<span data-ttu-id="28857-141">xsd: string</span><span class="sxs-lookup"><span data-stu-id="28857-141">xsd:string</span></span>  <br/> |<span data-ttu-id="28857-142">必需</span><span class="sxs-lookup"><span data-stu-id="28857-142">required</span></span>  <br/> ||<span data-ttu-id="28857-143">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="28857-143">Values of the xsd:string type.</span></span>  <br/> |
   

