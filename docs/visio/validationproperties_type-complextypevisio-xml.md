---
title: 'ValidationProperties_Type XML (Visio complexType) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3b0d1209-4636-ea9c-acf7-895c3300492a
ms.openlocfilehash: d83a1ce8e7ad89155726200de2950da755e5d3db
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538513"
---
# <a name="validationproperties_type-complextype-visio-xml"></a><span data-ttu-id="0851d-102">ValidationProperties_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="0851d-102">ValidationProperties_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="0851d-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="0851d-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0851d-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0851d-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="0851d-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0851d-105">**Schema file**</span></span> <br/> |<span data-ttu-id="0851d-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="0851d-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="0851d-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="0851d-107">**Extension base**</span></span> <br/> |<span data-ttu-id="0851d-108">无</span><span class="sxs-lookup"><span data-stu-id="0851d-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0851d-109">定义</span><span class="sxs-lookup"><span data-stu-id="0851d-109">Definition</span></span>

```XML
      <xs:complexType name="ValidationProperties_Type">
    <xs:attribute name="LastValidated"
  type="xsd:dateTime"
     use="required"
    />
    <xs:attribute name="ShowIgnored"
  type="xsd:boolean"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="0851d-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0851d-110">Elements and attributes</span></span>

<span data-ttu-id="0851d-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="0851d-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="0851d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="0851d-112">Child elements</span></span>

<span data-ttu-id="0851d-113">无。</span><span class="sxs-lookup"><span data-stu-id="0851d-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="0851d-114">属性</span><span class="sxs-lookup"><span data-stu-id="0851d-114">Attributes</span></span>

|<span data-ttu-id="0851d-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="0851d-115">**Attribute**</span></span>|<span data-ttu-id="0851d-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="0851d-116">**Type**</span></span>|<span data-ttu-id="0851d-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="0851d-117">**Required**</span></span>|<span data-ttu-id="0851d-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="0851d-118">**Description**</span></span>|<span data-ttu-id="0851d-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="0851d-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0851d-120">LastValidated</span><span class="sxs-lookup"><span data-stu-id="0851d-120">LastValidated</span></span>  <br/> |<span data-ttu-id="0851d-121">xsd：dateTime</span><span class="sxs-lookup"><span data-stu-id="0851d-121">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="0851d-122">必需</span><span class="sxs-lookup"><span data-stu-id="0851d-122">required</span></span>  <br/> ||<span data-ttu-id="0851d-123">xsd：dateTime 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0851d-123">Values of the xsd:dateTime type.</span></span>  <br/> |
|<span data-ttu-id="0851d-124">ShowIgnored</span><span class="sxs-lookup"><span data-stu-id="0851d-124">ShowIgnored</span></span>  <br/> |<span data-ttu-id="0851d-125">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="0851d-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="0851d-126">必需</span><span class="sxs-lookup"><span data-stu-id="0851d-126">required</span></span>  <br/> ||<span data-ttu-id="0851d-127">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0851d-127">Values of the xsd:boolean type.</span></span>  <br/> |
   

