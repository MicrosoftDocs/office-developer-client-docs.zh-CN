---
title: Validation_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1bc106ec-879a-0a4b-8c04-a5734eb0097a
ms.openlocfilehash: 26e7dec4ea54e118afd85ec25f334e69849a57dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19781624"
---
# <a name="validationtype-complextype-visio-xml"></a><span data-ttu-id="5e7d0-102">Validation_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="5e7d0-102">Validation_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="5e7d0-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="5e7d0-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5e7d0-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5e7d0-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="5e7d0-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5e7d0-105">**Schema file**</span></span> <br/> |<span data-ttu-id="5e7d0-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="5e7d0-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="5e7d0-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="5e7d0-107">**Extension base**</span></span> <br/> |<span data-ttu-id="5e7d0-108">无</span><span class="sxs-lookup"><span data-stu-id="5e7d0-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5e7d0-109">定义</span><span class="sxs-lookup"><span data-stu-id="5e7d0-109">Definition</span></span>

```XML
          <xs:complexType name="Validation_Type">
          
          <xs:sequence>
    <xs:element name="ValidationProperties"  type="ValidationProperties_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="RuleSets"  type="RuleSets_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Issues"  type="Issues_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="5e7d0-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5e7d0-110">Elements and attributes</span></span>

<span data-ttu-id="5e7d0-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="5e7d0-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="5e7d0-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5e7d0-112">Child elements</span></span>

|<span data-ttu-id="5e7d0-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="5e7d0-113">**Element**</span></span>|<span data-ttu-id="5e7d0-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="5e7d0-114">**Type**</span></span>|<span data-ttu-id="5e7d0-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="5e7d0-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5e7d0-116">问题</span><span class="sxs-lookup"><span data-stu-id="5e7d0-116">Issues</span></span>](issues-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5e7d0-117">Issues_Type</span><span class="sxs-lookup"><span data-stu-id="5e7d0-117">Issues_Type</span></span>](issues_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="5e7d0-118">规则集</span><span class="sxs-lookup"><span data-stu-id="5e7d0-118">RuleSets</span></span>](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5e7d0-119">RuleSets_Type</span><span class="sxs-lookup"><span data-stu-id="5e7d0-119">RuleSets_Type</span></span>](rulesets_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="5e7d0-120">ValidationProperties</span><span class="sxs-lookup"><span data-stu-id="5e7d0-120">ValidationProperties</span></span>](validationproperties-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5e7d0-121">ValidationProperties_Type</span><span class="sxs-lookup"><span data-stu-id="5e7d0-121">ValidationProperties_Type</span></span>](validationproperties_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="5e7d0-122">Attributes</span><span class="sxs-lookup"><span data-stu-id="5e7d0-122">Attributes</span></span>

<span data-ttu-id="5e7d0-123">无。</span><span class="sxs-lookup"><span data-stu-id="5e7d0-123">None.</span></span>
  

