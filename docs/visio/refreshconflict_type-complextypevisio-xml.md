---
title: RefreshConflict_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: aec7677f-a761-804c-6a12-731df86481a8
ms.openlocfilehash: 7b52bc87af213e9c26f4bc359adf6cf900b34957
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542826"
---
# <a name="refreshconflicttype-complextype-visio-xml"></a><span data-ttu-id="4905f-102">RefreshConflict_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="4905f-102">RefreshConflict_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="4905f-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="4905f-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4905f-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4905f-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="4905f-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4905f-105">**Schema file**</span></span> <br/> |<span data-ttu-id="4905f-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="4905f-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="4905f-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="4905f-107">**Extension base**</span></span> <br/> |<span data-ttu-id="4905f-108">无</span><span class="sxs-lookup"><span data-stu-id="4905f-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4905f-109">定义</span><span class="sxs-lookup"><span data-stu-id="4905f-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="4905f-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4905f-110">Elements and attributes</span></span>

<span data-ttu-id="4905f-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="4905f-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="4905f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4905f-112">Child elements</span></span>

<span data-ttu-id="4905f-113">无。</span><span class="sxs-lookup"><span data-stu-id="4905f-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="4905f-114">属性</span><span class="sxs-lookup"><span data-stu-id="4905f-114">Attributes</span></span>

|<span data-ttu-id="4905f-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="4905f-115">**Attribute**</span></span>|<span data-ttu-id="4905f-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="4905f-116">**Type**</span></span>|<span data-ttu-id="4905f-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="4905f-117">**Required**</span></span>|<span data-ttu-id="4905f-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="4905f-118">**Description**</span></span>|<span data-ttu-id="4905f-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4905f-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4905f-120">PageID</span><span class="sxs-lookup"><span data-stu-id="4905f-120">PageID</span></span>  <br/> |<span data-ttu-id="4905f-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4905f-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4905f-122">必需</span><span class="sxs-lookup"><span data-stu-id="4905f-122">required</span></span>  <br/> ||<span data-ttu-id="4905f-123">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4905f-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4905f-124">RowID</span><span class="sxs-lookup"><span data-stu-id="4905f-124">RowID</span></span>  <br/> |<span data-ttu-id="4905f-125">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4905f-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4905f-126">必需</span><span class="sxs-lookup"><span data-stu-id="4905f-126">required</span></span>  <br/> ||<span data-ttu-id="4905f-127">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4905f-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4905f-128">ShapeID</span><span class="sxs-lookup"><span data-stu-id="4905f-128">ShapeID</span></span>  <br/> |<span data-ttu-id="4905f-129">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4905f-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4905f-130">必需</span><span class="sxs-lookup"><span data-stu-id="4905f-130">required</span></span>  <br/> ||<span data-ttu-id="4905f-131">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4905f-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

