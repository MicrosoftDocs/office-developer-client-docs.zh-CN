---
title: 'ColorEntry_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d56b6110-634d-02d8-cf11-7902a2aaaf49
ms.openlocfilehash: f5ada3fef8d50c2e53f63c797601980f88349868
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540145"
---
# <a name="colorentry_type-complextype-visio-xml"></a><span data-ttu-id="1c37a-102">ColorEntry_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="1c37a-102">ColorEntry_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="1c37a-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="1c37a-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1c37a-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1c37a-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="1c37a-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1c37a-105">**Schema file**</span></span> <br/> |<span data-ttu-id="1c37a-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="1c37a-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="1c37a-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="1c37a-107">**Extension base**</span></span> <br/> |<span data-ttu-id="1c37a-108">无</span><span class="sxs-lookup"><span data-stu-id="1c37a-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1c37a-109">定义</span><span class="sxs-lookup"><span data-stu-id="1c37a-109">Definition</span></span>

```XML
      <xs:complexType name="ColorEntry_Type">
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="RGB"
  type="xsd:string"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="1c37a-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1c37a-110">Elements and attributes</span></span>

<span data-ttu-id="1c37a-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="1c37a-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="1c37a-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1c37a-112">Child elements</span></span>

<span data-ttu-id="1c37a-113">无。</span><span class="sxs-lookup"><span data-stu-id="1c37a-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="1c37a-114">属性</span><span class="sxs-lookup"><span data-stu-id="1c37a-114">Attributes</span></span>

|<span data-ttu-id="1c37a-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="1c37a-115">**Attribute**</span></span>|<span data-ttu-id="1c37a-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="1c37a-116">**Type**</span></span>|<span data-ttu-id="1c37a-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="1c37a-117">**Required**</span></span>|<span data-ttu-id="1c37a-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="1c37a-118">**Description**</span></span>|<span data-ttu-id="1c37a-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1c37a-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1c37a-120">IX</span><span class="sxs-lookup"><span data-stu-id="1c37a-120">IX</span></span>  <br/> |<span data-ttu-id="1c37a-121">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="1c37a-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="1c37a-122">必需</span><span class="sxs-lookup"><span data-stu-id="1c37a-122">required</span></span>  <br/> ||<span data-ttu-id="1c37a-123">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1c37a-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="1c37a-124">RGB</span><span class="sxs-lookup"><span data-stu-id="1c37a-124">RGB</span></span>  <br/> |<span data-ttu-id="1c37a-125">xsd：string</span><span class="sxs-lookup"><span data-stu-id="1c37a-125">xsd:string</span></span>  <br/> |<span data-ttu-id="1c37a-126">必需</span><span class="sxs-lookup"><span data-stu-id="1c37a-126">required</span></span>  <br/> ||<span data-ttu-id="1c37a-127">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1c37a-127">Values of the xsd:string type.</span></span>  <br/> |
   

