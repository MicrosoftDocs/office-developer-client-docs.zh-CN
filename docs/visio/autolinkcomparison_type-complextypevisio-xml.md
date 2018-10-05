---
title: AutoLinkComparison_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 319b4bfb-a798-4f6c-52be-45708ac40869
ms.openlocfilehash: 235b63777d21955a2f2062757d6a54e899b169ac
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389748"
---
# <a name="autolinkcomparisontype-complextype-visio-xml"></a><span data-ttu-id="5a64c-102">AutoLinkComparison_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="5a64c-102">AutoLinkComparison_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="5a64c-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="5a64c-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5a64c-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5a64c-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="5a64c-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5a64c-105">**Schema file**</span></span> <br/> |<span data-ttu-id="5a64c-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="5a64c-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="5a64c-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="5a64c-107">**Extension base**</span></span> <br/> |<span data-ttu-id="5a64c-108">无</span><span class="sxs-lookup"><span data-stu-id="5a64c-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5a64c-109">定义</span><span class="sxs-lookup"><span data-stu-id="5a64c-109">Definition</span></span>

```XML
      <xs:complexType name="AutoLinkComparison_Type">
    <xs:attribute name="ColumnName"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="ContextType"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="ContextTypeLabel"
  type="xsd:string"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="5a64c-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5a64c-110">Elements and attributes</span></span>

<span data-ttu-id="5a64c-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="5a64c-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="5a64c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5a64c-112">Child elements</span></span>

<span data-ttu-id="5a64c-113">无。</span><span class="sxs-lookup"><span data-stu-id="5a64c-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="5a64c-114">属性</span><span class="sxs-lookup"><span data-stu-id="5a64c-114">Attributes</span></span>

|<span data-ttu-id="5a64c-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="5a64c-115">**Attribute**</span></span>|<span data-ttu-id="5a64c-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="5a64c-116">**Type**</span></span>|<span data-ttu-id="5a64c-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="5a64c-117">**Required**</span></span>|<span data-ttu-id="5a64c-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="5a64c-118">**Description**</span></span>|<span data-ttu-id="5a64c-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="5a64c-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5a64c-120">ColumnName</span><span class="sxs-lookup"><span data-stu-id="5a64c-120">ColumnName</span></span>  <br/> |<span data-ttu-id="5a64c-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5a64c-121">xsd:string</span></span>  <br/> |<span data-ttu-id="5a64c-122">必需</span><span class="sxs-lookup"><span data-stu-id="5a64c-122">required</span></span>  <br/> ||<span data-ttu-id="5a64c-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5a64c-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="5a64c-124">ContextType</span><span class="sxs-lookup"><span data-stu-id="5a64c-124">ContextType</span></span>  <br/> |<span data-ttu-id="5a64c-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5a64c-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5a64c-126">必需</span><span class="sxs-lookup"><span data-stu-id="5a64c-126">required</span></span>  <br/> ||<span data-ttu-id="5a64c-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5a64c-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5a64c-128">ContextTypeLabel</span><span class="sxs-lookup"><span data-stu-id="5a64c-128">ContextTypeLabel</span></span>  <br/> |<span data-ttu-id="5a64c-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5a64c-129">xsd:string</span></span>  <br/> |<span data-ttu-id="5a64c-130">可选</span><span class="sxs-lookup"><span data-stu-id="5a64c-130">optional</span></span>  <br/> ||<span data-ttu-id="5a64c-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5a64c-131">Values of the xsd:string type.</span></span>  <br/> |
   

