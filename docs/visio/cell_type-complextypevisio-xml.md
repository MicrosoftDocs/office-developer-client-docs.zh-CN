---
title: Cell_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 38519bac-ce3e-9ded-d024-93dd7f34b107
ms.openlocfilehash: 4e0cedaab755dab669d79ff52742b8ac2b9f9725
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542301"
---
# <a name="celltype-complextype-visio-xml"></a><span data-ttu-id="e93a6-102">Cell_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="e93a6-102">Cell_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="e93a6-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="e93a6-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e93a6-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e93a6-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="e93a6-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e93a6-105">**Schema file**</span></span> <br/> |<span data-ttu-id="e93a6-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="e93a6-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="e93a6-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="e93a6-107">**Extension base**</span></span> <br/> |<span data-ttu-id="e93a6-108">无</span><span class="sxs-lookup"><span data-stu-id="e93a6-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e93a6-109">定义</span><span class="sxs-lookup"><span data-stu-id="e93a6-109">Definition</span></span>

```XML
          <xs:complexType name="Cell_Type">
          
          <xs:sequence>
    <xs:element name="RefBy"  type="RefBy_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="N"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="U"
  type="xsd:string"
    />
    <xs:attribute name="E"
  type="xsd:string"
    />
    <xs:attribute name="F"
  type="xsd:string"
    />
    <xs:attribute name="V"
  type="xsd:string"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e93a6-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e93a6-110">Elements and attributes</span></span>

<span data-ttu-id="e93a6-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="e93a6-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="e93a6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e93a6-112">Child elements</span></span>

|<span data-ttu-id="e93a6-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="e93a6-113">**Element**</span></span>|<span data-ttu-id="e93a6-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="e93a6-114">**Type**</span></span>|<span data-ttu-id="e93a6-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="e93a6-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e93a6-116">RefBy</span><span class="sxs-lookup"><span data-stu-id="e93a6-116">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e93a6-117">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="e93a6-117">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="e93a6-118">属性</span><span class="sxs-lookup"><span data-stu-id="e93a6-118">Attributes</span></span>

|<span data-ttu-id="e93a6-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="e93a6-119">**Attribute**</span></span>|<span data-ttu-id="e93a6-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="e93a6-120">**Type**</span></span>|<span data-ttu-id="e93a6-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="e93a6-121">**Required**</span></span>|<span data-ttu-id="e93a6-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="e93a6-122">**Description**</span></span>|<span data-ttu-id="e93a6-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e93a6-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e93a6-124">E</span><span class="sxs-lookup"><span data-stu-id="e93a6-124">E</span></span>  <br/> |<span data-ttu-id="e93a6-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e93a6-125">xsd:string</span></span>  <br/> |<span data-ttu-id="e93a6-126">可选</span><span class="sxs-lookup"><span data-stu-id="e93a6-126">optional</span></span>  <br/> ||<span data-ttu-id="e93a6-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e93a6-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e93a6-128">F</span><span class="sxs-lookup"><span data-stu-id="e93a6-128">F</span></span>  <br/> |<span data-ttu-id="e93a6-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e93a6-129">xsd:string</span></span>  <br/> |<span data-ttu-id="e93a6-130">可选</span><span class="sxs-lookup"><span data-stu-id="e93a6-130">optional</span></span>  <br/> ||<span data-ttu-id="e93a6-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e93a6-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e93a6-132">N</span><span class="sxs-lookup"><span data-stu-id="e93a6-132">N</span></span>  <br/> |<span data-ttu-id="e93a6-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e93a6-133">xsd:string</span></span>  <br/> |<span data-ttu-id="e93a6-134">必需</span><span class="sxs-lookup"><span data-stu-id="e93a6-134">required</span></span>  <br/> ||<span data-ttu-id="e93a6-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e93a6-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e93a6-136">U</span><span class="sxs-lookup"><span data-stu-id="e93a6-136">U</span></span>  <br/> |<span data-ttu-id="e93a6-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e93a6-137">xsd:string</span></span>  <br/> |<span data-ttu-id="e93a6-138">可选</span><span class="sxs-lookup"><span data-stu-id="e93a6-138">optional</span></span>  <br/> ||<span data-ttu-id="e93a6-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e93a6-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e93a6-140">部分</span><span class="sxs-lookup"><span data-stu-id="e93a6-140">V</span></span>  <br/> |<span data-ttu-id="e93a6-141">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e93a6-141">xsd:string</span></span>  <br/> |<span data-ttu-id="e93a6-142">可选</span><span class="sxs-lookup"><span data-stu-id="e93a6-142">optional</span></span>  <br/> ||<span data-ttu-id="e93a6-143">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e93a6-143">Values of the xsd:string type.</span></span>  <br/> |
   

