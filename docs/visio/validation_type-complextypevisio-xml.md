---
title: Validation_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1bc106ec-879a-0a4b-8c04-a5734eb0097a
ms.openlocfilehash: 6f751db1566e39d919fd0a456d3aab72559ceeba
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385590"
---
# <a name="validationtype-complextype-visio-xml"></a><span data-ttu-id="abebf-102">Validation_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="abebf-102">Validation_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="abebf-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="abebf-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="abebf-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="abebf-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="abebf-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="abebf-105">**Schema file**</span></span> <br/> |<span data-ttu-id="abebf-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="abebf-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="abebf-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="abebf-107">**Extension base**</span></span> <br/> |<span data-ttu-id="abebf-108">无</span><span class="sxs-lookup"><span data-stu-id="abebf-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="abebf-109">定义</span><span class="sxs-lookup"><span data-stu-id="abebf-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="abebf-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="abebf-110">Elements and attributes</span></span>

<span data-ttu-id="abebf-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="abebf-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="abebf-112">子元素</span><span class="sxs-lookup"><span data-stu-id="abebf-112">Child elements</span></span>

|<span data-ttu-id="abebf-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="abebf-113">**Element**</span></span>|<span data-ttu-id="abebf-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="abebf-114">**Type**</span></span>|<span data-ttu-id="abebf-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="abebf-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="abebf-116">问题</span><span class="sxs-lookup"><span data-stu-id="abebf-116">Issues</span></span>](issues-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="abebf-117">Issues_Type</span><span class="sxs-lookup"><span data-stu-id="abebf-117">Issues_Type</span></span>](issues_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="abebf-118">规则集</span><span class="sxs-lookup"><span data-stu-id="abebf-118">RuleSets</span></span>](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="abebf-119">RuleSets_Type</span><span class="sxs-lookup"><span data-stu-id="abebf-119">RuleSets_Type</span></span>](rulesets_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="abebf-120">ValidationProperties</span><span class="sxs-lookup"><span data-stu-id="abebf-120">ValidationProperties</span></span>](validationproperties-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="abebf-121">ValidationProperties_Type</span><span class="sxs-lookup"><span data-stu-id="abebf-121">ValidationProperties_Type</span></span>](validationproperties_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="abebf-122">Attributes</span><span class="sxs-lookup"><span data-stu-id="abebf-122">Attributes</span></span>

<span data-ttu-id="abebf-123">无。</span><span class="sxs-lookup"><span data-stu-id="abebf-123">None.</span></span>
  

