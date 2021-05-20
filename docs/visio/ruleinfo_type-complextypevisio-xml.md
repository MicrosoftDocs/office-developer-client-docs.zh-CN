---
title: 'RuleInfo_Type XML (Visio complexType) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9ec3a334-dd0e-acc1-2b4e-026568b6f265
ms.openlocfilehash: 8e7b04e938997786cf0dc99e92057f77cfe0cf76
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541643"
---
# <a name="ruleinfo_type-complextype-visio-xml"></a><span data-ttu-id="deecf-102">RuleInfo_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="deecf-102">RuleInfo_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="deecf-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="deecf-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="deecf-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="deecf-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="deecf-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="deecf-105">**Schema file**</span></span> <br/> |<span data-ttu-id="deecf-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="deecf-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="deecf-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="deecf-107">**Extension base**</span></span> <br/> |<span data-ttu-id="deecf-108">无</span><span class="sxs-lookup"><span data-stu-id="deecf-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="deecf-109">定义</span><span class="sxs-lookup"><span data-stu-id="deecf-109">Definition</span></span>

```XML
      <xs:complexType name="RuleInfo_Type">
    <xs:attribute name="RuleSetID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="RuleID"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="deecf-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="deecf-110">Elements and attributes</span></span>

<span data-ttu-id="deecf-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="deecf-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="deecf-112">子元素</span><span class="sxs-lookup"><span data-stu-id="deecf-112">Child elements</span></span>

<span data-ttu-id="deecf-113">无。</span><span class="sxs-lookup"><span data-stu-id="deecf-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="deecf-114">属性</span><span class="sxs-lookup"><span data-stu-id="deecf-114">Attributes</span></span>

|<span data-ttu-id="deecf-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="deecf-115">**Attribute**</span></span>|<span data-ttu-id="deecf-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="deecf-116">**Type**</span></span>|<span data-ttu-id="deecf-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="deecf-117">**Required**</span></span>|<span data-ttu-id="deecf-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="deecf-118">**Description**</span></span>|<span data-ttu-id="deecf-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="deecf-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="deecf-120">RuleID</span><span class="sxs-lookup"><span data-stu-id="deecf-120">RuleID</span></span>  <br/> |<span data-ttu-id="deecf-121">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="deecf-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="deecf-122">必需</span><span class="sxs-lookup"><span data-stu-id="deecf-122">required</span></span>  <br/> ||<span data-ttu-id="deecf-123">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="deecf-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="deecf-124">RuleSetID</span><span class="sxs-lookup"><span data-stu-id="deecf-124">RuleSetID</span></span>  <br/> |<span data-ttu-id="deecf-125">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="deecf-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="deecf-126">必需</span><span class="sxs-lookup"><span data-stu-id="deecf-126">required</span></span>  <br/> ||<span data-ttu-id="deecf-127">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="deecf-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

