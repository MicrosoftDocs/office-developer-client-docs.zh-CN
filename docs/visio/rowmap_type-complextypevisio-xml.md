---
title: 'RowMap_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2abe0572-53bb-20fc-333f-2b69b07e99be
ms.openlocfilehash: 8564f5a063ac2365de50919168df0b84e8ae100a
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538772"
---
# <a name="rowmap_type-complextype-visio-xml"></a><span data-ttu-id="02308-102">RowMap_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="02308-102">RowMap_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="02308-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="02308-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="02308-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="02308-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="02308-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="02308-105">**Schema file**</span></span> <br/> |<span data-ttu-id="02308-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="02308-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="02308-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="02308-107">**Extension base**</span></span> <br/> |<span data-ttu-id="02308-108">无</span><span class="sxs-lookup"><span data-stu-id="02308-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="02308-109">定义</span><span class="sxs-lookup"><span data-stu-id="02308-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="02308-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="02308-110">Elements and attributes</span></span>

<span data-ttu-id="02308-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="02308-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="02308-112">子元素</span><span class="sxs-lookup"><span data-stu-id="02308-112">Child elements</span></span>

<span data-ttu-id="02308-113">无。</span><span class="sxs-lookup"><span data-stu-id="02308-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="02308-114">属性</span><span class="sxs-lookup"><span data-stu-id="02308-114">Attributes</span></span>

|<span data-ttu-id="02308-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="02308-115">**Attribute**</span></span>|<span data-ttu-id="02308-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="02308-116">**Type**</span></span>|<span data-ttu-id="02308-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="02308-117">**Required**</span></span>|<span data-ttu-id="02308-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="02308-118">**Description**</span></span>|<span data-ttu-id="02308-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="02308-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="02308-120">PageID</span><span class="sxs-lookup"><span data-stu-id="02308-120">PageID</span></span>  <br/> |<span data-ttu-id="02308-121">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="02308-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="02308-122">必需</span><span class="sxs-lookup"><span data-stu-id="02308-122">required</span></span>  <br/> ||<span data-ttu-id="02308-123">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="02308-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="02308-124">RowID</span><span class="sxs-lookup"><span data-stu-id="02308-124">RowID</span></span>  <br/> |<span data-ttu-id="02308-125">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="02308-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="02308-126">必需</span><span class="sxs-lookup"><span data-stu-id="02308-126">required</span></span>  <br/> ||<span data-ttu-id="02308-127">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="02308-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="02308-128">ShapeID</span><span class="sxs-lookup"><span data-stu-id="02308-128">ShapeID</span></span>  <br/> |<span data-ttu-id="02308-129">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="02308-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="02308-130">必需</span><span class="sxs-lookup"><span data-stu-id="02308-130">required</span></span>  <br/> ||<span data-ttu-id="02308-131">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="02308-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

