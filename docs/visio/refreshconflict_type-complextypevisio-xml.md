---
title: RefreshConflict_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: aec7677f-a761-804c-6a12-731df86481a8
ms.openlocfilehash: 44910cd305b484771ca3d4f4d49ef8a09a6fc2dd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781047"
---
# <a name="refreshconflicttype-complextype-visio-xml"></a><span data-ttu-id="b3b6f-102">RefreshConflict_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b3b6f-102">RefreshConflict_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="b3b6f-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="b3b6f-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b3b6f-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b3b6f-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="b3b6f-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b3b6f-105">**Schema file**</span></span> <br/> |<span data-ttu-id="b3b6f-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="b3b6f-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="b3b6f-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="b3b6f-107">**Extension base**</span></span> <br/> |<span data-ttu-id="b3b6f-108">无</span><span class="sxs-lookup"><span data-stu-id="b3b6f-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b3b6f-109">定义</span><span class="sxs-lookup"><span data-stu-id="b3b6f-109">Definition</span></span>

```XML
      <xs:complexType name="RefreshConflict_Type">
    <xs:attribute name="RowID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="ShapeID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="PageID"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b3b6f-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b3b6f-110">Elements and attributes</span></span>

<span data-ttu-id="b3b6f-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="b3b6f-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="b3b6f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b3b6f-112">Child elements</span></span>

<span data-ttu-id="b3b6f-113">无。</span><span class="sxs-lookup"><span data-stu-id="b3b6f-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b3b6f-114">属性</span><span class="sxs-lookup"><span data-stu-id="b3b6f-114">Attributes</span></span>

|<span data-ttu-id="b3b6f-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="b3b6f-115">**Attribute**</span></span>|<span data-ttu-id="b3b6f-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="b3b6f-116">**Type**</span></span>|<span data-ttu-id="b3b6f-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="b3b6f-117">**Required**</span></span>|<span data-ttu-id="b3b6f-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="b3b6f-118">**Description**</span></span>|<span data-ttu-id="b3b6f-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b3b6f-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b3b6f-120">PageID</span><span class="sxs-lookup"><span data-stu-id="b3b6f-120">PageID</span></span>  <br/> |<span data-ttu-id="b3b6f-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b3b6f-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b3b6f-122">必需</span><span class="sxs-lookup"><span data-stu-id="b3b6f-122">required</span></span>  <br/> ||<span data-ttu-id="b3b6f-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b3b6f-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b3b6f-124">RowID</span><span class="sxs-lookup"><span data-stu-id="b3b6f-124">RowID</span></span>  <br/> |<span data-ttu-id="b3b6f-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b3b6f-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b3b6f-126">必需</span><span class="sxs-lookup"><span data-stu-id="b3b6f-126">required</span></span>  <br/> ||<span data-ttu-id="b3b6f-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b3b6f-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b3b6f-128">ShapeID</span><span class="sxs-lookup"><span data-stu-id="b3b6f-128">ShapeID</span></span>  <br/> |<span data-ttu-id="b3b6f-129">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b3b6f-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b3b6f-130">必需</span><span class="sxs-lookup"><span data-stu-id="b3b6f-130">required</span></span>  <br/> ||<span data-ttu-id="b3b6f-131">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b3b6f-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

