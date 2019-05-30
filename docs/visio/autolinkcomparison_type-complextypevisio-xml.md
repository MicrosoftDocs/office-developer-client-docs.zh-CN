---
title: AutoLinkComparison_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 319b4bfb-a798-4f6c-52be-45708ac40869
ms.openlocfilehash: eeb58a0e2f401c0e8a2bcf67147bc300bb8535ff
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537883"
---
# <a name="autolinkcomparisontype-complextype-visio-xml"></a><span data-ttu-id="fe834-102">AutoLinkComparison_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="fe834-102">AutoLinkComparison_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="fe834-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="fe834-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fe834-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="fe834-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="fe834-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="fe834-105">**Schema file**</span></span> <br/> |<span data-ttu-id="fe834-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="fe834-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="fe834-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="fe834-107">**Extension base**</span></span> <br/> |<span data-ttu-id="fe834-108">无</span><span class="sxs-lookup"><span data-stu-id="fe834-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="fe834-109">定义</span><span class="sxs-lookup"><span data-stu-id="fe834-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="fe834-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="fe834-110">Elements and attributes</span></span>

<span data-ttu-id="fe834-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="fe834-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="fe834-112">子元素</span><span class="sxs-lookup"><span data-stu-id="fe834-112">Child elements</span></span>

<span data-ttu-id="fe834-113">无。</span><span class="sxs-lookup"><span data-stu-id="fe834-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="fe834-114">属性</span><span class="sxs-lookup"><span data-stu-id="fe834-114">Attributes</span></span>

|<span data-ttu-id="fe834-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="fe834-115">**Attribute**</span></span>|<span data-ttu-id="fe834-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="fe834-116">**Type**</span></span>|<span data-ttu-id="fe834-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="fe834-117">**Required**</span></span>|<span data-ttu-id="fe834-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="fe834-118">**Description**</span></span>|<span data-ttu-id="fe834-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="fe834-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fe834-120">ColumnName</span><span class="sxs-lookup"><span data-stu-id="fe834-120">ColumnName</span></span>  <br/> |<span data-ttu-id="fe834-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="fe834-121">xsd:string</span></span>  <br/> |<span data-ttu-id="fe834-122">必需</span><span class="sxs-lookup"><span data-stu-id="fe834-122">required</span></span>  <br/> ||<span data-ttu-id="fe834-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fe834-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="fe834-124">ContextType</span><span class="sxs-lookup"><span data-stu-id="fe834-124">ContextType</span></span>  <br/> |<span data-ttu-id="fe834-125">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="fe834-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="fe834-126">必需</span><span class="sxs-lookup"><span data-stu-id="fe834-126">required</span></span>  <br/> ||<span data-ttu-id="fe834-127">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fe834-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="fe834-128">ContextTypeLabel</span><span class="sxs-lookup"><span data-stu-id="fe834-128">ContextTypeLabel</span></span>  <br/> |<span data-ttu-id="fe834-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="fe834-129">xsd:string</span></span>  <br/> |<span data-ttu-id="fe834-130">可选</span><span class="sxs-lookup"><span data-stu-id="fe834-130">optional</span></span>  <br/> ||<span data-ttu-id="fe834-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fe834-131">Values of the xsd:string type.</span></span>  <br/> |
   

