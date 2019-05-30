---
title: RuleInfo_Type 复杂类型 (Visio XML)
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
# <a name="ruleinfotype-complextype-visio-xml"></a><span data-ttu-id="3b6aa-102">RuleInfo_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="3b6aa-102">RuleInfo_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="3b6aa-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="3b6aa-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3b6aa-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3b6aa-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="3b6aa-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3b6aa-105">**Schema file**</span></span> <br/> |<span data-ttu-id="3b6aa-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="3b6aa-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="3b6aa-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="3b6aa-107">**Extension base**</span></span> <br/> |<span data-ttu-id="3b6aa-108">无</span><span class="sxs-lookup"><span data-stu-id="3b6aa-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3b6aa-109">定义</span><span class="sxs-lookup"><span data-stu-id="3b6aa-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="3b6aa-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3b6aa-110">Elements and attributes</span></span>

<span data-ttu-id="3b6aa-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="3b6aa-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="3b6aa-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3b6aa-112">Child elements</span></span>

<span data-ttu-id="3b6aa-113">无。</span><span class="sxs-lookup"><span data-stu-id="3b6aa-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="3b6aa-114">属性</span><span class="sxs-lookup"><span data-stu-id="3b6aa-114">Attributes</span></span>

|<span data-ttu-id="3b6aa-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="3b6aa-115">**Attribute**</span></span>|<span data-ttu-id="3b6aa-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="3b6aa-116">**Type**</span></span>|<span data-ttu-id="3b6aa-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="3b6aa-117">**Required**</span></span>|<span data-ttu-id="3b6aa-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="3b6aa-118">**Description**</span></span>|<span data-ttu-id="3b6aa-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="3b6aa-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b6aa-120">RuleID</span><span class="sxs-lookup"><span data-stu-id="3b6aa-120">RuleID</span></span>  <br/> |<span data-ttu-id="3b6aa-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="3b6aa-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="3b6aa-122">必需</span><span class="sxs-lookup"><span data-stu-id="3b6aa-122">required</span></span>  <br/> ||<span data-ttu-id="3b6aa-123">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3b6aa-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="3b6aa-124">RuleSetID</span><span class="sxs-lookup"><span data-stu-id="3b6aa-124">RuleSetID</span></span>  <br/> |<span data-ttu-id="3b6aa-125">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="3b6aa-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="3b6aa-126">必需</span><span class="sxs-lookup"><span data-stu-id="3b6aa-126">required</span></span>  <br/> ||<span data-ttu-id="3b6aa-127">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3b6aa-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

