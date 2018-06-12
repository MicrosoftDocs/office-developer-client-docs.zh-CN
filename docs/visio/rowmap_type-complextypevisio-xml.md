---
title: RowMap_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2abe0572-53bb-20fc-333f-2b69b07e99be
ms.openlocfilehash: 18f573a480e3ae057074a219def192f6b1b2829b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781176"
---
# <a name="rowmaptype-complextype-visio-xml"></a><span data-ttu-id="5ca0a-102">RowMap_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="5ca0a-102">RowMap_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="5ca0a-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="5ca0a-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5ca0a-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5ca0a-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="5ca0a-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5ca0a-105">**Schema file**</span></span> <br/> |<span data-ttu-id="5ca0a-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="5ca0a-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="5ca0a-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="5ca0a-107">**Extension base**</span></span> <br/> |<span data-ttu-id="5ca0a-108">无</span><span class="sxs-lookup"><span data-stu-id="5ca0a-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5ca0a-109">定义</span><span class="sxs-lookup"><span data-stu-id="5ca0a-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="5ca0a-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5ca0a-110">Elements and attributes</span></span>

<span data-ttu-id="5ca0a-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="5ca0a-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="5ca0a-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5ca0a-112">Child elements</span></span>

<span data-ttu-id="5ca0a-113">无。</span><span class="sxs-lookup"><span data-stu-id="5ca0a-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="5ca0a-114">属性</span><span class="sxs-lookup"><span data-stu-id="5ca0a-114">Attributes</span></span>

|<span data-ttu-id="5ca0a-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="5ca0a-115">**Attribute**</span></span>|<span data-ttu-id="5ca0a-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="5ca0a-116">**Type**</span></span>|<span data-ttu-id="5ca0a-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="5ca0a-117">**Required**</span></span>|<span data-ttu-id="5ca0a-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="5ca0a-118">**Description**</span></span>|<span data-ttu-id="5ca0a-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="5ca0a-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5ca0a-120">PageID</span><span class="sxs-lookup"><span data-stu-id="5ca0a-120">PageID</span></span>  <br/> |<span data-ttu-id="5ca0a-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5ca0a-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5ca0a-122">必需</span><span class="sxs-lookup"><span data-stu-id="5ca0a-122">required</span></span>  <br/> ||<span data-ttu-id="5ca0a-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5ca0a-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5ca0a-124">RowID</span><span class="sxs-lookup"><span data-stu-id="5ca0a-124">RowID</span></span>  <br/> |<span data-ttu-id="5ca0a-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5ca0a-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5ca0a-126">必需</span><span class="sxs-lookup"><span data-stu-id="5ca0a-126">required</span></span>  <br/> ||<span data-ttu-id="5ca0a-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5ca0a-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5ca0a-128">ShapeID</span><span class="sxs-lookup"><span data-stu-id="5ca0a-128">ShapeID</span></span>  <br/> |<span data-ttu-id="5ca0a-129">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5ca0a-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5ca0a-130">必需</span><span class="sxs-lookup"><span data-stu-id="5ca0a-130">required</span></span>  <br/> ||<span data-ttu-id="5ca0a-131">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5ca0a-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

