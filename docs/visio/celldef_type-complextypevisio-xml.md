---
title: CellDef_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 87ea346d-1786-dc87-073d-8e7459b7fef1
ms.openlocfilehash: 7b437e35aadfef0390908cb1337cc738668382e5
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542294"
---
# <a name="celldeftype-complextype-visio-xml"></a><span data-ttu-id="771d1-102">CellDef_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="771d1-102">CellDef_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="771d1-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="771d1-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="771d1-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="771d1-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="771d1-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="771d1-105">**Schema file**</span></span> <br/> |<span data-ttu-id="771d1-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="771d1-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="771d1-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="771d1-107">**Extension base**</span></span> <br/> |<span data-ttu-id="771d1-108">无</span><span class="sxs-lookup"><span data-stu-id="771d1-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="771d1-109">定义</span><span class="sxs-lookup"><span data-stu-id="771d1-109">Definition</span></span>

```XML
      <xs:complexType name="CellDef_Type">
    <xs:attribute name="N"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="T"
  type="xsd:token"
     use="required"
    />
    <xs:attribute name="F"
  type="xsd:string"
    />
    <xs:attribute name="IX"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="S"
  type="xsd:unsignedByte"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="771d1-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="771d1-110">Elements and attributes</span></span>

<span data-ttu-id="771d1-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="771d1-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="771d1-112">子元素</span><span class="sxs-lookup"><span data-stu-id="771d1-112">Child elements</span></span>

<span data-ttu-id="771d1-113">无。</span><span class="sxs-lookup"><span data-stu-id="771d1-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="771d1-114">属性</span><span class="sxs-lookup"><span data-stu-id="771d1-114">Attributes</span></span>

|<span data-ttu-id="771d1-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="771d1-115">**Attribute**</span></span>|<span data-ttu-id="771d1-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="771d1-116">**Type**</span></span>|<span data-ttu-id="771d1-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="771d1-117">**Required**</span></span>|<span data-ttu-id="771d1-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="771d1-118">**Description**</span></span>|<span data-ttu-id="771d1-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="771d1-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="771d1-120">F</span><span class="sxs-lookup"><span data-stu-id="771d1-120">F</span></span>  <br/> |<span data-ttu-id="771d1-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="771d1-121">xsd:string</span></span>  <br/> |<span data-ttu-id="771d1-122">可选</span><span class="sxs-lookup"><span data-stu-id="771d1-122">optional</span></span>  <br/> ||<span data-ttu-id="771d1-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="771d1-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="771d1-124">IX</span><span class="sxs-lookup"><span data-stu-id="771d1-124">IX</span></span>  <br/> |<span data-ttu-id="771d1-125">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="771d1-125">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="771d1-126">可选</span><span class="sxs-lookup"><span data-stu-id="771d1-126">optional</span></span>  <br/> ||<span data-ttu-id="771d1-127">Xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="771d1-127">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="771d1-128">N</span><span class="sxs-lookup"><span data-stu-id="771d1-128">N</span></span>  <br/> |<span data-ttu-id="771d1-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="771d1-129">xsd:string</span></span>  <br/> |<span data-ttu-id="771d1-130">必需</span><span class="sxs-lookup"><span data-stu-id="771d1-130">required</span></span>  <br/> ||<span data-ttu-id="771d1-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="771d1-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="771d1-132">S</span><span class="sxs-lookup"><span data-stu-id="771d1-132">S</span></span>  <br/> |<span data-ttu-id="771d1-133">xsd: unsignedByte</span><span class="sxs-lookup"><span data-stu-id="771d1-133">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="771d1-134">可选</span><span class="sxs-lookup"><span data-stu-id="771d1-134">optional</span></span>  <br/> ||<span data-ttu-id="771d1-135">Xsd: unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="771d1-135">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="771d1-136">T</span><span class="sxs-lookup"><span data-stu-id="771d1-136">T</span></span>  <br/> |<span data-ttu-id="771d1-137">xsd: token</span><span class="sxs-lookup"><span data-stu-id="771d1-137">xsd:token</span></span>  <br/> |<span data-ttu-id="771d1-138">必需</span><span class="sxs-lookup"><span data-stu-id="771d1-138">required</span></span>  <br/> ||<span data-ttu-id="771d1-139">Xsd: 令牌类型的值。</span><span class="sxs-lookup"><span data-stu-id="771d1-139">Values of the xsd:token type.</span></span>  <br/> |
   

