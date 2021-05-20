---
title: 'AutoLinkComparison_Type COMPLEXType (Visio XML) '
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
# <a name="autolinkcomparison_type-complextype-visio-xml"></a><span data-ttu-id="78584-102">AutoLinkComparison_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="78584-102">AutoLinkComparison_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="78584-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="78584-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="78584-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="78584-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="78584-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="78584-105">**Schema file**</span></span> <br/> |<span data-ttu-id="78584-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="78584-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="78584-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="78584-107">**Extension base**</span></span> <br/> |<span data-ttu-id="78584-108">无</span><span class="sxs-lookup"><span data-stu-id="78584-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="78584-109">定义</span><span class="sxs-lookup"><span data-stu-id="78584-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="78584-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="78584-110">Elements and attributes</span></span>

<span data-ttu-id="78584-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="78584-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="78584-112">子元素</span><span class="sxs-lookup"><span data-stu-id="78584-112">Child elements</span></span>

<span data-ttu-id="78584-113">无。</span><span class="sxs-lookup"><span data-stu-id="78584-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="78584-114">属性</span><span class="sxs-lookup"><span data-stu-id="78584-114">Attributes</span></span>

|<span data-ttu-id="78584-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="78584-115">**Attribute**</span></span>|<span data-ttu-id="78584-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="78584-116">**Type**</span></span>|<span data-ttu-id="78584-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="78584-117">**Required**</span></span>|<span data-ttu-id="78584-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="78584-118">**Description**</span></span>|<span data-ttu-id="78584-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="78584-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="78584-120">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78584-120">ColumnName</span></span>  <br/> |<span data-ttu-id="78584-121">xsd：string</span><span class="sxs-lookup"><span data-stu-id="78584-121">xsd:string</span></span>  <br/> |<span data-ttu-id="78584-122">必需</span><span class="sxs-lookup"><span data-stu-id="78584-122">required</span></span>  <br/> ||<span data-ttu-id="78584-123">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="78584-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="78584-124">ContextType</span><span class="sxs-lookup"><span data-stu-id="78584-124">ContextType</span></span>  <br/> |<span data-ttu-id="78584-125">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="78584-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="78584-126">必需</span><span class="sxs-lookup"><span data-stu-id="78584-126">required</span></span>  <br/> ||<span data-ttu-id="78584-127">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="78584-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="78584-128">ContextTypeLabel</span><span class="sxs-lookup"><span data-stu-id="78584-128">ContextTypeLabel</span></span>  <br/> |<span data-ttu-id="78584-129">xsd：string</span><span class="sxs-lookup"><span data-stu-id="78584-129">xsd:string</span></span>  <br/> |<span data-ttu-id="78584-130">可选</span><span class="sxs-lookup"><span data-stu-id="78584-130">optional</span></span>  <br/> ||<span data-ttu-id="78584-131">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="78584-131">Values of the xsd:string type.</span></span>  <br/> |
   

