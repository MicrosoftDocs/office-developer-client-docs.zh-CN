---
title: 'RefBy_Type XML (Visio complexType) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e2990281-6410-5a35-2b28-3a8b33246c73
ms.openlocfilehash: 7970ae735f4933f05e71f1758912d3ecd382bf89
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538275"
---
# <a name="refby_type-complextype-visio-xml"></a><span data-ttu-id="e0cc9-102">RefBy_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="e0cc9-102">RefBy_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="e0cc9-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="e0cc9-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e0cc9-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e0cc9-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="e0cc9-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e0cc9-105">**Schema file**</span></span> <br/> |<span data-ttu-id="e0cc9-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="e0cc9-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="e0cc9-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="e0cc9-107">**Extension base**</span></span> <br/> |<span data-ttu-id="e0cc9-108">无</span><span class="sxs-lookup"><span data-stu-id="e0cc9-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e0cc9-109">定义</span><span class="sxs-lookup"><span data-stu-id="e0cc9-109">Definition</span></span>

```XML
      <xs:complexType name="RefBy_Type">
    <xs:attribute name="T"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e0cc9-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e0cc9-110">Elements and attributes</span></span>

<span data-ttu-id="e0cc9-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="e0cc9-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="e0cc9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e0cc9-112">Child elements</span></span>

<span data-ttu-id="e0cc9-113">无。</span><span class="sxs-lookup"><span data-stu-id="e0cc9-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="e0cc9-114">属性</span><span class="sxs-lookup"><span data-stu-id="e0cc9-114">Attributes</span></span>

|<span data-ttu-id="e0cc9-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="e0cc9-115">**Attribute**</span></span>|<span data-ttu-id="e0cc9-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="e0cc9-116">**Type**</span></span>|<span data-ttu-id="e0cc9-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="e0cc9-117">**Required**</span></span>|<span data-ttu-id="e0cc9-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="e0cc9-118">**Description**</span></span>|<span data-ttu-id="e0cc9-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e0cc9-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0cc9-120">ID</span><span class="sxs-lookup"><span data-stu-id="e0cc9-120">ID</span></span>  <br/> |<span data-ttu-id="e0cc9-121">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e0cc9-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e0cc9-122">必需</span><span class="sxs-lookup"><span data-stu-id="e0cc9-122">required</span></span>  <br/> ||<span data-ttu-id="e0cc9-123">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0cc9-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="e0cc9-124">T</span><span class="sxs-lookup"><span data-stu-id="e0cc9-124">T</span></span>  <br/> |<span data-ttu-id="e0cc9-125">xsd：string</span><span class="sxs-lookup"><span data-stu-id="e0cc9-125">xsd:string</span></span>  <br/> |<span data-ttu-id="e0cc9-126">必需</span><span class="sxs-lookup"><span data-stu-id="e0cc9-126">required</span></span>  <br/> ||<span data-ttu-id="e0cc9-127">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0cc9-127">Values of the xsd:string type.</span></span>  <br/> |
   

