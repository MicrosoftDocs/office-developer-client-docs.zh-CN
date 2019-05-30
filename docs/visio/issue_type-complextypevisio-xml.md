---
title: Issue_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d6768062-37aa-5658-f068-dae8d3a24717
ms.openlocfilehash: b351554fe7919cada99172f721f5dbe2fd8f243a
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542959"
---
# <a name="issuetype-complextype-visio-xml"></a><span data-ttu-id="18b03-102">Issue_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="18b03-102">Issue_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="18b03-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="18b03-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="18b03-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="18b03-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="18b03-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="18b03-105">**Schema file**</span></span> <br/> |<span data-ttu-id="18b03-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="18b03-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="18b03-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="18b03-107">**Extension base**</span></span> <br/> |<span data-ttu-id="18b03-108">无</span><span class="sxs-lookup"><span data-stu-id="18b03-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="18b03-109">定义</span><span class="sxs-lookup"><span data-stu-id="18b03-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="18b03-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="18b03-110">Elements and attributes</span></span>

<span data-ttu-id="18b03-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="18b03-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="18b03-112">子元素</span><span class="sxs-lookup"><span data-stu-id="18b03-112">Child elements</span></span>

|<span data-ttu-id="18b03-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="18b03-113">**Element**</span></span>|<span data-ttu-id="18b03-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="18b03-114">**Type**</span></span>|<span data-ttu-id="18b03-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="18b03-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="18b03-116">IssueTarget</span><span class="sxs-lookup"><span data-stu-id="18b03-116">IssueTarget</span></span>](issuetarget-element-issue_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="18b03-117">IssueTarget_Type</span><span class="sxs-lookup"><span data-stu-id="18b03-117">IssueTarget_Type</span></span>](issuetarget_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="18b03-118">RuleInfo</span><span class="sxs-lookup"><span data-stu-id="18b03-118">RuleInfo</span></span>](ruleinfo-element-issue_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="18b03-119">RuleInfo_Type</span><span class="sxs-lookup"><span data-stu-id="18b03-119">RuleInfo_Type</span></span>](ruleinfo_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="18b03-120">属性</span><span class="sxs-lookup"><span data-stu-id="18b03-120">Attributes</span></span>

|<span data-ttu-id="18b03-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="18b03-121">**Attribute**</span></span>|<span data-ttu-id="18b03-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="18b03-122">**Type**</span></span>|<span data-ttu-id="18b03-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="18b03-123">**Required**</span></span>|<span data-ttu-id="18b03-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="18b03-124">**Description**</span></span>|<span data-ttu-id="18b03-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="18b03-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="18b03-126">ID</span><span class="sxs-lookup"><span data-stu-id="18b03-126">ID</span></span>  <br/> |<span data-ttu-id="18b03-127">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="18b03-127">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="18b03-128">必需</span><span class="sxs-lookup"><span data-stu-id="18b03-128">required</span></span>  <br/> ||<span data-ttu-id="18b03-129">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="18b03-129">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="18b03-130">Ignored</span><span class="sxs-lookup"><span data-stu-id="18b03-130">Ignored</span></span>  <br/> |<span data-ttu-id="18b03-131">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="18b03-131">xsd:boolean</span></span>  <br/> |<span data-ttu-id="18b03-132">可选</span><span class="sxs-lookup"><span data-stu-id="18b03-132">optional</span></span>  <br/> ||<span data-ttu-id="18b03-133">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="18b03-133">Values of the xsd:boolean type.</span></span>  <br/> |
   

