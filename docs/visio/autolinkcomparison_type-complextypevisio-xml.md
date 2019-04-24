---
title: AutoLinkComparison_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 319b4bfb-a798-4f6c-52be-45708ac40869
ms.openlocfilehash: 235b63777d21955a2f2062757d6a54e899b169ac
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338596"
---
# <a name="autolinkcomparisontype-complextype-visio-xml"></a><span data-ttu-id="ebde5-102">AutoLinkComparison_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="ebde5-102">AutoLinkComparison_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="ebde5-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="ebde5-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ebde5-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ebde5-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="ebde5-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ebde5-105">**Schema file**</span></span> <br/> |<span data-ttu-id="ebde5-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="ebde5-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="ebde5-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="ebde5-107">**Extension base**</span></span> <br/> |<span data-ttu-id="ebde5-108">无</span><span class="sxs-lookup"><span data-stu-id="ebde5-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ebde5-109">定义</span><span class="sxs-lookup"><span data-stu-id="ebde5-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="ebde5-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ebde5-110">Elements and attributes</span></span>

<span data-ttu-id="ebde5-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="ebde5-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="ebde5-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ebde5-112">Child elements</span></span>

<span data-ttu-id="ebde5-113">无。</span><span class="sxs-lookup"><span data-stu-id="ebde5-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="ebde5-114">属性</span><span class="sxs-lookup"><span data-stu-id="ebde5-114">Attributes</span></span>

|<span data-ttu-id="ebde5-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="ebde5-115">**Attribute**</span></span>|<span data-ttu-id="ebde5-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="ebde5-116">**Type**</span></span>|<span data-ttu-id="ebde5-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="ebde5-117">**Required**</span></span>|<span data-ttu-id="ebde5-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="ebde5-118">**Description**</span></span>|<span data-ttu-id="ebde5-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="ebde5-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ebde5-120">ColumnName</span><span class="sxs-lookup"><span data-stu-id="ebde5-120">ColumnName</span></span>  <br/> |<span data-ttu-id="ebde5-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ebde5-121">xsd:string</span></span>  <br/> |<span data-ttu-id="ebde5-122">必需</span><span class="sxs-lookup"><span data-stu-id="ebde5-122">required</span></span>  <br/> ||<span data-ttu-id="ebde5-123">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ebde5-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="ebde5-124">ContextType</span><span class="sxs-lookup"><span data-stu-id="ebde5-124">ContextType</span></span>  <br/> |<span data-ttu-id="ebde5-125">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ebde5-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ebde5-126">必需</span><span class="sxs-lookup"><span data-stu-id="ebde5-126">required</span></span>  <br/> ||<span data-ttu-id="ebde5-127">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ebde5-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="ebde5-128">ContextTypeLabel</span><span class="sxs-lookup"><span data-stu-id="ebde5-128">ContextTypeLabel</span></span>  <br/> |<span data-ttu-id="ebde5-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ebde5-129">xsd:string</span></span>  <br/> |<span data-ttu-id="ebde5-130">可选</span><span class="sxs-lookup"><span data-stu-id="ebde5-130">optional</span></span>  <br/> ||<span data-ttu-id="ebde5-131">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ebde5-131">Values of the xsd:string type.</span></span>  <br/> |
   

