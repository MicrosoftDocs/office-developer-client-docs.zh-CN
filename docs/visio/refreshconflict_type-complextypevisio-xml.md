---
title: RefreshConflict_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: aec7677f-a761-804c-6a12-731df86481a8
ms.openlocfilehash: 25c83a8168744820fa8b570dc37bda0547ab4ea0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346478"
---
# <a name="refreshconflicttype-complextype-visio-xml"></a><span data-ttu-id="9a7ff-102">RefreshConflict_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="9a7ff-102">RefreshConflict_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="9a7ff-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="9a7ff-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9a7ff-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9a7ff-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="9a7ff-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9a7ff-105">**Schema file**</span></span> <br/> |<span data-ttu-id="9a7ff-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="9a7ff-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="9a7ff-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="9a7ff-107">**Extension base**</span></span> <br/> |<span data-ttu-id="9a7ff-108">无</span><span class="sxs-lookup"><span data-stu-id="9a7ff-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9a7ff-109">定义</span><span class="sxs-lookup"><span data-stu-id="9a7ff-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="9a7ff-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9a7ff-110">Elements and attributes</span></span>

<span data-ttu-id="9a7ff-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="9a7ff-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="9a7ff-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9a7ff-112">Child elements</span></span>

<span data-ttu-id="9a7ff-113">无。</span><span class="sxs-lookup"><span data-stu-id="9a7ff-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="9a7ff-114">属性</span><span class="sxs-lookup"><span data-stu-id="9a7ff-114">Attributes</span></span>

|<span data-ttu-id="9a7ff-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="9a7ff-115">**Attribute**</span></span>|<span data-ttu-id="9a7ff-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="9a7ff-116">**Type**</span></span>|<span data-ttu-id="9a7ff-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="9a7ff-117">**Required**</span></span>|<span data-ttu-id="9a7ff-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="9a7ff-118">**Description**</span></span>|<span data-ttu-id="9a7ff-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9a7ff-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9a7ff-120">PageID</span><span class="sxs-lookup"><span data-stu-id="9a7ff-120">PageID</span></span>  <br/> |<span data-ttu-id="9a7ff-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9a7ff-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9a7ff-122">必需</span><span class="sxs-lookup"><span data-stu-id="9a7ff-122">required</span></span>  <br/> ||<span data-ttu-id="9a7ff-123">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9a7ff-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="9a7ff-124">RowID</span><span class="sxs-lookup"><span data-stu-id="9a7ff-124">RowID</span></span>  <br/> |<span data-ttu-id="9a7ff-125">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9a7ff-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9a7ff-126">必需</span><span class="sxs-lookup"><span data-stu-id="9a7ff-126">required</span></span>  <br/> ||<span data-ttu-id="9a7ff-127">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9a7ff-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="9a7ff-128">ShapeID</span><span class="sxs-lookup"><span data-stu-id="9a7ff-128">ShapeID</span></span>  <br/> |<span data-ttu-id="9a7ff-129">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9a7ff-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9a7ff-130">必需</span><span class="sxs-lookup"><span data-stu-id="9a7ff-130">required</span></span>  <br/> ||<span data-ttu-id="9a7ff-131">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9a7ff-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

