---
title: RowKeyValue_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e4c971f4-e3e3-11be-6b3f-45565e56cb23
ms.openlocfilehash: dcd4c972aac1e86fa7a66766a756ebef2cca7c02
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781171"
---
# <a name="rowkeyvaluetype-complextype-visio-xml"></a><span data-ttu-id="c7ab1-102">RowKeyValue_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="c7ab1-102">RowKeyValue_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="c7ab1-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="c7ab1-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c7ab1-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c7ab1-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="c7ab1-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c7ab1-105">**Schema file**</span></span> <br/> |<span data-ttu-id="c7ab1-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="c7ab1-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="c7ab1-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="c7ab1-107">**Extension base**</span></span> <br/> |<span data-ttu-id="c7ab1-108">无</span><span class="sxs-lookup"><span data-stu-id="c7ab1-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c7ab1-109">定义</span><span class="sxs-lookup"><span data-stu-id="c7ab1-109">Definition</span></span>

```XML
      <xs:complexType name="RowKeyValue_Type">
    <xs:attribute name="RowID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="Value"
  type="xsd:string"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c7ab1-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c7ab1-110">Elements and attributes</span></span>

<span data-ttu-id="c7ab1-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="c7ab1-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="c7ab1-112">子元素</span><span class="sxs-lookup"><span data-stu-id="c7ab1-112">Child elements</span></span>

<span data-ttu-id="c7ab1-113">无。</span><span class="sxs-lookup"><span data-stu-id="c7ab1-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="c7ab1-114">属性</span><span class="sxs-lookup"><span data-stu-id="c7ab1-114">Attributes</span></span>

|<span data-ttu-id="c7ab1-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="c7ab1-115">**Attribute**</span></span>|<span data-ttu-id="c7ab1-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="c7ab1-116">**Type**</span></span>|<span data-ttu-id="c7ab1-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="c7ab1-117">**Required**</span></span>|<span data-ttu-id="c7ab1-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="c7ab1-118">**Description**</span></span>|<span data-ttu-id="c7ab1-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c7ab1-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c7ab1-120">RowID</span><span class="sxs-lookup"><span data-stu-id="c7ab1-120">RowID</span></span>  <br/> |<span data-ttu-id="c7ab1-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="c7ab1-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="c7ab1-122">必需</span><span class="sxs-lookup"><span data-stu-id="c7ab1-122">required</span></span>  <br/> ||<span data-ttu-id="c7ab1-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c7ab1-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="c7ab1-124">值</span><span class="sxs-lookup"><span data-stu-id="c7ab1-124">Value</span></span>  <br/> |<span data-ttu-id="c7ab1-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c7ab1-125">xsd:string</span></span>  <br/> |<span data-ttu-id="c7ab1-126">必需</span><span class="sxs-lookup"><span data-stu-id="c7ab1-126">required</span></span>  <br/> ||<span data-ttu-id="c7ab1-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c7ab1-127">Values of the xsd:string type.</span></span>  <br/> |
   

