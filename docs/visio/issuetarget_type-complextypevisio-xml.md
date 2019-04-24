---
title: IssueTarget_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7a0dde1d-5748-63ce-b0da-87f545299b38
ms.openlocfilehash: d7b8309bb6dac9648d379c89687dc89165f44edf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314922"
---
# <a name="issuetargettype-complextype-visio-xml"></a><span data-ttu-id="73f0c-102">IssueTarget_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="73f0c-102">IssueTarget_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="73f0c-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="73f0c-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="73f0c-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="73f0c-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="73f0c-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="73f0c-105">**Schema file**</span></span> <br/> |<span data-ttu-id="73f0c-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="73f0c-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="73f0c-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="73f0c-107">**Extension base**</span></span> <br/> |<span data-ttu-id="73f0c-108">无</span><span class="sxs-lookup"><span data-stu-id="73f0c-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="73f0c-109">定义</span><span class="sxs-lookup"><span data-stu-id="73f0c-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="73f0c-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="73f0c-110">Elements and attributes</span></span>

<span data-ttu-id="73f0c-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="73f0c-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="73f0c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="73f0c-112">Child elements</span></span>

<span data-ttu-id="73f0c-113">无。</span><span class="sxs-lookup"><span data-stu-id="73f0c-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="73f0c-114">属性</span><span class="sxs-lookup"><span data-stu-id="73f0c-114">Attributes</span></span>

|<span data-ttu-id="73f0c-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="73f0c-115">**Attribute**</span></span>|<span data-ttu-id="73f0c-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="73f0c-116">**Type**</span></span>|<span data-ttu-id="73f0c-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="73f0c-117">**Required**</span></span>|<span data-ttu-id="73f0c-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="73f0c-118">**Description**</span></span>|<span data-ttu-id="73f0c-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="73f0c-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="73f0c-120">PageID</span><span class="sxs-lookup"><span data-stu-id="73f0c-120">PageID</span></span>  <br/> |<span data-ttu-id="73f0c-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="73f0c-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="73f0c-122">必需</span><span class="sxs-lookup"><span data-stu-id="73f0c-122">required</span></span>  <br/> ||<span data-ttu-id="73f0c-123">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73f0c-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="73f0c-124">ShapeID</span><span class="sxs-lookup"><span data-stu-id="73f0c-124">ShapeID</span></span>  <br/> |<span data-ttu-id="73f0c-125">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="73f0c-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="73f0c-126">必需</span><span class="sxs-lookup"><span data-stu-id="73f0c-126">required</span></span>  <br/> ||<span data-ttu-id="73f0c-127">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="73f0c-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

