---
title: 'Cell_Type XML (Visio complexType) '
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
# <a name="cell_type-complextype-visio-xml"></a><span data-ttu-id="283a2-102">Cell_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="283a2-102">Cell_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="283a2-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="283a2-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="283a2-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="283a2-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="283a2-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="283a2-105">**Schema file**</span></span> <br/> |<span data-ttu-id="283a2-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="283a2-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="283a2-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="283a2-107">**Extension base**</span></span> <br/> |<span data-ttu-id="283a2-108">无</span><span class="sxs-lookup"><span data-stu-id="283a2-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="283a2-109">定义</span><span class="sxs-lookup"><span data-stu-id="283a2-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="283a2-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="283a2-110">Elements and attributes</span></span>

<span data-ttu-id="283a2-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="283a2-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="283a2-112">子元素</span><span class="sxs-lookup"><span data-stu-id="283a2-112">Child elements</span></span>

|<span data-ttu-id="283a2-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="283a2-113">**Element**</span></span>|<span data-ttu-id="283a2-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="283a2-114">**Type**</span></span>|<span data-ttu-id="283a2-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="283a2-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="283a2-116">RefBy</span><span class="sxs-lookup"><span data-stu-id="283a2-116">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="283a2-117">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="283a2-117">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="283a2-118">属性</span><span class="sxs-lookup"><span data-stu-id="283a2-118">Attributes</span></span>

|<span data-ttu-id="283a2-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="283a2-119">**Attribute**</span></span>|<span data-ttu-id="283a2-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="283a2-120">**Type**</span></span>|<span data-ttu-id="283a2-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="283a2-121">**Required**</span></span>|<span data-ttu-id="283a2-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="283a2-122">**Description**</span></span>|<span data-ttu-id="283a2-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="283a2-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="283a2-124">E</span><span class="sxs-lookup"><span data-stu-id="283a2-124">E</span></span>  <br/> |<span data-ttu-id="283a2-125">xsd：string</span><span class="sxs-lookup"><span data-stu-id="283a2-125">xsd:string</span></span>  <br/> |<span data-ttu-id="283a2-126">可选</span><span class="sxs-lookup"><span data-stu-id="283a2-126">optional</span></span>  <br/> ||<span data-ttu-id="283a2-127">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="283a2-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="283a2-128">F</span><span class="sxs-lookup"><span data-stu-id="283a2-128">F</span></span>  <br/> |<span data-ttu-id="283a2-129">xsd：string</span><span class="sxs-lookup"><span data-stu-id="283a2-129">xsd:string</span></span>  <br/> |<span data-ttu-id="283a2-130">可选</span><span class="sxs-lookup"><span data-stu-id="283a2-130">optional</span></span>  <br/> ||<span data-ttu-id="283a2-131">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="283a2-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="283a2-132">N</span><span class="sxs-lookup"><span data-stu-id="283a2-132">N</span></span>  <br/> |<span data-ttu-id="283a2-133">xsd：string</span><span class="sxs-lookup"><span data-stu-id="283a2-133">xsd:string</span></span>  <br/> |<span data-ttu-id="283a2-134">必需</span><span class="sxs-lookup"><span data-stu-id="283a2-134">required</span></span>  <br/> ||<span data-ttu-id="283a2-135">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="283a2-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="283a2-136">U</span><span class="sxs-lookup"><span data-stu-id="283a2-136">U</span></span>  <br/> |<span data-ttu-id="283a2-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="283a2-137">xsd:string</span></span>  <br/> |<span data-ttu-id="283a2-138">可选</span><span class="sxs-lookup"><span data-stu-id="283a2-138">optional</span></span>  <br/> ||<span data-ttu-id="283a2-139">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="283a2-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="283a2-140">V</span><span class="sxs-lookup"><span data-stu-id="283a2-140">V</span></span>  <br/> |<span data-ttu-id="283a2-141">xsd：string</span><span class="sxs-lookup"><span data-stu-id="283a2-141">xsd:string</span></span>  <br/> |<span data-ttu-id="283a2-142">可选</span><span class="sxs-lookup"><span data-stu-id="283a2-142">optional</span></span>  <br/> ||<span data-ttu-id="283a2-143">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="283a2-143">Values of the xsd:string type.</span></span>  <br/> |
   

