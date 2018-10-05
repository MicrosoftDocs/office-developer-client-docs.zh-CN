---
title: RefreshConflict_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: aec7677f-a761-804c-6a12-731df86481a8
ms.openlocfilehash: 25c83a8168744820fa8b570dc37bda0547ab4ea0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383168"
---
# <a name="refreshconflicttype-complextype-visio-xml"></a><span data-ttu-id="df051-102">RefreshConflict_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="df051-102">RefreshConflict_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="df051-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="df051-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="df051-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="df051-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="df051-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="df051-105">**Schema file**</span></span> <br/> |<span data-ttu-id="df051-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="df051-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="df051-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="df051-107">**Extension base**</span></span> <br/> |<span data-ttu-id="df051-108">无</span><span class="sxs-lookup"><span data-stu-id="df051-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="df051-109">定义</span><span class="sxs-lookup"><span data-stu-id="df051-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="df051-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="df051-110">Elements and attributes</span></span>

<span data-ttu-id="df051-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="df051-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="df051-112">子元素</span><span class="sxs-lookup"><span data-stu-id="df051-112">Child elements</span></span>

<span data-ttu-id="df051-113">无。</span><span class="sxs-lookup"><span data-stu-id="df051-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="df051-114">属性</span><span class="sxs-lookup"><span data-stu-id="df051-114">Attributes</span></span>

|<span data-ttu-id="df051-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="df051-115">**Attribute**</span></span>|<span data-ttu-id="df051-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="df051-116">**Type**</span></span>|<span data-ttu-id="df051-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="df051-117">**Required**</span></span>|<span data-ttu-id="df051-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="df051-118">**Description**</span></span>|<span data-ttu-id="df051-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="df051-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="df051-120">PageID</span><span class="sxs-lookup"><span data-stu-id="df051-120">PageID</span></span>  <br/> |<span data-ttu-id="df051-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="df051-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="df051-122">必需</span><span class="sxs-lookup"><span data-stu-id="df051-122">required</span></span>  <br/> ||<span data-ttu-id="df051-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="df051-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="df051-124">RowID</span><span class="sxs-lookup"><span data-stu-id="df051-124">RowID</span></span>  <br/> |<span data-ttu-id="df051-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="df051-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="df051-126">必需</span><span class="sxs-lookup"><span data-stu-id="df051-126">required</span></span>  <br/> ||<span data-ttu-id="df051-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="df051-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="df051-128">ShapeID</span><span class="sxs-lookup"><span data-stu-id="df051-128">ShapeID</span></span>  <br/> |<span data-ttu-id="df051-129">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="df051-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="df051-130">必需</span><span class="sxs-lookup"><span data-stu-id="df051-130">required</span></span>  <br/> ||<span data-ttu-id="df051-131">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="df051-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

