---
title: RowMap_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2abe0572-53bb-20fc-333f-2b69b07e99be
ms.openlocfilehash: bdc76f35cf2824d5159e945bce7e9dd2a8abe2bf
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400997"
---
# <a name="rowmaptype-complextype-visio-xml"></a><span data-ttu-id="35178-102">RowMap_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="35178-102">RowMap_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="35178-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="35178-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="35178-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="35178-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="35178-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="35178-105">**Schema file**</span></span> <br/> |<span data-ttu-id="35178-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="35178-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="35178-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="35178-107">**Extension base**</span></span> <br/> |<span data-ttu-id="35178-108">无</span><span class="sxs-lookup"><span data-stu-id="35178-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="35178-109">定义</span><span class="sxs-lookup"><span data-stu-id="35178-109">Definition</span></span>

```XML
      <xs:complexType name="RowMap_Type">
    <xs:attribute name="RowID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="PageID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="ShapeID"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="35178-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="35178-110">Elements and attributes</span></span>

<span data-ttu-id="35178-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="35178-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="35178-112">子元素</span><span class="sxs-lookup"><span data-stu-id="35178-112">Child elements</span></span>

<span data-ttu-id="35178-113">无。</span><span class="sxs-lookup"><span data-stu-id="35178-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="35178-114">属性</span><span class="sxs-lookup"><span data-stu-id="35178-114">Attributes</span></span>

|<span data-ttu-id="35178-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="35178-115">**Attribute**</span></span>|<span data-ttu-id="35178-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="35178-116">**Type**</span></span>|<span data-ttu-id="35178-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="35178-117">**Required**</span></span>|<span data-ttu-id="35178-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="35178-118">**Description**</span></span>|<span data-ttu-id="35178-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="35178-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="35178-120">PageID</span><span class="sxs-lookup"><span data-stu-id="35178-120">PageID</span></span>  <br/> |<span data-ttu-id="35178-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="35178-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="35178-122">必需</span><span class="sxs-lookup"><span data-stu-id="35178-122">required</span></span>  <br/> ||<span data-ttu-id="35178-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="35178-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="35178-124">RowID</span><span class="sxs-lookup"><span data-stu-id="35178-124">RowID</span></span>  <br/> |<span data-ttu-id="35178-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="35178-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="35178-126">必需</span><span class="sxs-lookup"><span data-stu-id="35178-126">required</span></span>  <br/> ||<span data-ttu-id="35178-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="35178-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="35178-128">ShapeID</span><span class="sxs-lookup"><span data-stu-id="35178-128">ShapeID</span></span>  <br/> |<span data-ttu-id="35178-129">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="35178-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="35178-130">必需</span><span class="sxs-lookup"><span data-stu-id="35178-130">required</span></span>  <br/> ||<span data-ttu-id="35178-131">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="35178-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

