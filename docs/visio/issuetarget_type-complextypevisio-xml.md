---
title: IssueTarget_Type 复杂类型 (Visio XML)
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
# <a name="issuetargettype-complextype-visio-xml"></a><span data-ttu-id="cc1dd-102">IssueTarget_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="cc1dd-102">IssueTarget_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="cc1dd-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="cc1dd-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="cc1dd-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="cc1dd-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="cc1dd-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="cc1dd-105">**Schema file**</span></span> <br/> |<span data-ttu-id="cc1dd-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="cc1dd-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="cc1dd-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="cc1dd-107">**Extension base**</span></span> <br/> |<span data-ttu-id="cc1dd-108">无</span><span class="sxs-lookup"><span data-stu-id="cc1dd-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="cc1dd-109">定义</span><span class="sxs-lookup"><span data-stu-id="cc1dd-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="cc1dd-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="cc1dd-110">Elements and attributes</span></span>

<span data-ttu-id="cc1dd-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="cc1dd-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="cc1dd-112">子元素</span><span class="sxs-lookup"><span data-stu-id="cc1dd-112">Child elements</span></span>

<span data-ttu-id="cc1dd-113">无。</span><span class="sxs-lookup"><span data-stu-id="cc1dd-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="cc1dd-114">属性</span><span class="sxs-lookup"><span data-stu-id="cc1dd-114">Attributes</span></span>

|<span data-ttu-id="cc1dd-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="cc1dd-115">**Attribute**</span></span>|<span data-ttu-id="cc1dd-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="cc1dd-116">**Type**</span></span>|<span data-ttu-id="cc1dd-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="cc1dd-117">**Required**</span></span>|<span data-ttu-id="cc1dd-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="cc1dd-118">**Description**</span></span>|<span data-ttu-id="cc1dd-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="cc1dd-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc1dd-120">PageID</span><span class="sxs-lookup"><span data-stu-id="cc1dd-120">PageID</span></span>  <br/> |<span data-ttu-id="cc1dd-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="cc1dd-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="cc1dd-122">必需</span><span class="sxs-lookup"><span data-stu-id="cc1dd-122">required</span></span>  <br/> ||<span data-ttu-id="cc1dd-123">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="cc1dd-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="cc1dd-124">ShapeID</span><span class="sxs-lookup"><span data-stu-id="cc1dd-124">ShapeID</span></span>  <br/> |<span data-ttu-id="cc1dd-125">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="cc1dd-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="cc1dd-126">必需</span><span class="sxs-lookup"><span data-stu-id="cc1dd-126">required</span></span>  <br/> ||<span data-ttu-id="cc1dd-127">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="cc1dd-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

