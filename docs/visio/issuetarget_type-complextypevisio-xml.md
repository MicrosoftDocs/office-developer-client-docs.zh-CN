---
title: IssueTarget_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7a0dde1d-5748-63ce-b0da-87f545299b38
ms.openlocfilehash: b9e69edc5bd30ede969bc77d43501a4473e9f69e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780493"
---
# <a name="issuetargettype-complextype-visio-xml"></a><span data-ttu-id="26ee7-102">IssueTarget_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="26ee7-102">IssueTarget_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="26ee7-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="26ee7-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="26ee7-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="26ee7-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="26ee7-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="26ee7-105">**Schema file**</span></span> <br/> |<span data-ttu-id="26ee7-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="26ee7-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="26ee7-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="26ee7-107">**Extension base**</span></span> <br/> |<span data-ttu-id="26ee7-108">无</span><span class="sxs-lookup"><span data-stu-id="26ee7-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="26ee7-109">定义</span><span class="sxs-lookup"><span data-stu-id="26ee7-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="26ee7-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="26ee7-110">Elements and attributes</span></span>

<span data-ttu-id="26ee7-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="26ee7-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="26ee7-112">子元素</span><span class="sxs-lookup"><span data-stu-id="26ee7-112">Child elements</span></span>

<span data-ttu-id="26ee7-113">无。</span><span class="sxs-lookup"><span data-stu-id="26ee7-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="26ee7-114">属性</span><span class="sxs-lookup"><span data-stu-id="26ee7-114">Attributes</span></span>

|<span data-ttu-id="26ee7-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="26ee7-115">**Attribute**</span></span>|<span data-ttu-id="26ee7-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="26ee7-116">**Type**</span></span>|<span data-ttu-id="26ee7-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="26ee7-117">**Required**</span></span>|<span data-ttu-id="26ee7-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="26ee7-118">**Description**</span></span>|<span data-ttu-id="26ee7-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="26ee7-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="26ee7-120">PageID</span><span class="sxs-lookup"><span data-stu-id="26ee7-120">PageID</span></span>  <br/> |<span data-ttu-id="26ee7-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="26ee7-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="26ee7-122">必需</span><span class="sxs-lookup"><span data-stu-id="26ee7-122">required</span></span>  <br/> ||<span data-ttu-id="26ee7-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="26ee7-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="26ee7-124">ShapeID</span><span class="sxs-lookup"><span data-stu-id="26ee7-124">ShapeID</span></span>  <br/> |<span data-ttu-id="26ee7-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="26ee7-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="26ee7-126">必需</span><span class="sxs-lookup"><span data-stu-id="26ee7-126">required</span></span>  <br/> ||<span data-ttu-id="26ee7-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="26ee7-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

