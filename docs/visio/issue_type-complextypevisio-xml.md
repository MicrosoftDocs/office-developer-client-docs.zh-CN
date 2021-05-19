---
title: 'Issue_Type COMPLEXType (Visio XML) '
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
# <a name="issue_type-complextype-visio-xml"></a><span data-ttu-id="f65be-102">Issue_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="f65be-102">Issue_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="f65be-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="f65be-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f65be-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f65be-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="f65be-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f65be-105">**Schema file**</span></span> <br/> |<span data-ttu-id="f65be-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="f65be-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="f65be-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="f65be-107">**Extension base**</span></span> <br/> |<span data-ttu-id="f65be-108">无</span><span class="sxs-lookup"><span data-stu-id="f65be-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f65be-109">定义</span><span class="sxs-lookup"><span data-stu-id="f65be-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="f65be-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f65be-110">Elements and attributes</span></span>

<span data-ttu-id="f65be-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f65be-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="f65be-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f65be-112">Child elements</span></span>

|<span data-ttu-id="f65be-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="f65be-113">**Element**</span></span>|<span data-ttu-id="f65be-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="f65be-114">**Type**</span></span>|<span data-ttu-id="f65be-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="f65be-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f65be-116">IssueTarget</span><span class="sxs-lookup"><span data-stu-id="f65be-116">IssueTarget</span></span>](issuetarget-element-issue_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f65be-117">IssueTarget_Type</span><span class="sxs-lookup"><span data-stu-id="f65be-117">IssueTarget_Type</span></span>](issuetarget_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="f65be-118">RuleInfo</span><span class="sxs-lookup"><span data-stu-id="f65be-118">RuleInfo</span></span>](ruleinfo-element-issue_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f65be-119">RuleInfo_Type</span><span class="sxs-lookup"><span data-stu-id="f65be-119">RuleInfo_Type</span></span>](ruleinfo_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="f65be-120">属性</span><span class="sxs-lookup"><span data-stu-id="f65be-120">Attributes</span></span>

|<span data-ttu-id="f65be-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="f65be-121">**Attribute**</span></span>|<span data-ttu-id="f65be-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="f65be-122">**Type**</span></span>|<span data-ttu-id="f65be-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="f65be-123">**Required**</span></span>|<span data-ttu-id="f65be-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="f65be-124">**Description**</span></span>|<span data-ttu-id="f65be-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f65be-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f65be-126">ID</span><span class="sxs-lookup"><span data-stu-id="f65be-126">ID</span></span>  <br/> |<span data-ttu-id="f65be-127">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="f65be-127">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="f65be-128">必需</span><span class="sxs-lookup"><span data-stu-id="f65be-128">required</span></span>  <br/> ||<span data-ttu-id="f65be-129">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f65be-129">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="f65be-130">忽略</span><span class="sxs-lookup"><span data-stu-id="f65be-130">Ignored</span></span>  <br/> |<span data-ttu-id="f65be-131">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="f65be-131">xsd:boolean</span></span>  <br/> |<span data-ttu-id="f65be-132">可选</span><span class="sxs-lookup"><span data-stu-id="f65be-132">optional</span></span>  <br/> ||<span data-ttu-id="f65be-133">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f65be-133">Values of the xsd:boolean type.</span></span>  <br/> |
   

