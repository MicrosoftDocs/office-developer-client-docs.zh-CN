---
title: Issue_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d6768062-37aa-5658-f068-dae8d3a24717
ms.openlocfilehash: 1cdc38db93da57969230c280a2df24ac3b20ad0d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399695"
---
# <a name="issuetype-complextype-visio-xml"></a><span data-ttu-id="385e3-102">Issue_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="385e3-102">Issue_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="385e3-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="385e3-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="385e3-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="385e3-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="385e3-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="385e3-105">**Schema file**</span></span> <br/> |<span data-ttu-id="385e3-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="385e3-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="385e3-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="385e3-107">**Extension base**</span></span> <br/> |<span data-ttu-id="385e3-108">无</span><span class="sxs-lookup"><span data-stu-id="385e3-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="385e3-109">定义</span><span class="sxs-lookup"><span data-stu-id="385e3-109">Definition</span></span>

```XML
          <xs:complexType name="Issue_Type">
          
          <xs:sequence>
    <xs:element name="IssueTarget"  type="IssueTarget_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="RuleInfo"  type="RuleInfo_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="Ignored"
  type="xsd:boolean"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="385e3-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="385e3-110">Elements and attributes</span></span>

<span data-ttu-id="385e3-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="385e3-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="385e3-112">子元素</span><span class="sxs-lookup"><span data-stu-id="385e3-112">Child elements</span></span>

|<span data-ttu-id="385e3-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="385e3-113">**Element**</span></span>|<span data-ttu-id="385e3-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="385e3-114">**Type**</span></span>|<span data-ttu-id="385e3-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="385e3-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="385e3-116">IssueTarget</span><span class="sxs-lookup"><span data-stu-id="385e3-116">IssueTarget</span></span>](issuetarget-element-issue_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="385e3-117">IssueTarget_Type</span><span class="sxs-lookup"><span data-stu-id="385e3-117">IssueTarget_Type</span></span>](issuetarget_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="385e3-118">RuleInfo</span><span class="sxs-lookup"><span data-stu-id="385e3-118">RuleInfo</span></span>](ruleinfo-element-issue_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="385e3-119">RuleInfo_Type</span><span class="sxs-lookup"><span data-stu-id="385e3-119">RuleInfo_Type</span></span>](ruleinfo_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="385e3-120">Attributes</span><span class="sxs-lookup"><span data-stu-id="385e3-120">Attributes</span></span>

|<span data-ttu-id="385e3-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="385e3-121">**Attribute**</span></span>|<span data-ttu-id="385e3-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="385e3-122">**Type**</span></span>|<span data-ttu-id="385e3-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="385e3-123">**Required**</span></span>|<span data-ttu-id="385e3-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="385e3-124">**Description**</span></span>|<span data-ttu-id="385e3-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="385e3-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="385e3-126">ID</span><span class="sxs-lookup"><span data-stu-id="385e3-126">ID</span></span>  <br/> |<span data-ttu-id="385e3-127">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="385e3-127">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="385e3-128">必需</span><span class="sxs-lookup"><span data-stu-id="385e3-128">required</span></span>  <br/> ||<span data-ttu-id="385e3-129">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="385e3-129">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="385e3-130">忽略</span><span class="sxs-lookup"><span data-stu-id="385e3-130">Ignored</span></span>  <br/> |<span data-ttu-id="385e3-131">化</span><span class="sxs-lookup"><span data-stu-id="385e3-131">xsd:boolean</span></span>  <br/> |<span data-ttu-id="385e3-132">可选</span><span class="sxs-lookup"><span data-stu-id="385e3-132">optional</span></span>  <br/> ||<span data-ttu-id="385e3-133">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="385e3-133">Values of the xsd:boolean type.</span></span>  <br/> |
   

