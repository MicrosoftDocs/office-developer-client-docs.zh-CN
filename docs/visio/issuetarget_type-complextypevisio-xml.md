---
title: 'IssueTarget_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7a0dde1d-5748-63ce-b0da-87f545299b38
ms.openlocfilehash: 38c73e54ff75e94468cfb95258f1fde510d8019a
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542140"
---
# <a name="issuetarget_type-complextype-visio-xml"></a><span data-ttu-id="3ffe8-102">IssueTarget_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="3ffe8-102">IssueTarget_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="3ffe8-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="3ffe8-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3ffe8-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3ffe8-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="3ffe8-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3ffe8-105">**Schema file**</span></span> <br/> |<span data-ttu-id="3ffe8-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="3ffe8-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="3ffe8-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="3ffe8-107">**Extension base**</span></span> <br/> |<span data-ttu-id="3ffe8-108">无</span><span class="sxs-lookup"><span data-stu-id="3ffe8-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3ffe8-109">定义</span><span class="sxs-lookup"><span data-stu-id="3ffe8-109">Definition</span></span>

```XML
      <xs:complexType name="IssueTarget_Type">
    <xs:attribute name="PageID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="ShapeID"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="3ffe8-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3ffe8-110">Elements and attributes</span></span>

<span data-ttu-id="3ffe8-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="3ffe8-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="3ffe8-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3ffe8-112">Child elements</span></span>

<span data-ttu-id="3ffe8-113">无。</span><span class="sxs-lookup"><span data-stu-id="3ffe8-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="3ffe8-114">属性</span><span class="sxs-lookup"><span data-stu-id="3ffe8-114">Attributes</span></span>

|<span data-ttu-id="3ffe8-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="3ffe8-115">**Attribute**</span></span>|<span data-ttu-id="3ffe8-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="3ffe8-116">**Type**</span></span>|<span data-ttu-id="3ffe8-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="3ffe8-117">**Required**</span></span>|<span data-ttu-id="3ffe8-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="3ffe8-118">**Description**</span></span>|<span data-ttu-id="3ffe8-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="3ffe8-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3ffe8-120">PageID</span><span class="sxs-lookup"><span data-stu-id="3ffe8-120">PageID</span></span>  <br/> |<span data-ttu-id="3ffe8-121">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="3ffe8-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="3ffe8-122">必需</span><span class="sxs-lookup"><span data-stu-id="3ffe8-122">required</span></span>  <br/> ||<span data-ttu-id="3ffe8-123">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3ffe8-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="3ffe8-124">ShapeID</span><span class="sxs-lookup"><span data-stu-id="3ffe8-124">ShapeID</span></span>  <br/> |<span data-ttu-id="3ffe8-125">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="3ffe8-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="3ffe8-126">必需</span><span class="sxs-lookup"><span data-stu-id="3ffe8-126">required</span></span>  <br/> ||<span data-ttu-id="3ffe8-127">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3ffe8-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

