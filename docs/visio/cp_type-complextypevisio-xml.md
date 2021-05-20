---
title: 'cp_Type XML (Visio complexType) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1e69b0db-f705-61f0-e6ab-811b2acc358e
ms.openlocfilehash: afbba1f5b6e809d1f7ac673c6f77e762aa45ac5b
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540537"
---
# <a name="cp_type-complextype-visio-xml"></a><span data-ttu-id="5b5ae-102">cp_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="5b5ae-102">cp_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="5b5ae-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="5b5ae-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5b5ae-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5b5ae-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="5b5ae-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5b5ae-105">**Schema file**</span></span> <br/> |<span data-ttu-id="5b5ae-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="5b5ae-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="5b5ae-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="5b5ae-107">**Extension base**</span></span> <br/> |<span data-ttu-id="5b5ae-108">无</span><span class="sxs-lookup"><span data-stu-id="5b5ae-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5b5ae-109">定义</span><span class="sxs-lookup"><span data-stu-id="5b5ae-109">Definition</span></span>

```XML
      <xs:complexType name="cp_Type">
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="5b5ae-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5b5ae-110">Elements and attributes</span></span>

<span data-ttu-id="5b5ae-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="5b5ae-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5b5ae-112">Child elements</span></span>

<span data-ttu-id="5b5ae-113">无。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="5b5ae-114">属性</span><span class="sxs-lookup"><span data-stu-id="5b5ae-114">Attributes</span></span>

|<span data-ttu-id="5b5ae-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="5b5ae-115">**Attribute**</span></span>|<span data-ttu-id="5b5ae-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="5b5ae-116">**Type**</span></span>|<span data-ttu-id="5b5ae-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="5b5ae-117">**Required**</span></span>|<span data-ttu-id="5b5ae-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="5b5ae-118">**Description**</span></span>|<span data-ttu-id="5b5ae-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="5b5ae-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5b5ae-120">IX</span><span class="sxs-lookup"><span data-stu-id="5b5ae-120">IX</span></span>  <br/> |<span data-ttu-id="5b5ae-121">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5b5ae-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5b5ae-122">必需</span><span class="sxs-lookup"><span data-stu-id="5b5ae-122">required</span></span>  <br/> ||<span data-ttu-id="5b5ae-123">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

