---
title: AutoLinkComparison_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 319b4bfb-a798-4f6c-52be-45708ac40869
ms.openlocfilehash: bb1b07a59fbe3fc706bc67db58e67c5b0ec14033
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779657"
---
# <a name="autolinkcomparisontype-complextype-visio-xml"></a><span data-ttu-id="1c269-102">AutoLinkComparison_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="1c269-102">AutoLinkComparison_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="1c269-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="1c269-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1c269-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1c269-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="1c269-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1c269-105">**Schema file**</span></span> <br/> |<span data-ttu-id="1c269-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="1c269-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="1c269-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="1c269-107">**Extension base**</span></span> <br/> |<span data-ttu-id="1c269-108">无</span><span class="sxs-lookup"><span data-stu-id="1c269-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1c269-109">定义</span><span class="sxs-lookup"><span data-stu-id="1c269-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="1c269-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1c269-110">Elements and attributes</span></span>

<span data-ttu-id="1c269-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="1c269-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="1c269-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1c269-112">Child elements</span></span>

<span data-ttu-id="1c269-113">无。</span><span class="sxs-lookup"><span data-stu-id="1c269-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="1c269-114">属性</span><span class="sxs-lookup"><span data-stu-id="1c269-114">Attributes</span></span>

|<span data-ttu-id="1c269-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="1c269-115">**Attribute**</span></span>|<span data-ttu-id="1c269-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="1c269-116">**Type**</span></span>|<span data-ttu-id="1c269-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="1c269-117">**Required**</span></span>|<span data-ttu-id="1c269-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="1c269-118">**Description**</span></span>|<span data-ttu-id="1c269-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1c269-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1c269-120">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1c269-120">ColumnName</span></span>  <br/> |<span data-ttu-id="1c269-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="1c269-121">xsd:string</span></span>  <br/> |<span data-ttu-id="1c269-122">必需</span><span class="sxs-lookup"><span data-stu-id="1c269-122">required</span></span>  <br/> ||<span data-ttu-id="1c269-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1c269-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="1c269-124">ContextType</span><span class="sxs-lookup"><span data-stu-id="1c269-124">ContextType</span></span>  <br/> |<span data-ttu-id="1c269-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="1c269-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="1c269-126">必需</span><span class="sxs-lookup"><span data-stu-id="1c269-126">required</span></span>  <br/> ||<span data-ttu-id="1c269-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1c269-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="1c269-128">ContextTypeLabel</span><span class="sxs-lookup"><span data-stu-id="1c269-128">ContextTypeLabel</span></span>  <br/> |<span data-ttu-id="1c269-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="1c269-129">xsd:string</span></span>  <br/> |<span data-ttu-id="1c269-130">可选</span><span class="sxs-lookup"><span data-stu-id="1c269-130">optional</span></span>  <br/> ||<span data-ttu-id="1c269-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1c269-131">Values of the xsd:string type.</span></span>  <br/> |
   

