---
title: RowMap_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2abe0572-53bb-20fc-333f-2b69b07e99be
ms.openlocfilehash: bdc76f35cf2824d5159e945bce7e9dd2a8abe2bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355732"
---
# <a name="rowmaptype-complextype-visio-xml"></a><span data-ttu-id="86bca-102">RowMap_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="86bca-102">RowMap_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="86bca-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="86bca-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="86bca-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="86bca-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="86bca-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="86bca-105">**Schema file**</span></span> <br/> |<span data-ttu-id="86bca-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="86bca-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="86bca-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="86bca-107">**Extension base**</span></span> <br/> |<span data-ttu-id="86bca-108">无</span><span class="sxs-lookup"><span data-stu-id="86bca-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="86bca-109">定义</span><span class="sxs-lookup"><span data-stu-id="86bca-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="86bca-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="86bca-110">Elements and attributes</span></span>

<span data-ttu-id="86bca-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="86bca-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="86bca-112">子元素</span><span class="sxs-lookup"><span data-stu-id="86bca-112">Child elements</span></span>

<span data-ttu-id="86bca-113">无。</span><span class="sxs-lookup"><span data-stu-id="86bca-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="86bca-114">属性</span><span class="sxs-lookup"><span data-stu-id="86bca-114">Attributes</span></span>

|<span data-ttu-id="86bca-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="86bca-115">**Attribute**</span></span>|<span data-ttu-id="86bca-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="86bca-116">**Type**</span></span>|<span data-ttu-id="86bca-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="86bca-117">**Required**</span></span>|<span data-ttu-id="86bca-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="86bca-118">**Description**</span></span>|<span data-ttu-id="86bca-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="86bca-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="86bca-120">PageID</span><span class="sxs-lookup"><span data-stu-id="86bca-120">PageID</span></span>  <br/> |<span data-ttu-id="86bca-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="86bca-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="86bca-122">必需</span><span class="sxs-lookup"><span data-stu-id="86bca-122">required</span></span>  <br/> ||<span data-ttu-id="86bca-123">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="86bca-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="86bca-124">RowID</span><span class="sxs-lookup"><span data-stu-id="86bca-124">RowID</span></span>  <br/> |<span data-ttu-id="86bca-125">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="86bca-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="86bca-126">必需</span><span class="sxs-lookup"><span data-stu-id="86bca-126">required</span></span>  <br/> ||<span data-ttu-id="86bca-127">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="86bca-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="86bca-128">ShapeID</span><span class="sxs-lookup"><span data-stu-id="86bca-128">ShapeID</span></span>  <br/> |<span data-ttu-id="86bca-129">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="86bca-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="86bca-130">必需</span><span class="sxs-lookup"><span data-stu-id="86bca-130">required</span></span>  <br/> ||<span data-ttu-id="86bca-131">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="86bca-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

